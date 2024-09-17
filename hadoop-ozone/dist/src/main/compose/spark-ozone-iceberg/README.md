This demonstrates a complete warehouse cluster with dockerized Apache Spark, Apache Iceberg and Apache Ozone configured with s3:// storage protocol, with Spark also running as a Thriftserver and accepting JDBC connections.

- Download and unzip Apache Ozone from Apache Downloads folder https://ozone.apache.org/downloads/ into a folder called ozone
- Place the contents of this folder into ozone/compose/spark-ozone-iceberg folder
- Once in the directory, run the command `OZONE_DATANODES=3 ./run.sh -d`. 
- This will use Docker Dompose to start the  ozone cluster with 3 datanodes for testing purposes. In addition to that, it will also start a REST catalog server, a Spark master, a Spark worker and a Spark Thriftserver, all connected to the Ozone cluster
- Download and install an S3 client, like awscli: `$ sudo apt install awscli`
- Using awscli, create the warehouse bucket: `$ AWS_ACCESS_KEY_ID=any AWS_SECRET_ACCESS_KEY=any AWS_REGION=us-east-1 aws s3api --endpoint http://localhost:9878 --bucket=warehouse create-bucket`
- Connect to spark-sql and create a database
- `docker exec -it spark-ozone-iceberg-spark-master-1 /opt/bitnami/spark/bin/spark-sql`
- `spark-sql ()> create database test;`
- you can now create tables within the database, also you can connect using JDBC to the thriftserver.
