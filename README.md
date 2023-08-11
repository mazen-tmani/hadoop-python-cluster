# My Hadoop MapReduce Project
This repository contains the necessary files and instructions for setting up my Hadoop MapReduce project.
# Setting Cluster Nodes 
1. Clone gihub repository 
```bash
git clone https://github.com/mazen-tmani/hadoop-python-cluster
```
2. Create hadoop network
```bash
docker network create --driver=bridge hadoop
``` 
3. Build the image by running image-build.sh script 
```bash
cd hadoop-python-cluster
./image-build.sh
```
4. Start Containers 
```bash
./start-container.sh
```
- Output
```bash
start hadoop-master container...
start hadoop-slave1 container...
start hadoop-slave2 container...
root@hadoop-master:~#
```
- By default, our cluster will start 3 containers : 1 master and 2 slaves
- You will get into the /root directory of hadoop-master container
5. Start hadoop 
```bash
./start-hadoop.sh
```
#Dependencies Installation 
To run this project, you'll need to have the transformers and torch libraries installed. These libraries are not included directly in the Dockerfile to save build time. Instead, you can easily install them on each node of your Hadoop cluster using the following steps:

SSH into each node of your Hadoop cluster.
Run the following commands in each node's terminal:
```bash
pip3 install transformers torch
```
By following these steps, you'll ensure that the necessary dependencies are installed and ready for your MapReduce job.
#Change cluster size 
1. Clone and enter the clones repository 
Do 1 -> 3 like section A
2. Rebuild docker image
```bash
./resize-cluster.sh 4
```
- Specify number > 1 
- This script will rebuilt the hadoop image including new nodes and automatically setting names
3. Start containers
```bash
./start-container.sh 4
```
- Use the same number in step 2
  
