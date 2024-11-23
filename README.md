# BIGDATA
Complete setup of Big data


# Hadoop Installation Guide

## Introduction
This guide will walk you through the process of setting up Hadoop on Docker, covering both Windows and Mac (Apple M1, M2, M3 chip) users. Follow these steps to ensure a successful installation.

---

### :computer: **Prerequisites**
- Ensure Docker is installed and running on your system.
- Have an active internet connection to download necessary Docker images.

---

## :gear: **Installation Steps**

### **Windows Users**
1. **Open Command Prompt and Pull the Docker Image**
   ```bash
   docker pull suhothayan/hadoop-spark-pig-hive:2.9.2

⚠️ If the download freezes, cancel it by pressing Ctrl + C, switch your network, and try again.

Wait until the download is finished

Execute this Docker command in the same window where you have pulled the image:

    docker run -it --name myhadoop -p 9000:9000 -p 2122:2122 -p 50070:50070 -p 50010:50010 -p 50075:50075 -p 50020:50020 -p 50090:50090 -p 8088:8088 -p 8030:8030 -p 8031:8031 -p 8032:8032 -p 8033:8033 -p 8040:8040 -p 8042:8042 -p 8080:8080 -p 8081:8081 -p 10000:10000 -p 9083:9083 suhothayan/hadoop-spark-pig-hive:2.9.2 bash
### **Mac Users (Apple Chip M1, M2, M3)**
1. Open a Terminal and pull the image:

      docker pull bugbond/hadoop-spark-pig-hive-arm64

2. Run the services:

      docker run -it --name bigtools -p 9000:9000 -p 2122:2122 -p 50070:50070 -p 50010:50010 -p 50075:50075 -p 50020:50020 -p 50090:50090 -p 8088:8088 -p 8030:8030 -p 8031:8031 -p 8032:8032 -p 8033:8033 -p 8040:8040 -p 8042:8042 -p 8080:8080 -p 8081:8081 -p 10000:10000 -p 9083:9083 bugbond/hadoop-spark-pig-hive-arm64:latest bash


### **:wrench: Troubleshooting**
Error: Ports are not available on Windows
Fix: Open a Terminal (must be run as administrator) and execute:
```bash
net stop winnat
```

Error: The container name "/myhadoop" is already in use
Fix: Remove the container using Docker Desktop and re-run the docker run command.


### **:book: Port Number Explained**
1. 2122: SSH
2. 50070: HDFS NameNode
3. 50010: HDFS DataNode
4. 50075: HDFS DataNode
5. 50020: SecondaryNameNode
6. 50090: HDFS DataNode Secure
7. 8088: YARN ResourceManager
8. 8030, 8031, 8032, 8033: YARN ResourceManager Scheduler
9. 8040, 8042: YARN NodeManager
10. 8080: Spark Master Web UI
11. 8081: Spark Worker Web UI
12. 10000: HiveServer2

### **:repeat: Re-run Existing Container**
To access your previous work in an existing Hadoop container, use:

```bash

docker exec -it myhadoop bash
```
### **:earth_americas: Accessing Web Interfaces**
Hadoop Web Interface: http://localhost:50070

Spark Web Interface: http://localhost:8080

### **:memo: Update and Install Tools in Ubuntu**
1. Update Ubuntu:

```bash

apt update
```
2. Install nano editor:

```bash

apt install nano
```
3. Verify Hadoop Installation:

```bash

ls /usr/local/hadoop
```
### **:gear: Set Up Environment Variables**
1. Open your ~/.bashrc for editing:

```bash

nano ~/.bashrc
```
2. Add the following lines to set up environment variables:

```bash
export HADOOP_HOME=/usr/local/hadoop
export HADOOP_CONF_DIR=$HADOOP_HOME/etc/hadoop
export PATH=$PATH:$HADOOP_HOME/bin:$HADOOP_HOME/sbin
```
3. Reload the ~/.bashrc settings:

```bash

source ~/.bashrc
```

# Note: If Hadoop stops working for any reason, restart it using:
```bash
stop-dfs.sh
stop-yarn.sh
start-dfs.sh
start-yarn.sh
```
Navigate to the home directory and continue with your Hadoop tasks:

```bash
cd home
```

### **:file_folder: Data Handling in Hadoop**
1. Create a new directory:

```bash
mkdir datasrc
```

2. Upload the dataset to HDFS:

```bash
hadoop fs -mkdir -p /home/datasrc/bigDataTask
hadoop fs -put Books_rating.csv /home/datasrc/bigDataTask
```
3. Verify the file upload:
```bash
hadoop fs -ls /home/datasrc/bigDataTask
```
