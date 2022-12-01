# Real-Time Case Study Project Setup

### Prerequisite

1. Install Python3
2. Install MySQL
3. Install Apache Hadoop
4. Install Apache Spark
5. Install Apache Kafka



### Create MySQL database

> mysql -u root -p
> create database realtime_data_processing;
> show databases;
> exit;

### Run Real-Time Dashboard Application

> folder: realtime_charts
> python manage.py runserver
> Access Real-Time Dashboard Application using below url
> http://127.0.0.1:8000/

### Run Kafka Producer Application(Stream data simulator)

folder: kafka_producer_consumer

python kafka_producer.py

### Run Data Processing Pipeline application(Spark Streaming)

folder: realtime_data_processing

spark-submit --master local[*] --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.3.0,mysql:mysql-connector-java:5.1.49 --files ./realtime_app.conf ./realtime_data_processing.py

Keep monitoring the real-time dashboard using below url,

http://127.0.0.1:8000/
