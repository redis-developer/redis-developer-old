---
layout: layout_content.html
title: Redis Database Creation
---

# How to create a Redis Database 

This page explain the steo by step Redis database creation process for all the different options listed below:



# Cloud

1. You will have to create Redis Cloud account by visiting [link](https://redislabs.com/try-redis-modules-for-free) below. Once you click on “Get Started”, you will receive an email with a link to activate your account and complete your signup process.

[![]({{ '/images/getting_started/recloud.png' | url }})](https://redislabs.com/try-redis-modules-for-free)

2.  Next, you will have to add  Redis Enterprise Cloud Essentials subscription. In the Redis Enterprise Cloud menu, click Subscriptions. At the bottom of the page, click the “+” sign.

![My Image]({{ '/images/getting_started/recloud2.png' | url }} )

3. For the cloud provider, select Amazon AWS


![My Image]({{ '/images/getting_started/recloud3.png' | url }} )

4. For the region where you want to use the subscription, select ap-south-1. Please note that it’s currently available only in the AWS/Mumbai 


![My Image]({{ '/images/getting_started/recloud5.png' | url }} )

5. In the Redis Enterprise Cloud service levels, select the Redis Cloud Essentials 30MB/1 Database level


![My Image]({{ '/images/getting_started/recloud6.png' | url }} )

6. Click Create. After you create a subscription, you can create a database:


7.  Enter a name for the database of your choice

![My Image]({{ '/images/getting_started/recloud7.png' | url }} )


8. Click "Activate" and wait for few seconds till it gets activated. Once fully activated, you will see the database endpoints as shown below:

![My Image]({{ '/images/getting_started/recloud8.png' | url }} )


# Docker

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

![My Image]({{ '/images/getting_started/recloud10.png' | url }} )

- In the Node Configuration settings, enter a cluster FQDN such as cluster.local. Then click Next button.

![My Image]({{ '/images/getting_started/recloud11.png' | url }} )


- Enter your license key, if you have one. If not, click the Next button to use the trial version.

![My Image]({{ '/images/getting_started/recloud12.png' | url }} )

- Enter an email and password for the admin account for the web console.

![My Image]({{ '/images/getting_started/recloud13.png' | url }} )

- These credentials are also used for connections to the REST API.

- Click OK to confirm that you are aware of the replacement of the HTTPS SSL/TLS certificate on the node, and proceed through the browser warning

![My Image]({{ '/images/getting_started/recloud14.png' | url }} )

### Create a database

- Select “redis database” and the “single region” deployment, and click Next.

- Enter a database name such as demodb.

![My Image]({{ '/images/getting_started/recloud16.png' | url }} )

- Click Show advanced options and, in the Endpoint port number, enter 12000 for the port number.If you cannot activate the database because of a memory limitation, make sure that Docker has enough memory allocated in the Advanced section of Docker Settings.

![My Image]({{ '/images/getting_started/recloud18.png' | url }} )

If port 12000 is not available, enter any available port number between 10000 to 19999 and connect to the database with that port number.


The database configuration is shown. When you see a green check mark, the database is activated and ready for you to use.

![My Image]({{ '/images/getting_started/recloud20.png' | url }} )

You now have a Redis database!



# Redis Enterprise


# From Sources




