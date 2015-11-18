# Single Node Hadoop Env
## Step 1 config java env
 see details in https://github.com/LeverNucky/JavaEnv
## Step 2 add new group and new groupuser
````
sudo addgroup hadoop
sudo adduser -ingroup hadoop hadoop
sudo gedit /etc/sudoers
````
In /etc/sudoers add 
hadoop   ALL=(ALL:ALL)  ALL
## Step 3 ssh localhost
first switch to hadoop user
````
ssh-keygen -t rsa -P ""
cd ~/.ssh
cat id_rsa.pub >> authorized_keysp
````
## Step 4 setup hadoop
Download hadoop online, testing version is hadoop-1.2.1
cd download directory
````
sudo tar -zxf hadoop-1.2.1.tar.gz -C /home/hadoop/
cd /home
sudo chown -R hadoop:hadoop hadoop
````
## Step 5 hadoop conf modification
- In conf/hadoop-env.sh（find #export JAVA_HOME=...,delete #,then add your own explicit $JAVA_HOME）;
````
export JAVA_HOME=/usr/lib/jvm/java-sun

````
- replace core-site.xml
- replace mapred-site.xml
- replace hdfs-site.xml
 
 
