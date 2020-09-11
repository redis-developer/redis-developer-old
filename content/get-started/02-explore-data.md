---
layout: layout.html
title: Redis Insight
---


# Explore the data

Explore your data with Redis Insight


<details><summary>
1. Connect to Redis
</summary>
<br>
<details><summary> 
Using RedisInsight
</summary>

RedisInsight provides an intuitive and efficient GUI for Redis, allowing you to interact with your databases and manage your data—with built-in support for most popular Redis modules. It provides tools to analyze the memory, profile the performance of your database usage, and guide you toward better Redis usage.
To learn more about RedisInsight: https://redislabs.com/redis-enterprise/redis-insight

## Pre-requisite

Ensure that you have Docker binaries already installed in your system. Run the below command to bring up Docker container to start RedisInsight application services: 

```
$ docker run -v redisinsight:/db -p 8001:8001 redislabs/redisinsight:latest
```

When you run the above command, it will start the RedisInsight applications as shown below:

```
INFO 2020-08-01 19:10:16,255 redisinsight Application version: 1.6.3
INFO 2020-08-01 19:10:16,257 redisinsight First start detected
INFO 2020-08-01 19:10:16,343 redisinsight Created desktop-mode user.
INFO 2020-08-01 19:10:16,346 redisinsight Created installation ID: '02ba76b68cb645ab8151728a9418625c'
INFO 2020-08-01 19:10:16,349 redisinsight Application first start event sent.
INFO:redisinsight:Application first start event sent.
INFO 2020-08-01 19:10:16,351 redisinsight Created application update history entry for version 1.6.3
INFO:redisinsight:Created application update history entry for version 1.6.3
INFO 2020-08-01 19:10:16,353 redisinsight Application startup event sent.
INFO:redisinsight:Application startup event sent.
INFO 2020-08-01 19:10:16,355 redisinsight_startup Starting waitress
INFO:redisinsight_startup:Starting waitress
```

Head over to your web browser and open http://localhost:8001

Congratulations! You have successfully installed RedisInsight and now ready to inspect your Redis data, monitor health, and perform runtime server configuration with a browser-based management interface for your Redis deployment.

Once you accept EULA and click “Confirm”, you are ready to add Redis Databases as shown below:
Choose “Add Database”.

![My Image]({{ '/images/getting_started/recloud301.png' | url  }} )


Enter details like name, host(endpoint), port and password. You can skip username as of now.

![My Image]({{ '/images/getting_started/recloud302.png' | url  }} )

Click “Add Redis Database”.

![My Image]({{ '/images/getting_started/recloud303.png' | url  }} )


Click on the Box and you shall be able to see the RedisInsight dashboard for the first time.

![My Image]({{ '/images/getting_started/recloud304.png' | url  }} )

</details>

<details><summary>
- Using RedisCLI
</summary>

## Pre-requisite

Ensure that Redis CLI client software is installed by using the below command:

Run the below command to connect to Redis database


redis-cli -h <host> -p <port>


```
% redis-cli -h 192.168.43.160 
192.168.43.160:6379> info server
# Server
redis_version:6.0.1
redis_git_sha1:00000000
redis_git_dirty:0
redis_build_id:5ca5d79ba0098212
redis_mode:standalone
os:Linux 4.19.76-linuxkit x86_64
arch_bits:64
multiplexing_api:epoll
atomicvar_api:atomic-builtin
gcc_version:8.3.0
process_id:1
run_id:5d5a9ab7448d40d7b37749b6d1b2172ddea57b07
tcp_port:6379
uptime_in_seconds:6900
uptime_in_days:0
hz:10
configured_hz:10
lru_clock:5985991
executable:/data/redis-server
config_file:
```
</details>
<br>
<details><summary>
2. Import a Dataset
</summary>
</details>

