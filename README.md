# My Hadoop MapReduce Project
This repository contains the necessary files and instructions for setting up my Hadoop MapReduce project.
# Installation
To run this project, you'll need to have the transformers and torch libraries installed. These libraries are not included directly in the Dockerfile to save build time. Instead, you can easily install them on each node of your Hadoop cluster using the following steps:

SSH into each node of your Hadoop cluster.
Run the following commands in each node's terminal:
```bash
pip3 install transformers torch
```
By following these steps, you'll ensure that the necessary dependencies are installed and ready for your MapReduce job.
# Setting Cluster Nodes 
1. Clone gihub repository 
```bash
git clone https://github.com/mazen-tmani/hadoop-python-cluster
```
2. Build the image by running image-build.sh script 
```bash
cd hadoop-python-cluster
./image-build.sh
```
