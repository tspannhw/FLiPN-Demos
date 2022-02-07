# FLiPN-Demos
Some FLiPN Demos


## Output

* https://www.tweepy.org/



## Input / Output


## Use Cases

### IoT

### Example Run

````


# Scylla Query

select col from pulsar_test_table where key like '%NiFi%' ALLOW FILTERING;


# Spark Table

val dfPulsar = spark.readStream.format("pulsar").option("service.url", "pulsar://localhost:6650").option("admin.url", "http://localhost:8080").option("topic", "persistent://public/default/iotjetsonjson").load()
dfPulsar.printSchema()
val pQuery = dfPulsar.selectExpr("*").writeStream.format("console").option("truncate", "false").start()

pQuery.explain()
pQuery.awaitTermination()
pQuery.stop()

# Flink table

CREATE CATALOG pulsar WITH (
   'type' = 'pulsar',
   'service-url' = 'pulsar://pulsar1:6650',
   'admin-url' = 'http://pulsar1:8080',
   'format' = 'json'
);

USE CATALOG pulsar;

SHOW TABLES;

CREATE TABLE iotjetsonjson
(
  `id` STRING, uuid STRING, ir STRING,
  `end` STRING, lux STRING, gputemp STRING, 
  cputemp STRING, `te` STRING, systemtime STRING, hum STRING,
 memory STRING, gas STRING, pressure STRING, 
 `host` STRING, diskusage STRING, ipaddress STRING, macaddress STRING, 
  gputempf STRING, host_name STRING, camera STRING, filename STRING, 
    `runtime` STRING, cpu STRING,cputempf STRING, imageinput STRING,
    `networktime` STRING, top1 STRING, top1pct STRING, 
  publishTime TIMESTAMP(3) METADATA,
  WATERMARK FOR publishTime AS publishTime - INTERVAL '5' SECOND
) WITH (
  'connector' = 'pulsar',
  'topic' = 'persistent://public/default/iotjetsonjson',
  'value.format' = 'json',
  'scan.startup.mode' = 'earliest',
  'service-url' = 'pulsar://pulsar1:6650',
  'admin-url' = 'http://pulsar1:8080'
);

CREATE TABLE default_catalog.default_database.iotjetsonjson2
(
  publishTime TIMESTAMP(3) METADATA,
  WATERMARK FOR publishTime AS publishTime - INTERVAL '5' SECOND
) WITH (
  'connector' = 'pulsar',
  'topic' = 'persistent://public/default/iotjetsonjson',
  'value.format' = 'json',
  'scan.startup.mode' = 'earliest',
  'service-url' = 'pulsar://pulsar1:6650',
  'admin-url' = 'http://pulsar1:8080'
)
like 'iotjetsonjson';

# Pulsar SQL

select * from pulsar."public/default".iotjetsonjson;

select max(gputempf) as maxgputempf, max(cputemp) as maxcputemp, max(memory) as maxmemory from pulsar."public/default".iotjetsonjson;

select max(gputempf) as maxgputempf, max(cputemp) as maxcputemp, max(memory) as maxmemory, min(gputempf) as mingputempf, count(*) as rowcount, min(cputemp) as mincputemp, min(memory) as minmemory, avg(top1pct) as avgtop1pct, avg(try_cast(gputempf as double)) as avggputempf from pulsar."public/default".iotjetsonjson;


````
