# What it is ?
Worked on high performance distributed computing for Big Data using Hadoop Framework 
A web application to analyze YouTube data which automates setting up Hadoop Clusters via Manual method ( by Setting up of Ip addresses by the users ) and on demand method ( Completely automated by Dockers-users has to just specify the ).

Technologies:
1)Built from scratch on RHEL 7.3
2)Python CGI
3)Hadoop 1
4)Dockers for setting Hadoop cluster.
5)Ivolves configuration of HTTP,SSH,NFS(for mounnting volume to dockers) servers.
6)Web technologies used are HTML ,CSS 

Other Technologies used are Ansible (DevOps) : for configuring the docker cluster together.

# Getting Started
-In order to run Hadoop 1 cluster for Manual method the user has to write ip address of the machines he wants to setup his cluster on. 

-The On-Demand setup which is one-click setup where user has to just fill the following input boxes.
1) No of machines required in the cluster.
2) Replication factor of the data.
and the required cluster is setup on dockers.

# *Prerequisites*
1. Redhat Linux with Jq(for json), ansible, Hadoop and JDk installed .
2. A VG with name 'myvg' of atleast 2Gb in size.
3. Docker setup and latest image of centos:latest can be pulled from "DockerHub"
4. Making a custom image (Install ssh server , Hadoop version 1 and JDk installed inside centos and  commit a new image of this centos with name 'os:v5')
5. Add a hostname and ip in '[web]' in '/etc/ansible/hosts' file
    
# Precaution:
**In ON-demand setup a LV  will be created from 'myvg' VG on the system (let's say main system) whose hostname and ip is set in '/etc/ansible/hosts' file and will be shared to the system where you are setting Docker setup  through NFS server. This will create entry in 'fstab' file of  main system. 
So if you remove th LV, you need to  remove entry from fstab file otherwise your system will be corrupted (but can be repaired ).**

# Note:
This project was not focussed on security implementation or UI interface of the webpages. It's main motive was to implement the concepts and implementation of Hadoop 1 via help of docker including ssh,nfs servers.