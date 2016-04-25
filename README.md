# spark_workshop

### Installing Spark

Head over to the Spark download page at http://spark.apache.org/downloads.html .

The Spark download page offers the possibility to download earlier versions of Spark and different package and download types. We will select the latest release, pre-built for Hadoop 2.6 and later. The easiest way to install Spark is to use a Spark package prebuilt for Hadoop 2.6 and later, rather than build it from source. Move the file to the directory ~/spark under the root directory.

Download the latest release of Spark—Spark 1.5.2, released on November 9, 2015:

1. Select Spark release 1.5.2 (Nov 09 2015)
2. Chose the package type Prebuilt for Hadoop 2.6 and later
3. Chose the download type Direct Download
4. Download Spark: spark-1.5.2-bin-hadoop2.6.tgz
5. Verify this release using the 1.3.0 signatures and checksums

This can also be accomplished by running:

```
# download spark
$ wget http://d3kbcqa49mib13.cloudfront.net/spark-1.5.2-bin-hadoop2.6.tgz
```

Next, we'll extract the files and clean up:

```
# extract, clean up, move the unzipped files under the spark directory
$ tar -xf spark-1.5.2-bin-hadoop2.6.tgz
$ rm spark-1.5.2-bin-hadoop2.6.tgz
$ sudo mv spark-* spark
```

Now, we can run the Spark Python interpreter with:

```
# run spark
$ cd ~/spark
./bin/pyspark
```

You should see something like this:

