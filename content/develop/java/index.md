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

Java developers have the choice between various clients to use Redis, the main ones are Jedis and Lettuce, and you can find more in the [Redis Client Page](https://redis.io/clients#java).

The following content shows how to get started with Jedis and Lettuce. [Guy Royse](https://github.com/guyroyse) has written a [blog post that explores the differences between these two clients](https://redislabs.com/blog/jedis-vs-lettuce-an-exploration/), and when to use one or the other.

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

<!-- HTML generated using hilite.me --><div style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;"><pre style="margin: 0; line-height: 125%"><span style="color: #007700">&lt;dependency&gt;</span>
<span style="color: #007700">  &lt;groupId&gt;</span>redis.clients<span style="color: #007700">&lt;/groupId&gt;</span>
<span style="color: #007700">  &lt;artifactId&gt;</span>jedis<span style="color: #007700">&lt;/artifactId&gt;</span>
<span style="color: #007700">  &lt;version&gt;</span>3.3.0<span style="color: #007700">&lt;/version&gt;</span>
<span style="color: #007700">  &lt;type&gt;</span>jar<span style="color: #007700">&lt;/type&gt;</span>
<span style="color: #007700">  &lt;scope&gt;</span>compile<span style="color: #007700">&lt;/scope&gt;</span>
<span style="color: #007700">&lt;/dependency&gt;</span>
</pre></div>


2- Create a Jedis Pool

<!-- HTML generated using hilite.me --><div style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;"><pre style="margin: 0; line-height: 125%">JedisPool pool <span style="color: #333333">=</span> <span style="color: #008800; font-weight: bold">new</span> JedisPool<span style="color: #333333">(</span><span style="color: #008800; font-weight: bold">new</span> JedisPoolConfig<span style="color: #333333">(),</span> <span style="background-color: #fff0f0">&quot;localhost&quot;</span><span style="color: #333333">,</span> <span style="color: #0000DD; font-weight: bold">6379</span><span style="color: #333333">);</span>
</pre></div>



3- Use the pool in your application

<!-- HTML generated using hilite.me --><div style="background: #ffffff; overflow:auto;width:auto;border:solid gray;border-width:.1em .1em .1em .8em;padding:.2em .6em;"><pre style="margin: 0; line-height: 125%"><span style="color: #888888">/// Jedis implements Closeable. Hence, the jedis instance will be auto-closed after the last statement.</span>
<span style="color: #008800; font-weight: bold">try</span> <span style="color: #333333">(</span>Jedis jedis <span style="color: #333333">=</span> pool<span style="color: #333333">.</span><span style="color: #0000CC">getResource</span><span style="color: #333333">())</span> <span style="color: #333333">{</span>
  <span style="color: #888888">/// ... do stuff here ... for example</span>
  jedis<span style="color: #333333">.</span><span style="color: #0000CC">set</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;foo&quot;</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;bar&quot;</span><span style="color: #333333">);</span>
  String foobar <span style="color: #333333">=</span> jedis<span style="color: #333333">.</span><span style="color: #0000CC">get</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;foo&quot;</span><span style="color: #333333">);</span>
  jedis<span style="color: #333333">.</span><span style="color: #0000CC">zadd</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;sose&quot;</span><span style="color: #333333">,</span> <span style="color: #0000DD; font-weight: bold">0</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;car&quot;</span><span style="color: #333333">);</span> jedis<span style="color: #333333">.</span><span style="color: #0000CC">zadd</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;sose&quot;</span><span style="color: #333333">,</span> <span style="color: #0000DD; font-weight: bold">0</span><span style="color: #333333">,</span> <span style="background-color: #fff0f0">&quot;bike&quot;</span><span style="color: #333333">);</span> 
  Set<span style="color: #333333">&lt;</span>String<span style="color: #333333">&gt;</span> sose <span style="color: #333333">=</span> jedis<span style="color: #333333">.</span><span style="color: #0000CC">zrange</span><span style="color: #333333">(</span><span style="background-color: #fff0f0">&quot;sose&quot;</span><span style="color: #333333">,</span> <span style="color: #0000DD; font-weight: bold">0</span><span style="color: #333333">,</span> <span style="color: #333333">-</span><span style="color: #0000DD; font-weight: bold">1</span><span style="color: #333333">);</span>
<span style="color: #333333">}</span>
<span style="color: #888888">/// ... when closing your application:</span>
pool<span style="color: #333333">.</span><span style="color: #0000CC">close</span><span style="color: #333333">();</span>
</pre></div>


Find more information about Java client & Redis connection in the **"[Redis Connect](https://github.com/Redislabs-Solution-Architects/redis-connect/tree/master/java)"** project.

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