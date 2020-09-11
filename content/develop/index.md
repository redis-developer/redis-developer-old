---
layout: layout.html
title: Develop for Redis
---

<details>
<summary> Using Python
</summary>

The below python code insert a key("foo") with a value("bar") directly to the redis server
Copy the below code and save it in a file called foobar.py

## Pre-requisite

- Ensure that you have Python installed on your system.

```
import redis
# Create connection object
r = redis.StrictRedis(host='localhost', port=6379, db=0, password='redis12#')
# set a value for the foo object
r.set('foo', 'bar')
# retrieve and print the value for the foo object
print(r.get('foo'))
```


Execute the python code

```
python foobar.py
```

</details>

<details><summary>
Using JAVA
</summary>
tbd
</details>
