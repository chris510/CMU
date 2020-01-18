# Caching

Created By: Chris Trinh
Last Edited: Jan 17, 2020 3:22 PM

- What is caching?
    - Uses the reference principle: stores recently requested data that is likely to be requested again.
    - Short-term memory with limited amount of space but usually super fast
- What happens when you place a cache on a request layer node?
    - Allows the response to be stored in the local storage
    - Every time theres a request, node will return the cache data super quickly if its exists
- What happens when cache is placed on too many nodes?
    - If the load balancer distributes these requests randomly, there will be increase chance of a cache miss.
    - can use global caches and distributed caches to prevent the misses
- Whats a cache miss and hit?
    - Hit is where the content that the cache is searched for returns found data. Miss is opposite where the data isn't found.
- What are CDNs?
    - Content Distribution Network
    - Used for serving large amounts of static media.
- Whats cache invalidation?
    - The cache and database are connected so if data is modified in the database, it should be invalidated in the cache. Solved with the three write cache methods.
- What is write-throgh cache?
    - Data is written into the cache and connecting database at the same time.
    - Data is written twice for every opertaion so higher write latency.
- Write-around?
    - Data is written directly to permanent storage by passing the cache.
    - Cache doesn't have unnecessary re-read data but the recent write data will go through a 'cache miss' and have high read latency
- Write back?
    - data is written to cache only and then a write to permanent storage after certain conditions.
    - Low latency and high throughput for write-intensive apps.
- What are some of the most common cache eviction policies?
    1. First In First Out (FIFO): The cache evicts the first block accessed first without any regard to how often or how many times it was accessed before.
    2. Last In First Out (LIFO): The cache evicts the block accessed most recently first without any regard to how often or how many times it was accessed before.
    3. Least Recently Used (LRU): Discards the least recently used items first.
    4. Most Recently Used (MRU): Discards, in contrast to LRU, the most recently used items first.
    5. Least Frequently Used (LFU): Counts how often an item is needed. Those that are used least often are discarded first.
    6. Random Replacement (RR): Randomly selects a candidate item and discards it to make space when necessary.