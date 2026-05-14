# Distributed Spark Cluster with Docker, Jupyter & Persistent Storage

An Apache Spark cluster built locally using Docker Compose, multiple Spark workers, Jupyter Notebook integration, persistent storage, and distributed Parquet processing.

This project was built to deeply understand:
- Distributed computing
- Spark cluster architecture
- Executors & partitions
- Spark UI & DAG execution
- Persistent storage handling
- Docker networking & volumes
- Distributed Parquet writing
- Hadoop filesystem behavior

---

# Architecture

```text
                    +-------------------+
                    |     Jupyter       |
                    |   Spark Driver    |
                    +---------+---------+
                              |
                              v
                    +-------------------+
                    |   Spark Master    |
                    | Cluster Manager   |
                    +---------+---------+
                              |
              ---------------------------------
              |                               |
              v                               v
    +-------------------+         +-------------------+
    |  Spark Worker 1   |         |  Spark Worker 2   |
    |    Executor       |         |    Executor       |
    +-------------------+         +-------------------+
```

---

# Tech Stack

- Apache Spark 3.5.1
- Docker & Docker Compose
- Jupyter Notebook
- PySpark

---

# Features

- Multi-node Spark cluster
- Distributed processing
- Spark Master & Workers
- Jupyter Notebook integration
- Spark UI monitoring
- Persistent Docker volume storage

---

# Project Structure

```text
spark-jupyter-cluster/
│
├── docker-compose.yml
├── README.md
│
├── jupyter-image/
│   └── Dockerfile
│
├── input/
│   └── raw/
│       └── employees.csv
│
└── notebooks/
    └── spark_cluster.ipynb
```

---

# Docker Architecture

This project uses two storage layers:

| Storage Type | Purpose |
|---|---|
| Local Mounted Folder (`/input`) | Read local CSV files |
| Docker Managed Volume (`/data`) | Distributed Parquet storage |

This separation mimics real-world data lake architectures.

---

# Running the Cluster

## Start Cluster

```bash
docker compose up -d --build
```

---

## Stop Cluster

```bash
docker compose down
```

---

# Accessing Services

| Service | URL |
|---|---|
| Jupyter Notebook | http://localhost:8888 |
| Spark Master UI | http://localhost:8085 |
| Spark Worker 1 UI | http://localhost:8081 |
| Spark Worker 2 UI | http://localhost:8082 |
| Spark Application UI | http://localhost:4040 |

---

