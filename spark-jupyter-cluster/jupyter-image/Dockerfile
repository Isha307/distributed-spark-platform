FROM apache/spark:3.5.1

USER root

RUN pip install pyspark jupyter delta-spark==3.2.0

WORKDIR /opt/workspace

CMD jupyter notebook \
    --ip=0.0.0.0 \
    --port=8888 \
    --allow-root \
    --NotebookApp.token='' \
    --NotebookApp.password=''