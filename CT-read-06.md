## Redis
### What is Redis?
- Redis, which stands for Remote Dictionary Server, is a fast, open-source, in-memory key-value data store for use as a database, cache, message broker, and queue.
### How does Redis work?
- All Redis data resides in-memory, in contrast to databases that store data on disk or SSDs. By eliminating the need to access disks, in-memory data stores such as Redis avoid seek time delays and can access data in microseconds.
### Redis vs Memcached
- Both Redis and MemCached are in-memory, open-source data stores. Memcached, a high-performance distributed memory cache service, is designed for simplicity while Redis offers a rich set of features that make it effective for a wide range of use cases
### What's new with Redis 5.0
-  The big story here is the introduction of Streams, the first entirely new data structure in Redis since HyperLogLog. This release also added more commands for Sorted Sets, and new capabilities for Module APIs.
### Benefits of Redis
- in-memory data store
  - All Redis data resides in the server’s main memory, in contrast to databases such as PostgreSQL, Cassandra, MongoDB and others that store most data on disk or on SSDs. In comparison to traditional disk based databases where most operations require a roundtrip to disk, in-memory data stores such as Redis don’t suffer the same penalty. They can therefore support an order of magnitude more operations and faster response times. The result is – blazing fast performance with average read or write operations taking less than a millisecond and support for millions of operations per second.
- Flexible data structures
  - Unlike simplistic key-value data stores that offer limited data structures, Redis has a vast variety of data structures to meet your application needs
- Simplicity and ease of use
  - Redis simplifies your code by enabling you to write fewer lines of code to store, access, and use data in your applications. For example, if your application has data stored in a hashmap, and you want to store that data in a data store – you can simply use the Redis hash data structure to store the data. A similar task on a data store with no hash data structures would require many lines of code to convert from one format to another. Redis comes with native data structures and many options to manipulate and interact with your data. Over a hundred open source clients are available for Redis developers. Supported languages include Java, Python, PHP, C, C++, C#, JavaScript, Node.js, Ruby, R, Go and many others.
- Replication and persistence
  - Redis employs a primary-replica architecture and supports asynchronous replication where data can be replicated to multiple replica servers. This provides improved read performance (as requests can be split among the servers) and faster recovery when the primary server experiences an outage. For persistence, Redis supports point-in-time backups (copying the Redis data set to disk)
- High availability and scalability
  - Redis offers a primary-replica architecture in a single node primary or a clustered topology. This allows you to build highly available solutions providing consistent performance and reliability. When you need to adjust your cluster size, various options to scale up and scale in or out are also available. This allows your cluster to grow with your demands.
- Extensibility
  - Redis is an open source project supported by a vibrant community. There’s no vendor or technology lock in as Redis is open standards based, supports open data formats, and features a rich set of clients.
### Popular Redis use cases
- caching
  - Redis is a great choice for implementing a highly available in-memory cache to decrease data access latency, increase throughput, and ease the load off your relational or NoSQL database and application. Redis can serve frequently requested items at sub-millisecond response times, and enables you to easily scale for higher loads without growing the costlier backend. Database query results caching, persistent session caching, web page caching, and caching of frequently used objects such as images, files, and metadata are all popular examples of caching with Redis.
- Chat, messaging and queues
  - Redis supports Pub/Sub with pattern matching and a variety of data structures such as lists, sorted sets, and hashes. This allows Redis to support high performance chat rooms, real-time comment streams, social media feeds and server intercommunication. The Redis List data structure makes it easy to implement a lightweight queue. Lists offer atomic operations as well as blocking capabilities, making them suitable for a variety of applications that require a reliable message broker or a circular list.
- gaming leaderboards
  - Redis is a popular choice among game developers looking to build real-time leaderboards. Simply use the Redis Sorted Set data structure, which provides uniqueness of elements while maintaining the list sorted by users' scores
- session store
  - Redis as an in-memory data store with high availability and persistence is a popular choice among application developers to store and manage session data for internet-scale applications
- rich media streaming
  - Redis offers a fast, in-memory data store to power live streaming use cases. Redis can be used to store metadata about users' profiles and viewing histories, authentication information/tokens for millions of users, and manifest files to enable CDNs to stream videos to millions of mobile and desktop users at a time.
- geospacial
  - Redis offers purpose-built in-memory data structures and operators to manage real-time geospatial data at scale and speed. Commands such as GEOADD, GEODIST, GEORADIUS, and GEORADIUSBYMEMBER to store, process, and analyze geospatial data in real-time make geospatial easy and fast with Redis. You can use Redis to add location-based features such as drive time, drive distance, and points of interest to your applications
- machine learning
  - Modern data-driven applications require machine learning to quickly process a massive volume, variety, and velocity of data and automate decision making. For use cases like fraud detection in gaming and financial services, real-time bidding in ad-tech, and matchmaking in dating and ride sharing, the ability to process live data and make decisions within tens of milliseconds is of utmost importance. Redis gives you a fast in-memory data store to build, train, and deploy machine learning models quickly
- real-time anylytics
  - Redis can be used with streaming solutions such as Apache Kafka and Amazon Kinesis as an in-memory data store to ingest, process, and analyze real-time data with sub-millisecond latency. Redis is an ideal choice for real-time analytics use cases such as social media analytics, ad targeting, personalization, and IoT.

## What is a queue?
- queue is another common data structure that places elements in a sequence, similar to stack
- A queue uses the FIFO method (First In First Out), by which the first element that is enqueued will be the first one to be dequeued.
- basic operations of queue
  - Enqueue() — Inserts an element to the end of the queue
  - Dequeue() — Removes an element from the start of the queue
  - isEmpty() — Returns true if queue is empty
  - Top() — Returns the first element of the queue

