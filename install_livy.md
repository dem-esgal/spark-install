// Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
sudo apt-get update
apt-cache policy docker-ce
sudo apt-get install -y docker-ce
sudo systemctl status docker
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-16-04

2)
# cd /usr/local/src && wget -qO- https://get.docker.com/ | sh

Минихадуп
docker pull cloudera/quickstart:latest

docker run --hostname=quickstart.cloudera --privileged=true -itd -p 8888:8888 -p 7180:7180 --name demixer/minihadoop /usr/bin/docker-quickstart

3)
install scala

install anaconda 3

https://github.com/dem-esgal/spark-install

pip install py4j
pip install pyspark

check pi

sudo bash ~/livy/bin/livy-server

.bashrc:
export PATH="~/anaconda3/bin:$PATH"
export SPARK_HOME=/usr/local/spark
export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH

export HADOOP_HOME=/usr/local/hadoop
export LD_LIBRARY_PATH=$HADOOP_HOME/lib/native/:$LD_LIBRARY_PATH

export SPARK_HOME=/usr/local/spark
export HADOOP_CONF_DIR=/usr/local/hadoop/conf

// hadoop
https://malderhout.wordpress.com/2014/08/22/install-single-node-hadoop-on-centos-7-in-5-simple-steps/
# disable ipv6
net.ipv6.conf.all.disable_ipv6 = 1
net.ipv6.conf.default.disable_ipv6 = 1
net.ipv6.conf.lo.disable_ipv6 = 1

PATH="$PATH:/usr/local/hadoop/sbin"
export JAVA_HOME=/usr/lib/jvm/java-8-oracle/
(+ to etc/environment)
sudo cp /usr/local/hadoop-2.7.4/etc/hadoop/*.xml ~/conf
sudo cp ~/conf/* /usr/local/hadoop-2.7.4/conf/
add logs directory
iptables -A INPUT -p tcp --dport 50070 -j ACCEPT
export HADOOP_INSTALL=$HADOOP_HOME
export HADOOP_MAPRED_HOME=$HADOOP_HOME
export HADOOP_COMMON_HOME=$HADOOP_HOME
export HADOOP_HDFS_HOME=$HADOOP_HOME
export HADOOP_YARN_HOME=$HADOOP_HOME
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native
export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin
//end
Livy 0.4
just run as bash livy-server
create logs folder with rights

//https://stackoverflow.com/questions/32711804/running-pyspark-with-dependency-package-like-numpy-pandas-and-scikit-learn

pip install elasticsearch 

//разрешить запуск
nohup ~/livy/bin/livy-server &

chmod 0666 /etc/resolv.conf

etc/resolv.conf (или /etc/resolvconf/resolv.conf.d/head)
nameserver 8.8.8.8

// Run scikit-learn + jupiter
conda install -c anaconda scikit-learn 
jupyter notebook --no-browser --ip 0.0.0.0 --port 8888
nohup jupyter notebook --no-browser --ip 0.0.0.0 --port 8888 &
tail -f nohup.out &