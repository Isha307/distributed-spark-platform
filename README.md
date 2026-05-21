# Distributed Spark Lakehouse Environment

A complete local distributed data engineering environment using:

- Apache Spark cluster
- Jupyter Notebook
- MinIO (S3-compatible object storage)
- Delta Lake
- Docker Compose

This project simulates a real-world cloud-style data lake architecture locally.

---

# Architecture

```text
                   Jupyter Notebook
                           |
                           v
                    Spark Driver
                           |
                           v
                    Spark Master
                     /         \
                    /           \
                   v             v
           Spark Worker 1   Spark Worker 2
                    \           /
                     \         /
                      v       v
                        MinIO
                    (S3 Object Store)
                           |
                           v
                 Delta / Parquet Files
```

---

# Features

- Multi-node Spark cluster
- Distributed Spark execution
- Local S3-compatible storage using MinIO
- Delta Lake support
- Parquet-based data lake
- Dockerized infrastructure
- Interactive notebook environment
- Real-world DE architecture concepts

---

# Tech Stack

| Technology | Purpose |
|---|---|
| Apache Spark | Distributed data processing |
| Delta Lake | ACID transactions + lakehouse storage |
| MinIO | Local S3-compatible object storage |
| Docker Compose | Container orchestration |
| Jupyter Notebook | Interactive Spark development |
| Parquet | Columnar storage format |

---

# Project Structure

```text
project/
│
├── docker-compose.yml
│
├── jupyter-image/
│   └── Dockerfile
│
├── input/
│
├── notebooks/
│
└── README.md
```

---

# Services

## Spark Master

- Cluster manager
- Schedules jobs
- Tracks workers
- Spark UI available

Port:

```text
8085
```

---

## Spark Workers

- Execute distributed tasks
- Process partitions
- Write parquet/delta files

---

## Jupyter Notebook

- Acts as Spark Driver
- Interactive development environment
- Submits jobs to Spark cluster

Port:

```text
8888
```

---

## MinIO

- Local S3-compatible object storage
- Stores parquet and delta files
- Simulates cloud object storage locally

Ports:

```text
9000 -> S3 API
9001 -> MinIO Console
```

---

# Getting Started

## 1. Clone Repository

```bash
git clone https://github.com/Isha307/distributed-spark-platform
cd spark-jupyter-cluster
```

---

## 2. Start Containers

```bash
docker compose up -d
```

---

## 3. Verify Services

| Service | URL |
|---|---|
| Spark Master UI | http://localhost:8085 |
| MinIO Console | http://localhost:9001 |
| Jupyter Notebook | http://localhost:8888 |

---

# MinIO Setup

Login credentials:

```text
Username: admin
Password: password123
```

---

# This project demonstrates:

- Distributed Spark architecture
- Driver vs Executor model
- Spark partitions
- Object storage concepts
- S3 APIs
- Delta Lake transactions
- Dockerized data platforms
- Parquet optimization
- Distributed dependency management

---

# Future Improvements

Planned additions:

- Apache Airflow for workflow orchestration
- Apache Kafka for real-time streaming
- Spark Structured Streaming
- Medallion architecture
- Batch + streaming pipelines
- Data quality checks
- Lakehouse analytics

---

# Learning Goals

This project is designed to provide hands-on experience with:

- Modern data engineering systems
- Distributed computing
- Cloud-style object storage
- Lakehouse architecture
- Production-style Spark workflows
