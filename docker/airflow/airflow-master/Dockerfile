FROM bitnami/airflow:2.7.3

USER root

RUN apt-get clean && apt-get update && apt-get install -y curl wget vim nano


RUN apt-get update && apt-get install -y \
    software-properties-common
RUN apt-get update && apt-get install -y default-jdk && apt-get clean
RUN mkdir -p /usr/share/man/man1 \
    mkdir -p /opt/bitnami/spark/jars


RUN curl -o hadoop-aws-3.3.4.jar https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-aws/3.3.4/hadoop-aws-3.3.4.jar && \
    curl -o aws-java-sdk-bundle-1.12.604.jar https://repo1.maven.org/maven2/com/amazonaws/aws-java-sdk-bundle/1.12.604/aws-java-sdk-bundle-1.12.604.jar&& \
    curl -o postgresql-42.3.5.jar https://jdbc.postgresql.org/download/postgresql-42.2.14.jar && \
    curl -o mssql-jdbc-12.4.2.jre11.jar https://repo1.maven.org/maven2/com/microsoft/sqlserver/mssql-jdbc/12.4.2.jre11/mssql-jdbc-12.4.2.jre11.jar && \
    curl -o delta-core_2.12-2.4.0.jar https://repo1.maven.org/maven2/io/delta/delta-core_2.12/2.4.0/delta-core_2.12-2.4.0.jar && \
    mv aws-java-sdk-bundle-1.12.604.jar hadoop-aws-3.3.4.jar postgresql-42.3.5.jar mssql-jdbc-12.4.2.jre11.jar delta-core_2.12-2.4.0.jar /opt/bitnami/spark/jars/ && \
    apt-get clean
    
USER 1001