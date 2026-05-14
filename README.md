# Spark-Cluster

This repository sets up a Spark cluster using Docker Compose. The cluster consists of a Spark Master and Spark Worker. Below are the details of the setup:

## Architecture

```
              Jupyter
                  ↓
          Spark Master
            /      \
     Spark Worker  Spark Worker
                  ↓
             MinIO (S3)
                  ↓
               Parquet
```

