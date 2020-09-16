---
layout: layout.html
title: Java and Redis

description: Develop with Redis & Java

data_101_app:
    - 
      demo: "Connect to Redis: all languages"
      url: "https://github.com/Redislabs-Solution-Architects/redis-connect"
    - 
      demo: "Getting Started with Redis Streams"
      url: "https://github.com/tgrall/redis-streams-101-java"
    - 
      demo: "Getting Started with RediSearch"
      url: "https://github.com/redis-developer/getting-started-redisearch"
    - 
      demo: "Redis Streams & Consumer Groups"
      url: "https://github.com/redis-developer/redis-streams-in-action"
  
data_complete_app: 
    - 
      demo: "Brewdis"
      url: "https://github.com/Redislabs-Solution-Architects/brewdis"
    - 
      demo: "Popup Store"
      url: "https://github.com/RedisTimeSeries/redis-pop-up-store"
    - 
      demo: "Microservices with Redis"
      url: "https://github.com/tgrall/redis-microservices-demo"

---


# Develop with Redis & Java


<div class="d-flex justify-content-center">
<img src="{{ '/images/logo/logo_small.png' | url }}" width="80"" /> <span style="font-size:50px">+<span> 
<img src="{{ '/images/logo/java.png' | url }}" width="80"> 
</div>


**Getting Started**

<ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" href="#">Jedis</a>
<div>


</div>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Lettuce</a>
  </li>
</ul>


1- Add dependencies to your Maven or Gradle project file:

```xml
<dependency>
    <groupId>redis.clients</groupId>
    <artifactId>jedis</artifactId>
    <version>3.3.0</version>
    <type>jar</type>
    <scope>compile</scope>
</dependency>
```

2- Create a Jedis Pool

```java
JedisPool pool = new JedisPool(new JedisPoolConfig(), "localhost");
```

3- Use the pool in your application

```java
/// Jedis implements Closeable. Hence, the jedis instance will be auto-closed after the last statement.
try (Jedis jedis = pool.getResource()) {
  /// ... do stuff here ... for example
  jedis.set("foo", "bar");
  String foobar = jedis.get("foo");
  jedis.zadd("sose", 0, "car"); jedis.zadd("sose", 0, "bike"); 
  Set<String> sose = jedis.zrange("sose", 0, -1);
}
/// ... when closing your application:
pool.close();
```


---
#### Ecosystem

<div class="row ">
    <div class="col-4 d-flex justify-content-center">
        <img src="{{ '/images/logo/spring-logo.svg' | url }}" height="40">
    </div>
    <div class="col-4 d-flex justify-content-center">
        <img src="{{ '/images/logo/vertx-logo.png' | url }}" height="30"> 
    </div>
    <div class="col-4 d-flex justify-content-center">
        <img src="{{ '/images/logo/quarkus_logo_horizontal_rgb_reverse.svg' | url }}" height="50">
    </div>
</div>

---
#### Demonstrations

<div class="row">
<div class="col-6">
    <div class="h5">
    <img src="{{ '/images/logo/logo_small.png' | url }}" height="25" />
    Redis 101
    </div>
    <ul>
        {% for item in data_101_app %}<li><a href="{{item.url}}" >{{item.demo}}</a></li>{% endfor %}</ul>
</div>              
<div class="col-6">
    <div class="h5">
    <img src="{{ '/images/logo/logo_small.png' | url }}" height="25" />
    Complete Applications
    </div>
    <ul>
    {% for item in data_complete_app %}<li><a href="{{item.url}}" >{{item.demo}}</a></li>{% endfor %}
    </ul>
</div>  
</div>

---
#### Redis University

<div class="row ">
    <div class="col-8 d-flex justify-content-center">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/CmQMdJefTjc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>   
    </div>
    <div class="col-4">
        <h5>Redis for Java Developers</h5>
        A complete Redis development course for the Java programmer.<br>
        <a href="https://university.redislabs.com/register?course_id=course-v1%3Aredislabs%2BRU102J%2B2020_06&enrollment_action=enroll" target="_blank">
        <button class="btn btn-dark">Enroll</button>
        </a>
    </div>
</div>