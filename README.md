# Ambari Service for Apache Drill

Ambari Service to run and manage Apache Drill. For more information about Apache Drill visit <a href>https://drill.apache.org/</a>

* Requirements
  - RHEL/CENTOS 7.4
  - Ambari 2.X
  - HDP 2.6
  - You need HDFS and Zookeeper up & running on your cluster
    
* Features
  - Allows to install Apache Drill on an Ambari-managed cluster <br>
  - Edit drill-overrides.conf and drill-env.sh via ambari <br>
  - Integration with zookeeper <br>

## Setup

#### 1. Download the Drill Service

```
git clone https://github.com/thyarles/ambari-drill-service.git /var/lib/ambari-server/resources/stacks/HDP/2.6/services/DRILL
```
#### 2. Restart ambari

```
ambari-server restart
```

#### 3. Create the drill directory in hdfs (workaround)

```
sudo -u hdfs hadoop fs -mkdir /user
sudo -u hdfs hadoop fs -mkdir /user/drill
sudo -u hdfs hadoop fs -chown drill:drill /user/drill
```

Note the drill status command will need to get fixed

#### 4. Install Drill in Ambari

Now you can install Drill by clicking on "Add Service" button in Ambari
