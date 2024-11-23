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
    ```bash
    docker run -it --name myhadoop -p 9000:9000 -p 2122:2122 -p 50070:50070 -p 50010:50010 -p 50075:50075 -p 50020:50020 -p 50090:50090 -p 8088:8088 -p 8030:8030 -p 8031:8031 -p 8032:8032 -p 8033:8033 -p 8040:8040 -p 8042:8042 -p 8080:8080 -p 8081:8081 -p 10000:10000 -p 9083:9083 suhothayan/hadoop-spark-pig-hive:2.9.2 bash
