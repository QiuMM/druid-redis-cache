Druid Redis Cache
--------------------

**THIS WAS MOVED TO <a href="https://github.com/druid-io/druid">DRUID.IO</a> AS PR: https://github.com/druid-io/druid/pull/4615

# How to use

Refer to: http://druid.io/docs/latest/operations/including-extensions.html

# Requirement
JDK 1.8 and higher.

# Configuration
Below are the configuration options known to this module:

|`runtime.properties`|Description|Default|
|--------------------|-----------|-------|
|`druid.cache.host`|Redis server host.|none; must be provided|
|`druid.cache.port`|Redis server port.|none; must be provided|
|`druid.cache.expiration`|Expiration(in milliseconds) for cache entries.|24 * 3600 * 1000|
|`druid.cache.timeout`|Timeout(in milliseconds) for get cache entries from Redis.|2000|
|`druid.cache.maxTotalConnections`|Max total connections to Redis(This module use JedisPool to connect to Redis).|8|
|`druid.cache.maxIdleConnections`|Max idle connections to Redis.|8|
|`druid.cache.minIdleConnections`|Min idle connections to Redis.|0|

# Metrics
In addition to the normal cache metrics, the redis cache implementation also reports the following in both `total` and `delta`

|Metric|Description|
|------|-----------|
|`query/cache/redis/*/requests`|Count of requests to redis cache|
