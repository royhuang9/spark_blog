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

```xml
<configuration>
    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
</configuration>
```
