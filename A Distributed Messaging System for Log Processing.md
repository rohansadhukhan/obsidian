
Log are typically includes
1. user activity, includes login, page view, clicks, likes, share, comment, search query, etc.
2. operational metrics, includes service call stack, call latency, errors, system metrics like CPU, memory, network or disk utilisation

Why we need log data ?
These are used for analytics to track user engagement, system utilisation etc.
Also, search relevance, recommendation (which may be driven  by item popularity or occurrence in user activity), ad targeting, security application, news feed.

Problem ?

| Log Data >> Real Data    | 
| --- |
eg. recommendations, advertising require computing granular click through rates, which generate log records for every user click and also every items on each page that are not clicked. Facebook gather around $\approx 6TB$ of user activity event daily.


Solution ?

recent days distributed log aggregator are built, Scribe (Facebook), Data Highway (Yahoo), Flume (Cloudera)

objective of these software is to collect and load log data into a data warehouse or hadoop for offline consumption.

New Requirement
LinkedIn -> addition to traditional offline analytics, it needed to support most of the real-time applications mentioned above with delays of no more than a few seconds.

Kafka 
1. Distributed, scalable and offers high throughput
2. provide api similar to a messaging system and allow application to consume logs in real time


Existing log aggregator's limitations (Need)

1. Those systems often focus on offering a rich set of delivery guarantees.
2. many systems do not focus as strongly on throughput as their primary design constraint. eg. Java Message Service (JMS) has no API to allow the producer to explicitly batch multiple messages into a single request. This means each message requires a full TCP/IP roundtrip
3. systems are weak in distributed support
4. many messaging systems assume near immediate consumption of messages, so the queue of unconsumed messages is always fairly small
5. some are push model




