# Spark Blogs
## How to Install Anaconda on CentOS
https://blog.vpscheap.net/how-to-setup-python-anaconda-in-centos/

## How to Access Jupyter notebook remotely
Access through a ssh tunnule. See another article for accessing directly
https://amber-md.github.io/pytraj/latest/tutorials/remote_jupyter_notebook

The following doesn't work
https://jupyter-notebook.readthedocs.io/en/stable/public_server.html

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
