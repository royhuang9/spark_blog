# Spark Blogs
## How to Install Anaconda on CentOS
https://blog.vpscheap.net/how-to-setup-python-anaconda-in-centos/

## How to Access Jupyter notebook remotely. For example on Google Cloud or AWS
### Generate a password for jupyter notebook
```
$ jupyter notebook password
```
Enter your password

### Generate jupyter notebook configuration file
If you don’t already have config file for the notebook, create one using the following command:
```
$ jupyter notebook --generate-config
```
### Endit configuration file
```
# Set ip to '*' to bind on all interfaces (ips) for the public server
c.NotebookApp.ip = '*'
c.NotebookApp.open_browser = False

# It is a good idea to set a known, fixed port for server access
c.NotebookApp.port = 9999
```

### Change the firewall to allow access tcp port 9999
Google it.

## How to Run Scala and Spark in the Jupyter notebook
https://github.com/Valassis-Digital-Media/spylon-kernel

https://medium.com/@bogdan.cojocar/how-to-run-scala-and-spark-in-the-jupyter-notebook-328a80090b3b


# Install single node hadoop and spark
## Install hadoop on single node
https://hadoop.apache.org/docs/stable/hadoop-project-dist/hadoop-common/SingleCluster.html

Configuration file
etc/hadoop/core-site.xml:
```xml
<configuration>
    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
</configuration>
```
etc/hadoop/hdfs-site.xml:

Setup passphraseless ssh

Now check that you can ssh to the localhost without a passphrase:
```
  $ ssh localhost
```
If you cannot ssh to localhost without a passphrase, execute the following commands:
```
  $ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
  $ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
  $ chmod 0600 ~/.ssh/authorized_keys
```

he following instructions are to run a MapReduce job locally. If you want to execute a job on YARN, see YARN on Single Node.

Format the filesystem:
```
  $ bin/hdfs namenode -format
```

Start NameNode daemon and DataNode daemon:
```
    $ sbin/start-dfs.sh
```

The hadoop daemon log output is written to the $HADOOP_LOG_DIR directory (defaults to $HADOOP_HOME/logs).

Browse the web interface for the NameNode; by default it is available at:

NameNode - http://localhost:50070/

## jupyter environment is overwritten after install python3 kernel in jupyter
run "jupyter kernelspec list" to check where it is
