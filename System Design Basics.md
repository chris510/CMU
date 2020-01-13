# System Design Basics

Created By: Chris Trinh
Last Edited: Jan 12, 2020 1:40 PM

**Basics**

- What do we consider when designing a large system?
    - Architectural Pieces
    - How they work with each other
    - How to best utilized pieces and possible tradeoffs

Scalability

- What is scalability?
    - ability for the system, process, or network to grow and manage increased demand.
- What are some reasons a system has to scale?
    - Increased data volume or increase amount of work involved (e.g. # of transactions)
- Why may a system's performance decline because of scalability?
    - Machines are far apart from each other
    - Task may not be distributed properly, because of inherent atomic nature or flaw in the initial design.
    - Poor initial scalable architecture design, so planning for balancing of load for participating nodes is needed
- What is horizontal scaling?
    - Add more servers
    - Easier to scale dynamically
- What is vertical scaling?
    - Increase the capacity of the servers like CPU, RAM, or Storage
    - Limited by capacity of single server and scaling involves downtime but comes with an upper limit
- What are examples of horizontal scaling and vertical?
    - Horizontal: Cassandra and MongoDB
    - Vertical: MySQL

Reliability

- What is reliability?
    - Probability that a system will fail within a given period
- What is considered reliable?
    - If a system is able to keep up with its processes when one or several software/hardware components fail.
- What is an example of a reliable system?
    - Amazon keeps user transactions and keeps a users shopping cart, system is not expected to lose it. If the server carrying the user's shopping cart breaks, then the server has the exact replica of the shopping cart
    - Pros of a redundant system creates reliability but higher cost

Availability

- What is availability?
    - Time a system remains operational within a time period
- What are the comparisons of a system being reliable/available?
    - If its reliable, it is available. If its available, its not necessarily reliable.

Efficiency

- How do we measure efficiency in a system?
    - Looking at response time (latency); delay to get the first item
        - Unit cost of number of messages globally sent by nodes regardless of message size
    - Throughput (bandwidth) number of items delivered in a given time frame
        - Size of messages representing volume of data exchanges

Serviceability or Manageability 

- What is serviceability or manageability?
    - simplicity and speed in which a system can be repaired or maintained
    - Fx a failed system increases, availability will decrease
- What are things to consider?
    - Ease of diagnosing and understanding problems when they occur
    - Ease of making updates or modifications
    - How simple a system is to operate