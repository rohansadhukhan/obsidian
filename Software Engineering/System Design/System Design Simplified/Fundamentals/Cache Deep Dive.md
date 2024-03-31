
what is caching and where cache should be used ?
scenarios 
1. in a social media platform, an user trying 
2. let a server gets multiple request for a single query (eg. get average age)
3. there is one database and multiple servers are hitting the database, we can use multiple cache so servers can hit cache first which reduce load on database server

speed up response time

benefits of cache 
1. save network calls
2. avoid re-computations
3. reduce db load

why can't we replace database with cache ?
1. cache hardware cost >> database hardware cost
2. if we are going to store all data in cache it will be too expensive and response time will also increase (as data size increases)

therefore database has infinite information but the cache has the most relevant information according to the request that will come in future.

we need to predict it, it can be done by 2 important questions
1. when do i make an entry in the cache ?
2. when do i evict data from cache ?

| the way we are load or evict data from cache is called a cache policy | 
| --------------------------------------------------------------- |
cache performance is dependent on the cache policy. there are many cache policy 
1. Least Recently Used (LRU) - most popular, top entries are used most recently and the bottom entries are used in years ago / months ago. so every time in loading a data in cache we evict from bottom and insert from the top.
2. Least Frequently Used (LFU) - 
3. Sliding Window based policy - 

drawbacks
1. inefficient cache policy - every time you query in cache but cache doesn't has the data, then query the database. this increases the response time
2. thrashing - smaller cache size
3. consistency - let server 1 stores cache of some data and server 2 updated the data in the database. so server 1 will response stale data.


where should we place the cache ?
there are some advantages and some disadvantages for placing cache, 

in memory cache in the servers (local cache)

advantages
1. faster
2. easy to implement

disadvantages
1. server size and cache size, can not be scaled independently
2. what if some server fails - cached data will loss
3. what if cached data in different servers are not consistent - for critical data we can not use this


in between server and database (global cache) - distributed global cache (redis), 

advantages
1. accurate - even if a server fails nothing happens as cache is distributed, global and consistent
2. scale independently - we can scale the global cache independently 


what are the benefits of global cache ?

global cache can have multiple nodes (as global cache is distributed), and every nodes has its own key value pairs, which were external services can connect to.

there is 2 ways to handle incoming read requests
1.  the global cache is sharded on the key and there will be a co-ordinator who send a particular request to specific node.
2. the co-ordinator will broadcast the request to all the node, let all the node has the value but not consistent ($node_1$ {id = 1, value = 60}, $node_2$ {id = 1, value = 60}, $node_3$ {id = 1, value = 59}), so co-ordinator will return majority among them. we can also store timestamp and we can evaluate based on timestamp also. ($node_1$ {id=1, value=60, time=10}, $node_2$ {id=1, value=60, time=20}, $node_3$ {id=1, value=59, time=5}), we can say $node_3$ stored older value and we can take latest value from $node_2$ and send back the response.

incoming write requests
1. if the cache is sharded on the key, we can only update in the particular node where the key is stored.
2. new write requests will update the cache in one node and then the node will broadcast to every other node to store updated value. if any node failed to update the value or in-between the broadcast some read request comes it will vote or based on timestamp return the response. in worst case let suppose updated value nodes are failed, so it will return old value store in the node. For this Quorum consistency used, ie. $R + W > N$, where $R$ is when we are reading the value the number of nodes that we are reading the value, $W$ is Number of node absolutely make sure that they written the new value in the cache and $N$ is number of nodes. So we failed the read request after a write request if the condition does not satisfy. This condition must satisfy for every data entry, not for every request.


write policy
when ever a write request comes (from user),
1. we may need to update the database
2. we may need to update the cache
these are determined by write policy for every write requests.

three types of write request can occur
1. create
2. update 
3. delete



