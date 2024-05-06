FROM apache/airflow:2.5.1-python3.9

LABEL maintainer="Vy Pham"

USER airflow

COPY requirements.txt /tmp
RUN pip install -r /tmp/requirements.txt


USER root

RUN pip install 'apache-airflow[spark]'

ENV SPARK_HOME=/opt/spark
ENV PYTHONPATH="${SPARK_HOME}/python:${SPARK_HOME}/python/lib/py4j-0.10.9-src.zip"
ENV SPARK_MASTER_URL=spark://spark-master:7077


COPY airflow.cfg /opt/airflow/airflow.cfg

EXPOSE 8080 5555 8888

