FROM bitnami/spark:3.5
USER root
RUN apt-get clean && apt-get update && apt-get install -y curl wget vim nano
RUN curl -o postgresql-42.3.5.jar https://jdbc.postgresql.org/download/postgresql-42.3.5.jar && \
    curl -o mssql-jdbc-12.4.2.jre11.jar https://repo1.maven.org/maven2/com/microsoft/sqlserver/mssql-jdbc/12.4.2.jre11/mssql-jdbc-12.4.2.jre11.jar && \
    curl -o delta-core_2.12-2.4.0.jar https://repo1.maven.org/maven2/io/delta/delta-core_2.12/2.4.0/delta-core_2.12-2.4.0.jar && \
    mv postgresql-42.3.5.jar mssql-jdbc-12.4.2.jre11.jar delta-core_2.12-2.4.0.jar /opt/bitnami/spark/jars/ && \
    apt-get clean
RUN mkdir -p ${SPARK_HOME}/history
RUN mkdir -p ${SPARK_HOME}/spark-events
ENV TZ=Europe/Istanbul
RUN date
RUN apt-get update && apt-get install -y \
    software-properties-common
RUN mkdir -p /usr/share/man/man1
COPY ./jars/ /opt/bitnami/spark/jars/
# RUN apt-get update && apt-get install -y default-jdk && apt-get clean
# COPY requirements.txt requirements.txt
# RUN pip install --no-cache-dir -r requirements.txt
USER 1001

