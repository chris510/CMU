# TripleByte

Created By: Chris Trinh
Last Edited: Jan 01, 2020 10:39 PM

I first took the generalist interview, and I didn't pass it but felt I could have based on the experience if I had performed to the best of my ability. So I signed up for a front end interview two days later and passed. I believe they have a couple month wait period if you want to take the same subject over again after not passing but I was allowed to immediately pivot to a different track and reinterview right away. There was a lot of overlap between the two interviews, only a few sections were much different so I think that might be a good strategy to do both. I didn't do a practice interview but I know they offer them as well if you want to see what it is like.Both were about two hours in total, with a live coding exercise (where you can google stuff you need to know but the time is tight), some trivia on datastructures, some general trivia (http, promises, security, you don't have to know all of it I had to punt on some subjects), and a system design question. For the system design they want you to name specific technologies eg Rails and postgres but the way they phrased the question that wasn't obvious to me at first.If you do the frontend one you should have a front end framework boilerplate ready to go (like a create-react-app all set up and configured before the interview started) and be ready to deal with a slightly nested state. If you do the generalist one you should maybe not choose javascript as your language for the first coding exercise. Reading user input from the terminal in node is an annoying async operation, I got stuck on that for a large amount of time and I think that was what specifically prevented me from passing the first interview I took. Either way for the live coding exercise you should focus on just making it function as it should quickly even if it's messy. The grading is based on if you were able to get certain functionality implemented in a short period of time. Generalist also had a debugging section where they send you a written program that fails some specs and ask you to make them pass. Front end they didn't do that, but asked me questions about how I would debug a site if it was slow (chrome dev tools, lighthouse audits).A ton of people take the interviews so if you search around online you can find more on specific questions people were asked.

The person asked if I moved to bay-area at some point or if I was born and raised there. How did I like being in bay-area. He shared his eperience of living in Georgia(Russia). I think we spent like 5 mins talking about the pros-cons of SF bay. He said he didn't like San Francisco that much but couldn't quite put his finger on why.He had a considerable Russian accent which made it difficult to understand what he was saying. I had to ask him to repeat himself( sometimes twice) many times. He didn't seem to be annoyed by this and repeated whenever I asked.Coding Round : Screenshare ( I picked javascript for this)

- Design a class to implement Spreadsheet. It takes in number of rows and columns and has two methods update and eg. Alice|5|foo Bob|10| || ||
- pretty_print - Left aligned, dynamically assigned width Alice |5 |foo Bob |10|

There must have been a lot more to it but I never got to that part because I was stuck in finishing this part.Short conceptual questions: VERBALDatabase

- What is a normalized db
- What is foreign key
- How is foreign key useful to normalize db
- what are indices
- How are indices implemented
- what are the advantages/disadvantages of having indices
- What are composed indices
- How do you measure performance of a query ( what tools would you use, what output does it provide that is relevant to you)

System Level

- What is a mutex
- What is deadlock
- What are reader/writer locks Data structures

Hashes and Maps

- How are they implemented
- What are collisions
- If you have 64000 values getting stored using a hash function that has 64 possible outputs, how would you store them.
- What is Bloom Filter
- How do we store passwords in tables
- What is hashing and salting
- Where is salt value stored [https://brilliant.org/wiki/bloom-filter/](https://slack-redir.net/link?url=https%3A%2F%2Fbrilliant.org%2Fwiki%2Fbloom-filter%2F)
- How does malloc function works in C ( what parameters you pass to it and what is the output)
- How does free function work
- Binary Search Trees
- Search time Big O, Worst case search time
- How to you find kth smallest element ( preorder traversal?)
- How is preorder traversal implemented ( I tried to explain it but found it hard to do it verbally probably because I didn't remember the algorithm very well)

Debugging Round: Screenshare ( I picked Ruby for this)Find bugs in Web Crawler. They provided nice specs for it. Make sure to run passing specs after each fix, it's possible to fail passing specs while you THINK you fixed the failing specs ( which would be awful).System Architecture :VERBALHTTP Difference between GET and POST requests How does caching work, what is load balancing?Q. A colleague has given you data scraped from Craigslist on used cars. It contains data about many million cars and has their make, model, color, miles, location etc. You have to design a system that would query the data and return the details about cars. What would be the API endpoints of this system? Example - All the red hondas, between 30000 - 50000 miles located in Baltimore.Personal Questions

- Q. Number of years of experience in software
- Q. What did you work on
- Q. What are you looking for in your next job ( The interviewer commented on my desired job being 180 degree to my previous job)
- Q. What kind of company I would prefer
- Q. If I had any questions other than the next steps

[https://slack-imgs.com/?c=1&o1=wi32.he32.si&url=https%3A%2F%2Fbrilliant.org%2Fapple-touch-icon-precomposed.png](https://slack-imgs.com/?c=1&o1=wi32.he32.si&url=https%3A%2F%2Fbrilliant.org%2Fapple-touch-icon-precomposed.png)

**brilliant.org**

**[Bloom Filter | Brilliant Math & Science Wiki](https://brilliant.org/wiki/bloom-filter/)**

A bloom filter is a probabilistic data structure that is based on hashing. It is extremely space efficient and is typically used to add elements to a set and test if an element is in a set. Though, the elements themselves are not added to a set. Instead a hash of the elements is added to the set. When testing if an element is in the bloom filter, false positives are possible. It will either ...(16 kB)