# Spark-Cluster

This repository sets up a Spark cluster using Docker Compose. The cluster consists of a Spark Master and Spark Worker. Below are the details of the setup:

## Architecture

```
Worker Container
      |
      | connect
      v
spark://spark-master:7077
      |
      v
Master Container
```

