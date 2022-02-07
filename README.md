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

````
