Druid Redis Cache
--------------------

# How to use
Just download the Latest release file `druid-redis-cache-0.11.0.tar.gz` and decompress it. There must be three jar files:

* druid-redis-cache-0.11.0.jar
* commons-pool2-2.4.2.jar
* jedis-2.9.0.jar

Copy all these jars into your druid extensions directory. Then, add "druid-example-extension" to druid.extensions.loadList in common.runtime.properties to instruct Druid to load the extension.
More details of loading extensions to your Druid: http://druid.io/docs/latest/operations/including-extensions.html

# Requirement
JDK 1.8 and higher.

# Configuration
Below are the configuration options known to this module:

|`runtime.properties`|Description|Default|
|--------------------|-----------|-------|
|`druid.cache.host`|Redis server host.|none; must be provided|
|`druid.cache.port`|Redis server port.|none; must be provided|
|`druid.cache.expiration`|Expiration(in seconds) for cache entries.|24 * 3600|
|`druid.cache.timeout`|Timeout(in milliseconds) for get cache entries from Redis.|2000|
|`druid.cache.maxTotalConnections`|Max total connections to Redis(This module use JedisPool to connect to Redis).|8|
|`druid.cache.maxIdleConnections`|Max idle connections to Redis.|8|
|`druid.cache.minIdleConnections`|Min idle connections to Redis.|0|

# Metrics
In addition to the normal cache metrics, the redis cache implementation also reports the following in both `total` and `delta`

|Metric|Description|
|------|-----------|
|`query/cache/redis/*/requests`|Count of requests to redis cache|