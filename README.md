# BIGDATA
Complete setup of Big data


# Hadoop Installation Guide

This guide provides step-by-step instructions to install Hadoop on Docker, including setups for different platforms and troubleshooting common issues.

## 📋 Prerequisites

- Docker must be installed and running on your machine.
- Ensure you have a stable internet connection.

## 🚀 Installation Steps

### **Windows Users**

**1. Open Docker:**
Ensure Docker Engine is running.

**2. Pull the Docker Image:**

```bash
docker pull suhothayan/hadoop-spark-pig-hive:2.9.2



**⚠️ Note: If the download freezes, cancel it with Ctrl + C, switch your network, and try again.**

3. Run the Docker Image:
docker run -it --name myhadoop -p 9000:9000 -p 2122:2122 -p 50070:50070 -p 50010:50010 -p 50075:50075 -p 50020:50020 -p 50090:50090 -p 8088:8088 -p 8030:8030 -p 8031:8031 -p 8032:8032 -p 8033:8033 -p 8040:8040 -p 8042:8042 -p 8080:8080 -p 8081:8081 -p 10000:10000 -p 9083:9083 suhothayan/hadoop-spark-pig-hive:2.9.2 bash
