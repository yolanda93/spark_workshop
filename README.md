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

# run spark
$ cd ~/spark
./bin/pyspark

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