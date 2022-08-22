<p> Apache Spark is an open-source, general-purpose, multi-language analytics engine for large-scale data processing. It works on both single and multiple nodes by utilizing the RAM in clusters to perform fast data queries on large amounts of data. It offers batch data processing and real-time streaming, with support of high-level APIs in languages such as Python, SQL, Scala, Java or R. The framework offers in-memory technologies that allow it to store queries and data directly in the main memory of the </p>


### Install Java 
		sudo apt update
		sudo apt install default-jdk -y
		java -version

### Install Apache Spark
		sudo apt install curl mlocate git scala -y
		curl -O https://archive.apache.org/dist/spark/spark-3.2.0/spark-3.2.0-bin-hadoop3.2.tgz
		sudo tar xvf spark-3.2.0-bin-hadoop3.2.tgz

### Create an installation directory /opt/spark.
		sudo mkdir /opt/spark

### Move the extracted files to the installation directory.
		sudo mv spark-3.2.0-bin-hadoop3.2/* /opt/spark

### Change the permission of the directory.
		sudo chmod -R 777 /opt/spark

### Edit the bashrc configuration file to add Apache Spark installation directory to the system path.
		sudo nano ~/.bashrc

### Add the code below at the end of the file, save and exit the file:
		export SPARK_HOME=/opt/spark
		export PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin

		source ~/.bashrc

		start-master.sh
### Browse

		URL: spark://my-server-development:7077
