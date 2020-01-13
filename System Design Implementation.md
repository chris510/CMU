# System Design Implementation

Created By: Chris Trinh
Last Edited: Jan 12, 2020 1:41 PM

- What are the steps for answering a system design interview question?
    - 1. Clarify Requirements
        - Ask open-ended questions that clarifies the scope of the problem
        - Defining the end goals have a better chance to be successful in the interview
        - Examples Of Twitter
            - Will users of our service be able to post tweets and follow other people?
            - Should we also design to create and display the user’s timeline?
            - Will tweets contain photos and videos?
            - Are we focusing on the backend only or are we developing the front-end too?
            - Will users be able to search tweets?
            - Do we need to display hot trending topics?
            - Will there be any push notification for new (or important) tweets?
    - 2.Backend Estimations
        - To estimate the scale at which the system is going to for design. Helps in the future with scaling, partitioning, load balancing, and caching.
        - Examples
            - What scale is expected from the system (e.g., number of new tweets, number of tweet views, number of timeline generations per sec., etc.)?
            - How much storage will we need? We will have different storage requirements if users can have photos and videos in their tweets.
            - What network bandwidth usage are we expecting? This will be crucial in deciding how we will manage traffic and balance load between servers.
    - 3.Define the System Interface
        - Define the APIs that are needed for the system
        - Which things do we need to retrieve from a database to show to the user?
        - Examples
            - PostTweet
            - generateTimeLine
            - markTweetFavorite
    - 4.Define the Data Model
        - Clarify schema in how data will flow between different components in the application
        - Example
            - **Users:** UserID, Name, Email, DoB, CreationData, LastLogin, etc.
            - **Tweet:** TweetID, Content, TweetLocation, NumberOfLikes, TimeStamp, etc.
            - **UserFollowo:** UserdID1, UserID2
            - **FavoriteTweets:** UserID, TweetID, TimeStamp
        - Which database system should we use and why?
    - 5.Create a High Level Design
        - Draw a high level design to identify actual components to solve the problem from end-to-end
        - Twitter needs multiple application servers for all the read/write requests with load balancers for distributing them between the servers.
            - If there are assumptions on read traffic being more than write, we can have separate servers handling the scenarios instead of putting both uses in one.
            - Need an efficient backend that can store all the tweets and support a large number of reads without overflow
            - Distributed file storage system for storing photos and videos
    - 6.Detail the Design
        - Select a few more important components to go deeper on. Should be able to provide different approaches for implementation, pros and cons, and explain why one approach is more preferable than the other
        - Consider the tradeoffs
        - Twitter Examples
            - Since we will be storing a massive amount of data, how should we partition our data to distribute it to multiple databases? Should we try to store all the data of a user on the same database? What issue could it cause?
            - How will we handle hot users who tweet a lot or follow lots of people?
            - Since users’ timeline will contain the most recent (and relevant) tweets, should we try to store our data in such a way that is optimized for scanning the latest tweets?
            - How much and at which layer should we introduce cache to speed things up?
            - What components need better load balancing?
    - 7.Identify and resolve Bottle Necks
        - Examples
        - Is there any single point of failure in our system? What are we doing to mitigate it?
        - Do we have enough replicas of the data so that if we lose a few servers, we can still serve our users?
        - Similarly, do we have enough copies of different services running such that a few failures will not cause total system shutdown?
        - How are we monitoring the performance of our service? Do we get alerts whenever critical components fail or their performance degrades?
- Url Shortening Service (TinyURL)
    - What is a URL shortener?
        - Creates shorter alias for long urls that redirect to the original Link
        - Saves a lot of space when displayed, printed, messaged, or tweeted
        - Users are less likely to mistype shorter URLs
    - Whats it used for and why do we need it?
        - Optimizing links across devices, tracking individual links, analyze audience and campaign performance, and hiding affiliated original URLs
    - What are the requirements?
        - What are the four functional requirements?
            1. When we have URL, we should create a unique and shorter alias. Short enough to be copied and pasted into applications
            2. Clicking the shorter link should redirect them to the original link
            3. Users should be able to pick a custom short link for their URL
            4. Links should expire after a default time span, but users should be able to put an expiration date
        - What are the 3 non functional requirements?
            1. System should be up and working all the time because if the service is down, the URL redirections from short link to original won't work.
            2. Redirection should work in real time without minimal latency
            3. Shortened Links should not be guessable or predictable
        - Any extended requirements?
            1. Analytics, how many times does the redirect link get clicked or happen?
            2. Should we have REST API's that are able to use the service?

    - What are capacity estimations and constraints?
        - We have to take into account the limit of our system like read/write. Assume 100:1 ratio of read/write
        - What are the traffic estimates?
            - Take into account how many new URL shortenings per month and how many redirections. 50B
            - Look at the queries per second(QPS)
                - 500mil / 30days*24hrs * 3600 secs = ~200URLS/s
            - How many URLs redirections per second?
                - 100 * 200 URLs/s = 20K/s
        - What are the storage estimates?
            - We have to assume we are storing every URL shortening request and a link that is associated with it.
            - Since 500mil new URLs every month, then we will store 30 billion for 5 years
                - 500mil * 5 years * 12months
            - Each object is assumed 500 bytes so
                - 30billion * 500bytes = 15TB of storage
        - Bandwidth estimates?
            - For write request, assume 200 new URLs every second and total data into service will be 100KB/s
                - So 200 * 500bytes = 100KB/s
            - For read request, we expect 20k URLs redirects per second so
                - 20k * 500bytes = 10MB/s
        - Memory estimates?
            - Use a caching system to cache the frequently accessed URLs. How much memory do we need to store? Follow 80/20 rule(traffic/hotURLs)
            - 20k Requests/s equals 1.7 billion requests per day
                - 20k * 3600 seconds * 24 hours
            - To cache 20% of these requests, we need 170GB of memory
                - 0.2 * 1.7billion * 500bytes = ~170GB
                - We note that sometimes theres duplicate requests so the actual memory usage will be less than 170GB
        - High level estimates?
            - New URLs: 200/s
            - URL directions: 20k / second
            - Incoming Data: 100KB/second
            - Outgoing Data: 10MB/second
            - Storage for 5 years: 15TB
            - Memory for Cache: 170GB