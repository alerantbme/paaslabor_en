# Practice 1. - Docker

## Learn more
[Important information](Tudnivalok.md)
## Help
## Docker commands
```Shell
docker help
docker CMD --help
docker --debug CMD
```

[Key Docker Commands](https://www.cheatography.com/tobix10/cheat-sheets/docker-commands/)

## Useful linux commands
```Shell
brctl show
ifconfig
ip link show
```

### Nginx
/usr/share/nginx/html is the home page
/etc/init.d/nginx stop|start|restart|status 

---

## Task 1. - Basic Docker Operations
** Duration: ~ 15-30 minutes **

### Purpose, description
The purpose of this task is to get to know the most important Docker commands. To do this, use the _docker help_ command to find everything.

1. List the available Docker commands, get to know your help command to find everything easily later. (exec, images, info, inspect, logs, ps, pull, run, search, ...)
2. Look at what images have already been pulled into the local registry.
3. Search for a cirros image and drag to the local repo (This is a lightweight linux).
4. Launch a container made from the previous cirros image
  * Enter into a terminal /bin/sh shell and make sure you are in an isolated container! (search for docker run -it on the net!)
  * Compare running processes in the container and host machine. (ps)
5. Check the following in the running container:
  * What is the container host name?
  * What nameserver is configured?
  * What are the network interfaces?
  * What is the gateway?
  * What IP did you get?
  * What is the routing table? (eg netstat -nr)
6. Run the cirros container and find out in which file in the HOST machine (ie the VirtualBox image) is stored the container /etc/hostname file!

_Hint: these commands will be useful: docker search, docker pull, docker run, docker ps, netstat -nr, docker inspect, etc._
### For the solution report
Copy the answer to the last point in a text file to the report. which docker command you came with!

---


## Task 2. - Docker www server
** Duration: ~ 15 minutes **

### Purpose, description
The purpose of this task is to take advantage of a running container somehow.
The task is to run a web server in Docker container. Opening a Firefox on the host machine at this URL http://localhost should tell you "Hello BME Paas lab!" You may found that port 80 busy, and then select a different port.

Recommended web server: nginx (but can be different)
The following must be resolved:

1. Opening the inner port of the container to the host (_docker run -P_)
2. Observe the status of the container! If you change it, e.g. an index.html file and shut down, will not be there when you start a new container. Why? Can I start a previously modified container (docker ps -a)?
3. (Optional) Possibly solution with volume attachment (docker run -v ...).

_Hint: these commands will be useful: docker run -p, etc._
### For the solution report
Along with the most important commands, there should be a 2-3 sentence description of how you resolved it.

---

## Task 3. - Docker Networks
** Duration: ~ 15 minutes **

### Purpose, description
Run the previous container, which opens port 80 and checks the network operation.

1. Stop all running containers.
2. Check the list of hnetwork interfaces on the host machine.
3. Start with  the container of the former task to open a port on the host.
4. Check your host machine for a list of network interfaces. What has changed?
   - Check the bridges too!
5. Try the docker network inspect command. Notice what containers are connected to the docker0 bridge.
   - You can even launch more containers and see the previous points again.

_Hint: these commands will be useful: docker network, brctl, ifconfig_
### For the solution report
Answer the question in the minutes.