```
Welcome to
____
/ __/__
__
___ _____/ /__
_\ \/ _ \/ _ `/ __/
'_/
/__ / .__/\_,_/_/ /_/\_\
version 1.5.2
/_/
Using Python version 2.7.6 (default, Mar 22 2014 22:59:56)
SparkContext available as sc.
>>>
The interpreter will have already provided us with a Spark context object, sc ,
which we can see by running:
>>> print(sc)
<pyspark.context.SparkContext object at 0x7f34b61c4e50>
```


## Enabling IPython Notebook
We will work with IPython Notebook for a friendlier user experience than
the console.

You can launch IPython Notebook by using the following command:

```
$ IPYTHON_OPTS="notebook --pylab inline" ./bin/pyspark
```

Launch PySpark with IPYNB in the directory examples/AN_Spark where Jupyter or IPython Notebooks are stored:

```
# cd to /home/an/spark/spark-1.5.0-bin-hadoop2.6/examples/AN_Spark
# launch command using python 2.7 and the spark-csv package:
$ IPYTHON_OPTS='notebook' /home/an/spark/spark-1.5.0-bin-hadoop2.6/bin/pyspark --packages com.databricks:spark-csv_2.11:1.2.0
```

```
# launch command using python 3.4 and the spark-csv package:
$ IPYTHON_OPTS='notebook' PYSPARK_PYTHON=python3 /home/an/spark/spark-1.5.0-bin-hadoop2.6/bin/pyspark --packages com. databricks:spark-csv_2.11:1.2.0
```


## Example files

Assuming you uncompressed spark in  ~/practice/spark, put the previously delivered example files in ~/practice/spark 

Put them in the base path where you uncompressed spark.  The same folder that spark LICENSE file. 	

#### Downloading example Data
 
Browse following URL with your browser 
 
http://www.cim.mcgill.ca/~dudek/206/Logs/AOL­user­ct­collection/ 
 
download ​
aol­data.tar.gz 
 
Uncompress file and position the text files in a folder called ​AOL­user­ct­collection​ inside your spark folder 

#### Launching Environment

```
~/practice/spark$ IPYTHON_OPTS="notebook" ./bin/pyspark 
```

#### Launching practice Example

Open​_2.­ Aol.ipynb 

![Alt text] (https://github.com/yolanda93/spark_workshop/blob/master/Documentation/images/1.png "Usage example")

1.­ Test the example code. Be sure you have adjusted the path where the data files are before executing, if you do not, you would get an error. 

![Alt text] (https://github.com/yolanda93/spark_workshop/blob/master/Documentation/images/3.png "Usage example")

2.­ See how spark partitions the different processes in the console log of the shell where you executed the command

![Alt text] (https://github.com/yolanda93/spark_workshop/blob/master/Documentation/images/4.png "Usage example")

Change the example code, so,  the last table, instead counting group members by Date, counts group members by Anonymous user id. 
 
Use this tutorial for help 

http://nbviewer.jupyter.org/github/jkthompson/pyspark­pictures/blob/master/pyspark­pictures.ipynb 

#### Recommended Readings 

Intro. 
 
Bigtable:A Distributed Storage System for Structured Google, Inc. 
http://static.googleusercontent.com/media/research.google.com/en//archive/bigtable­osdi06.pdf  


MapReduce: Simplied Data Processing on Large Clusters Jeffre y Dean and Sanjay Ghemawat Google, Inc. 
http://static.googleusercontent.com/media/research.google.com/en//archive/mapreduce­-osdi04.pdf 

Parallel Data Processing with MapReduce: A Survey 
http://www.cs.arizona.edu/~bkmoon/papers/sigmodrec11.pdf 

Comparative Study Parallel Join Algorithms for MapReduce environment 
http://www.ispras.ru/proceedings/docs/2012/23/isp_23_2012_285.pdf 

Hadoop 

Hadoop Map Reduce ​
http://hadoop.apache.org/  

The Hadoop Distributed File System (HDFS) 
http://zoo.cs.yale.edu/classes/cs422/2014fa/readings/papers/shvachko10hdfs.pdf 

Spark 

Resilient Distributed Datasets: A Fault­Tolerant Abstraction for In­Memory Cluster Computing 
http://www.cs.princeton.edu/courses/archive/fall11/cos518/papers/spark.pdf 

Fast and Interactive Analytics over Hadoop Data with Spark 
https://www.usenix.org/system/files/login/articles/zaharia.pdf  

Tachyon: Reliable, Memory Speed Storage for Cluster Computing Frameworks 
http://www.cs.berkeley.edu/~haoyuan/papers/2014_socc_tachyon.pdf 

Spark :​ http://spark.apache.org/ 


Ingestion to Apache Kafka

Ingestion: Kafka Connect: 
http://docs.confluent.io/2.0.1/connect/index.html 

Ingestion: Kafka Connect Connectors: 
http://www.confluent.io/developers/connectors 
 
 
Kafka: a Distributed Messaging System for Log Processing 
http://notes.stephenholiday.com/Kafka.pdf 

Confluent Kafka Distribution Documentation 
http://docs.confluent.io/2.0.1/  
 
 
Apache Flume: 
https://blogs.apache.org/flume/entry/flume_ng_architecture 
 
 
http://kafka.apache.org/  
 
Zookeper, distributed config and coordination states. 
 
ZooKeeper: Wait­free coordination for Internet­scale systems 
https://www.usenix.org/legacy/event/usenix10/tech/full_papers/Hunt.pdf 


Hybrid Architectures ­ Batch and Real Time / Streaming 
 
Lambda Architecture: 
http://jameskinley.tumblr.com/post/37398560534/the­lambda­architecture­principles­for 
http://lambda­architecture.net/ 
 
Kappa Architecture: 
https://www.oreilly.com/ideas/questioning­the­lambda­architecture  
 
Real time Querying BlinkDB: Queries with Bounded Errors and Bounded Response Times 
on Very Large Data 
https://www.cs.berkeley.edu/~sameerag/blinkdb_eurosys13.pdf 


Visualization 
 
Matplotlib​: ​
https://github.com/jbmouret/matplotlib_for_papers  
Plotly​; ​https://plot.ly/python/offline/ 
 
Big Data as a Service 
 
Mesos: A Platform for Fine­Grained Resource Sharing in the Data Center 
http://people.csail.mit.edu/matei/papers/2011/nsdi_mesos.pdf  


Networking in Containers and Container Clusters 
http://people.netfilter.org/pablo/netdev0.1/papers/Networking­in­Containers­and­Contain
er­Clusters.pdf  
 
Apache Hadoop YARN: Yet Another Resource Negotiator 
https://sites.google.com/site/2013socc/home/program/a5­vavilapalli.pdf?attredirects=1  
 
The Datacenter as a Computer An Introduction to the Design of Warehouse­Scale Machines 
http://www.morganclaypool.com/doi/pdf/10.2200/S00516ED2V01Y201306CAC024 

Parallel Machine Learning in Spark

Spark MLLib ​: MLlib: Scalable Machine Learning on Spark 
http://stanford.edu/~rezab/sparkworkshop/slides/xiangrui.pdf 


R With Spark​: SparkR Interactive R at scale 
http://files.meetup.com/3138542/SparkR­meetup.pdf  
 
GraphX: Unifying Data­Parallel and Graph­Parallel Analytics 
https://amplab.cs.berkeley.edu/wp­content/uploads/2014/02/graphx.pdf 
 
Graph Databases: 
http://info.neotechnology.com/rs/neotechnology/images/GraphDatabases.pdf  


Bonus: Parallel Deep Learning with Tensor Flow and Spark 
 
TensorFlow: Large­Scale Machine Learning on Heterogeneous Distributed Systems 
http://download.tensorflow.org/paper/whitepaper2015.pdf  
 
VIDEO: Tensor Flow with Spark: Distributed Tensor Flow on Spark: Scaling Google's Deep 
Learning Library 
https://spark­summit.org/east­2016/events/distributed­tensor­flow­on­spark­scaling­googl
es­deep­learning­library/  

More Jupyter Examples. 
 
Not all of them with spark: ​http://nb.bianp.net/sort/views/ 
