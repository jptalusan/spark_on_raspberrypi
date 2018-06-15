# spark_on_raspberrypi
Saving code/configurations for spark on raspberry pi in case i need it again

Follow steps here initially:  
http://nicholaspropes.com/files/documents/2016-09-05-Raspberry-Pi-Hadoop-Setup-v1-%281%29.pdf  

java -version  
java version "1.8.0_65"  
Java(TM) SE Runtime Environment (build 1.8.0_65-b17)  
Java HotSpot(TM) Client VM (build 25.65-b01, mixed mode)  


Troubleshooting:  
sudo rm -rf /hdfs/tmp/  
sudo mkdir -p /hdfs/tmp  
sudo chown hduser:hadoop /hdfs/tmp/  
sudo chmod 750 /hdfs/tmp  
hadoop namenode -format  
  
cp /etc/os-release scripts/  
cp /etc/hosts scripts/  
cp /home/hduser/.local/share/jupyter/kernels/pyspark-python3/kernel.json scripts/  
cp ~/.bashrc scripts/  
cp /opt/hadoop-2.7.1/etc/hadoop/hadoop-env.sh .  
cp /opt/hadoop-2.7.1/etc/hadoop/core-site.xml .  
cp /opt/hadoop-2.7.1/etc/hadoop/hdfs-site.xml .  
cp /opt/hadoop-2.7.1/etc/hadoop/yarn-site.xml .  
cp /opt/hadoop-2.7.1/etc/hadoop/mapred-site.xml .  
cp /opt/hadoop-2.7.1/etc/hadoop/masters .  
cp /opt/hadoop-2.7.1/etc/hadoop/slaves .  


hdfs dfsadmin -safemode leave  
hdfs dfs -mkdir -p /user/hduser/ARBench  
hdfs dfs -copyFromLocal X_train.txt y_train.txt ARBench  
hdfs dfs -copyFromLocal X_test.txt y_test.txt ARBench  
