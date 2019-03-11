# Knowledge

## VirtualBox Import

For home work, to complete the exercises, the virtual machine can be downloaded here (from BME network): 
curl -L0 http://ossrv1.aut.bme.hu/alerantbme_paaslabor_student_2019.ova

You also have it on the desktop at C:\VPCImages\PAAS\alerantbme_paaslabor_student_2019.ova

### Delete previous virtual machine
Carefully, avoid erasing other virtual machines!

1. At the workstation , open VirtualBox, select AlerantBME_CentOS7: Delete , Delete all 
2. In VirtualBox-> File-> Virtual Media Manager, check that the AlerantBME_CentOS7 disk does not exist, if it is there, delete it.

### Importing a virtual machine
1. Create the C:\Work\VirtualBox directory (if there is, but there is no others virtual machine in it, delete it all)
2. In VirtualBox:
- Check File-> Preferences-> General-> Default Machine (File-> Preferences-> General-> Default Machine Folder) Folder: C:\Work\VirtualBox
- Import Appliance: C:\VPCImages\PAAS\alerantbme_paaslabor_student_2019.ova
- At the last step of the wizard, check if a good path has been entered

## VirtualBox CentOS Information
- Start the CentOS image in VirtualBox and work on it!
- CentOS Login: ** BME Paas user,password: paaslabor **
- sudo can be used (carefully :))
- if you need some package on Linux: sudo yum install -y XXXXXXXX
- mount host host directory:
    1. Create a folder in Devices / Shared Folders in VirtualBox. Name it "host".
    2. Then you can mount it in CentOS: sudo mount -t vboxsf host /media ("host" is the share name)
- Firefox is the browser
- You should set the bidirectional clipboard in VirtualBox to make copy-paste work
- status and restart of services such as sudo systemctl restart NetworkManager
- Make a working directory for yourself and work on it

## GitHub

Everyone must create a GitHub account or use an existing one!

1. https://github.com/
2. Sign Up
3. username example: alerantbmexy, etc..., you need to confirm your registration via email
4. Create a new project with GitHub start project, e.g. practice2

You can work in the ~/git directory in the CentOS image (there will be more projects)

Git Important Commands:
``Shell
echo "# gyakorlat2" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/alerantbmexy/practice2.git
git push -u origin master
```

Here's how to clone examples in practice:
``Shell
Example # Cloning Java OpenShift Wildfly Application
git clone https://github.com/bparees/openshift-jee-sample practice2
git pull https://github.com/bparees/openshift-jee-sample practice2

# Do not place it back in the original location, but under your own user
git remote set-url origin https://github.com/alerantbmenz/practice2.git

# modifications
git commit -a -m 'Some commit message'
# upload to the new location under our own account
git push origin master
```
You can now create a new project on your own code base based on your own GitHub URL.

Such is the directory structure:

``Shell

[bmepaasuser @ localhost ~] $ tree git /
git/
└── practice2
    ├── pom.xml
    ├── README.md
    └── src
        └── main
            ├── java
            ├── resources
            └── webapp
                ├── images
                │ └── jbosscorp_logo.png
                ├── index.html
                └── snoop.jsp

```


## DNS and hosts file
- Openhift application core components are basically available with IP, but FQDNs are included in the /etc/hosts file
- Dnsmasqd is also installed on the machines, which also works with wildcard DNA, eg. XXX.apps.openshift.local also resolves to the correct IP

dnsmasq config file: /etc/NetworkManager/dnsmasq.d

## IPs
``Shell
192.168.30.11 bmepaas-master.openshift.local
192.168.30.12 bmepaas-node1.openshift.local
192.168.30.13 bmepaas-node2.openshift.local
```


## References

## Docker 
- There are Docker images on the local machine, use them and do not download new ones!

## OpenShift 
- Central OpenShift dashboard: https://bmepas-master.openshift.local:8443
- Starting local OpenShift: sudo systemctl start openshift

## Solution Document

** Collect materials for the report continuously, when, what you do, to have all the information at the time of filling. **

# How can I try out at home?
On Linux is a simpler, but other platforms also work!
## Virtual Machine
You can also take with you the virtual machine that is used in practice!
## Docker
- Install and play with it, on Linux via the package manager or [from](https://store.docker.com/search?offering=community&type=edition) 
- Or play with [online](http://training.play-with-docker.com/)!
## Kubernetes
- Native Kubernetes installation on Linux
- [Minicube](https://github.com/kubernetes/minikube)
## Openshift
- oc cluster up [here](https://www.okd.io/)
- [Minishift](https://github.com/minishift/minishift)
## Openshift course
- https://learn.openshift.com

## Useful links, blogs
- https://github.com/veggiemonk/awesome-docker
- http://www.opensourcerers.org/tag/openshift/
- http://training.play-with-docker.com/
- https://learn.openshift.com
