
# Exercise 2. - OpenShift Overview

## Learn more
[Important information](Tudnivalok.md)

**Important:**
- Local OpenShift can be used on your virtual machines!
_sudo systemctl status openshift_ to see if it is running.

- OpenShift Conventions if you use central OpenShift:
  - Username: studentxy - where x y is the initials of your names eg studentnz (lowercase)
  - Project names: practiceNxy - N number of practice, x, y lsd. first, eg practice2nz (lowercase)
- Everyone uses your own user to work separately!


## Installed OpenShift Overview - Leaded Tutorial
### Dashboard
- Login / Exit
- Create a new project (project name is unique!)
  - Javascript example selection, Node.js
  - Selecting TryIt Git sample
  - Advanced Parts Overview
- Build process
- Deployment process
- Deployment Config
- Pods (build and app)

_Further documentation: https://docs.openshift.org/latest/welcome/index.html_






### oc CLI, main components
```shell
 oc login https://bmepaas-master.openshift.local:8443    
#or locally 
oc login -u system:admin
```


Nodes:
```shell
oc get nodes
NAME                             STATUS                     AGE
bmepaas-master.openshift.local   Ready,SchedulingDisabled   2d
bmepaas-node1.openshift.local    Ready                      2d
bmepaas-node2.openshift.local    Ready                      2d
```
_No pod to the master node (SchedulingDisabled)_

Services:
```shell
oc get services
NAME               CLUSTER-IP       EXTERNAL-IP   PORT(S)                   AGE
docker-registry    172.30.238.160   <none>        5000/TCP                  2d
kubernetes         172.30.0.1       <none>        443/TCP,53/UDP,53/TCP     2d
registry-console   172.30.8.163     <none>        9000/TCP                  2d
router             172.30.117.243   <none>        80/TCP,443/TCP,1936/TCP   2d
```

Built in Pods:
```shell
oc get pods
NAME                       READY     STATUS    RESTARTS   AGE
docker-registry-2-8ejuy    1/1       Running   1          2d
registry-console-1-63wqa   1/1       Running   1          2d
router-1-2wth4             1/1       Running   1          2d
router-1-wksfx             1/1       Running   1          2d

oc adm manage-node bmepaas-node1.openshift.local --list-pods
Listing matched pods on node: bmepaas-node1.openshift.local
NAME                       READY     STATUS    RESTARTS   AGE
registry-console-1-63wqa   1/1       Running   1          2d
router-1-wksfx             1/1       Running   1          2d

```

## Help

### The CLI commands required for tasks:
```shell
oc help
oc login -u system:admin
oc new-project
oc whoami
oc status
oc describe
oc new-app
```

## Task 1. - Install PaaS Sample Application
** Duration: 30 minutes **

### Purpose, description
The purpose of this task is to try out PaaS. Create a sample application within your projects (you can choose technology from the dashboard).
 
Recommended sample: NodeJS or Java
Go through the following and collect the marked data for the minutes:

1. Create an application with your own user account on the Dashboard. Check out the selected Git project on the github link. It is worth checking out, understanding what will compile and deploy.
2. Follow the installation process. Build logs worth checking out.
3. Check to see if the application is running from your browser and it works!
4. Look at the Dashboard based on the tutorial to see what has been created, what information you have.
5. Also look at the project, the POD, the service with oc CLI.
6. Find out what the container id is for the application, ie what running Docker container is running in the application?

_Hint: these commands will be useful: oc new-app, oc get pods, oc get svc, oc describe pod etc.

### For Protocol
Write down the result of point 6 and how you discovered it.
