# Docker-Revive-Adserver
## Introduction
The purpose of this small project is to quickly deploy revive-adserver-5.0.0 through docker containers

## Requirements
-**docker** (https://docs.docker.com/engine/installation/linux/debian/)
-**docker-compose** (https://docs.docker.com/compose/install/)

## how to use
**1:** Clone the project and enter the directory
`git clone https://github.com/JimmyBryant/docker-revive-adserver.git`
`cd docker-revive-adserver`

**2:** Execute the following commands to start nginx and mysql containers
`docker-compose up -d`

**3:** Get the IP address of the Mysql container
`docker inspect --format'{{ .NetworkSettings.IPAddress }}' docker-revive-adserver_db_1`

**4:** Visit http://IP[:port] to initialize Revive Adserver, such as my server: http://217.118.67.176:8000

**5:** Accept the terms. Now should display the database connection setup

**6:** Mysql container creates the user revive by default, the initial password is 123456, and an empty database revive5 is created
-**Database Name:revive5**
-**username:** revive
-**password:** 123456
-**hostname:** (Fill in the IP of the Mysql container)

**7:** Start using revive-adserver

## memcached cache
1. First, you need to find out the IP address of the memcached container, and then go to the Plugins option to set the memcached Host of the Banner Delivery Cache Store Plugin, for example, 172.18.0.4:11211
2. Go to Banner Delivery Setting under Configuration option and set Banner Delivery Cache Store Type to memcached


## Deploy to aws
https://docs.aws.amazon.com/AmazonECS/latest/userguide/docker-basics.html