### Task Queues
- When handling requests from web clients, sometimes operations take more time to
execute than we want to spend immediately. We can defer those operations by putting
information about our task to be performed inside a queue, which we process later.
### FIFO queues
- In the world of queues beyond task queues, normally a few different kinds of queues
are discussed—first-in, first-out (FIFO), last-in first-out (LIFO), and priority queues.
- you can use push and pop to manage queue
- interesting tutorial
### multiple executable tasks
- Because Redis only gives a single caller a popped item, we can be sure that none of the
emails are duplicated and sent twice. Because we only put email messages to send in
the queue, our worker process was simple. Having a single queue for each type of message
### task priorities
- Sometimes when working with queues, it’s necessary to prioritize certain operations
before others.
- By using multiple queues, priorities can be implemented easily.
## Bull
### What is Bull?
- Bull is a Node library that implements a fast and robust queue system based on redis.
- Although it is possible to implement queues directly using Redis commands, this library provides an API that takes care of all the low-level details and enriches Redis basic functionality so that more complex use-cases can be handled easily.
- Queues can solve many different problems in an elegant way, from smoothing out processing peaks to creating robust communication channels between microservices or offloading heavy work from one server to many smaller workers, etc
### getting started
- Bull is a public npm package and can be installed using either npm or yarn:
  - npm install bull --save
  - yarn add bull
### simpole queues
- A queue is simply created by instantiating a Bull instance:
  - const myFirstQueue = new Bull('my-first-queue')
- A queue instance can normally have 3 main different roles: A job producer, a job consumer or/and an events listener
### producers
- A job producer is simply some Node program that adds jobs to a queue, 
  - const myFirstQueue = new Bull('my-first-queue');

const job = await myFirstQueue.add({
  foo: 'bar'
});
### consumers
- a consumer or worker is nothing more than a Node program that defines a process function
### listeners
- Finally, you can just listen to events that happen in the queue. Listeners can be local, meaning that they only will receive notifications produced in the given queue instance, or global, meaning that they listen to all the events for a given queue. So you can attach a listener to any instance, even instances that are acting as consumers or producers. But note that a local event will never fire if the queue is not a consumer or producer, you will need to use global events in that case
### a job's lifecycle
- In order to use the full potential of Bull queues, it is important to understand the lifecycle of a job. From the moment a producer calls the add method on a queue instance, a job enters a lifecycle where it will be in different states, until its completion or failure (although technically a failed job could be retried and get a new lifecycle)
- When a job is added to a queue it can be in one of two states, it can either be in the “wait” status, which is, in fact, a waiting list, where all jobs must enter before they can be processed, or it can be in a “delayed” status: a delayed status implies that the job is waiting for some timeout or to be promoted for being processed, however, a delayed job will not be processed directly, instead it will be placed at the beginning of the waiting list and processed as soon as a worker is idle.
- The next state for a job I the “active” state. The active state is represented by a set, and are jobs that are currently being processed, i.e. they are running in the process function explained in the previous chapter. A job can be in the active state for an unlimited amount of time until the process is completed or an exception is thrown so that the job will end in either the “completed” or the “failed” status.
### stalled jobs
- In Bull, we defined the concept of stalled jobs. A stalled job is a job that is being processed but where Bull suspects that the process function has hanged. This happens when the process function is processing a job and is keeping the CPU so busy that the worker is not able to tell the queue that it is still working on the job.
- When a job stalls, depending on the job settings the job can be retried by another idle worker or it can just move to the failed status.
### events
- A Queue in Bull generates a handful of events that are useful in many use cases. Events can be local for a given queue instance (a worker), for example, if a job is completed in a given worker a local event will be emitted just for that instance. However, it is possible to listen to all events, by prefixing global: to the local event name. Then we can listen to all the events produced by all the workers of a given queue
### queue options
- A queue can be instantiated with some useful options, for instance, you can specify the location and password of your Redis server, as well as some other useful settings.
- rate limiter
  - It is possible to create queues that limit the number of jobs processed in a unit of time. The limiter is defined per queue, independently of the number of workers, so you can scale horizontally and still limiting the rate of processing easily
- named jobs
  - It is possible to give names to jobs. This does not change any of the mechanics of the queue but can be used for clearer code and better visualization in UI tools
- sandboxed processors
### job types
- The default job type in Bull is “FIFO” (first in first out), meaning that the jobs are processed in the same order they are coming into the queue. Sometimes it is useful to process jobs in a different order
- LIFO
  - Lifo (last in first out) means that jobs are added to the beginning of the queue and therefore will be processed as soon as the worker is idle
- delayed
  - It is also possible to add jobs to the queue that are delayed a certain amount of time before they will be processed. Note that the delay parameter means the minimum amount of time the job will wait before being processed. When the delay time has passed the job will be moved to the beginning of the queue and be processed as soon as a worker is idle
- prioritized
  - Jobs can be added to a queue with a priority value. Jobs with higher priority will be processed before than jobs with lower priority. Highest priority is 1, and lower the larger integer you use. Keep in mind that priority queues are a bit slower than a standard queue (currently insertion time O(n), n being the number of jobs currently waiting in the queue, instead of O(1) for standard queues)
- repeatable
  - Repeatable jobs are special jobs that repeat themselves indefinitely or until a given maximum date or the number of repetitions has been reached, according to a cron specification or a time interval.

