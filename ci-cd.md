# Prerequisites
===============

- On mac/windows get the IP from the VM **default** : (probably 192.168.99.100)

> docker-machine ip default

Or just grab the container IP under linux host with docker inspect command :

> docker inspect --format '{{ .NetworkSettings.IPAddress }}' jenkins-master

# Nexus 3 container
===================

> docker run -d -p 8081:8081 --name nexus sonatype/nexus3

Wait for 1/2 min for a full start.

URL : http://192.168.99.100:8181

# Jenkins 2
===========

Latest release is 2.0

> docker run --name jenkins-master -p 8080:8080 -p 50000:50000 jenkins:2.0

Note : get the default password on starting logs or get it like this :

> docker exec jenkins-master cat /var/jenkins_home/secrets/initialAdminPassword

URL : http://192.168.99.100:8080
