---
layout: layout_content.html
title: Redis Database Creation
---

# DB Creation

This page explain the db creation process.


## Cloud

1. You will have to create Redis Cloud account by visiting [link](https://redislabs.com/try-redis-modules-for-free) below. Once you click on “Get Started”, you will receive an email with a link to activate your account and complete your signup process.

[![](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud.png)](https://redislabs.com/try-redis-modules-for-free)

2.  Next, you will have to add  Redis Enterprise Cloud Essentials subscription. In the Redis Enterprise Cloud menu, click Subscriptions. At the bottom of the page, click the “+” sign.

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud2.png)

3. For the cloud provider, select Amazon AWS


![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud4.png)

4. For the region where you want to use the subscription, select ap-south-1. Please note that it’s currently available only in the AWS/Mumbai 


![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud5.png)

5. In the Redis Enterprise Cloud service levels, select the Redis Cloud Essentials 30MB/1 Database level


![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud6.png)

6. Click Create. After you create a subscription, you can create a database:


7.  Enter a name for the database of your choice

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud7.png)


8. Click "Activate" and wait for few seconds till it gets activated. Once fully activated, you will see the database endpoints as shown below:

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud8.png)


## Docker

### Install Docker Engine

Go to the Docker installation page for your operating system for detailed instructions about installing Docker Engine:

### Linux (Ubuntu/Debian)

```
curl -fsSL https://get.docker.com/ | sh
```

### MacOS 

Refer https://docs.docker.com/docker-for-mac/install/ to install Docker Desktop for Mac.

### Run the container

To pull and start the Redis Enterprise Software Docker container, run this docker run command in the terminal or command-line for your operating system.

Note: On Windows, make sure Docker is configured to run Linux-based containers.

```
docker run -d --cap-add sys_resource --name rp -p 8443:8443 -p 9443:9443 -p 12000:12000 redislabs/redis
```

The Docker container with RS runs on your localhost with port 8443 open for HTTPS connections, 9443 for REST API connections, and port 12000 open for redis client connections. You can publish other ports with -p <host_port>:<container_port>.

### Set up a cluster

In the web browser on the host machine, go to https://localhost:8443 to see the Redis Enterprise Software web console.

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud10.png)

- In the Node Configuration settings, enter a cluster FQDN such as cluster.local. Then click Next button.

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud11.png)


- Enter your license key, if you have one. If not, click the Next button to use the trial version.

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud12.png)

- Enter an email and password for the admin account for the web console.

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud13.png)

- These credentials are also used for connections to the REST API.

- Click OK to confirm that you are aware of the replacement of the HTTPS SSL/TLS certificate on the node, and proceed through the browser warning

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud14.png)

### Create a database

- Select “redis database” and the “single region” deployment, and click Next.

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud15.png)

- Enter a database name such as demodb.

![My Image](https://github.com/ajeetraina/redis-developer/blob/master/content/get-started/images/recloud16.png)

- Click Show advanced options and, in the Endpoint port number, enter 12000 for the port number.

If port 12000 is not available, enter any available port number between 10000 to 19999 and connect to the database with that port number.


The database configuration is shown. When you see a green check mark, the database is activated and ready for you to use.

You now have a Redis database!



##

Redis Enterprise


## From Sources




