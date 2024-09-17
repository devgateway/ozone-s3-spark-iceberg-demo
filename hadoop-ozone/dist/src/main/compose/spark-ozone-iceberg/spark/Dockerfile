FROM bitnami/spark:3.5.0
USER root
RUN install_packages curl sudo net-tools
USER 1001
RUN mkdir extra-jars
RUN mkdir event-logs
RUN mkdir history-logs
RUN curl https://repo1.maven.org/maven2/org/apache/iceberg/iceberg-aws-bundle/1.5.0/iceberg-aws-bundle-1.5.0.jar --output /opt/bitnami/spark/extra-jars/iceberg-aws-bundle-1.5.0.jar
RUN curl https://repo1.maven.org/maven2/org/apache/iceberg/iceberg-spark-runtime-3.5_2.12/1.5.0/iceberg-spark-runtime-3.5_2.12-1.5.0.jar --output /opt/bitnami/spark/extra-jars/iceberg-spark-runtime-3.5_2.12-1.5.0.jar
RUN curl https://repo1.maven.org/maven2/org/slf4j/slf4j-api/2.0.7/slf4j-api-2.0.7.jar --output /opt/bitnami/spark/extra-jars/slf4j-api-2.0.7.jar
