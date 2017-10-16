# ambari-drill-service
Ambari service for Apache Drill

Ambari service to run and manage Apache Drill. For more information about Apache Drill visit <a href>https://drill.apache.org/</a>

  Requirements: <br>
    - RHEL/CENTOS 7.1 <br>
    - Ambari 2.X <br>
    - HDP 2.6 <br>
    - You need HDFS and Zookeeper up & running on your cluster
    
  Features: <br>
    - Allows to install Apache Drill on an Ambari-managed cluster <br>
    - Edit drill-overrides.conf and drill-env.sh via ambari <br>
    - Integration with zookeeper <br>

### Setup

Download the Drill Service:
<code>
git clone https://github.com/thyarles/ambari-drill-service.git /var/lib/ambari-server/resources/stacks/HDP/2.6/services/DRILL 
</code>

Restart ambari
<code>
ambari-server restart
</code>

Create the drill directory in hdfs (workaround)

```
sudo -u hdfs hadoop fs -mkdir /user
sudo -u hdfs hadoop fs -mkdir /user/drill
sudo -u hdfs hadoop fs -chown drill:drill /user/drill
```

Note the drill status command will need to get fixed

Now you can install Drill by clicking on "Add Service" button in Ambari
