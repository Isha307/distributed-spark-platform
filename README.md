# Distributed Spark Streaming Lakehouse Platform

A complete local distributed data engineering platform built using:

- Apache Spark Cluster
- Apache Kafka
- Spark Structured Streaming
- Delta Lake
- MinIO (S3-Compatible Object Storage)
- Jupyter Notebook
- Docker Compose

This project simulates a modern cloud-style streaming lakehouse architecture locally.

---

# Architecture

```text
                         Producer Applications
                                   |
                                   v
                              Apache Kafka
                                   |
                                   v
                         Spark Structured Streaming
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
                        (S3-Compatible Storage)
                                   |
                                   v
                          Delta Lake Tables
```

---

# Features

- Multi-node Spark cluster
- Distributed Spark execution
- Local S3-compatible storage using MinIO
- Delta Lake support
- Real-time streaming with Kafka
- Spark Structured Streaming pipelines
- Streaming ingestion into Delta Lake
- Checkpoint-based fault tolerance
- Distributed parquet writes
- Interactive notebook development
- Dockerized infrastructure
- Real-world DE architecture concepts

---

# Tech Stack

| Technology | Purpose |
|---|---|
| Apache Spark | Distributed data processing |
| Spark Structured Streaming | Real-time stream processing |
| Apache Kafka | Distributed event streaming |
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
- Schedules distributed jobs
- Tracks worker nodes
- Coordinates executors

Port:

```text
8085
```

---

## Spark Workers

- Execute distributed Spark tasks
- Process partitions
- Run Spark executors
- Write parquet and delta files

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

## Apache Kafka

- Distributed event streaming platform
- Stores streaming events inside topics
- Buffers and distributes real-time data

Port:

```text
9092
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
cd distributed-spark-platform
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

# Streaming Pipeline

This project supports real-time event ingestion using Apache Kafka and Spark Structured Streaming.

Pipeline flow:

```text
Producer → Kafka → Spark Streaming → Delta Lake → MinIO
```

The system continuously ingests streaming events and stores them as Delta Lake tables inside MinIO object storage.

This simulates a modern streaming lakehouse architecture locally.

---


# Engineering Concepts Covered

This project demonstrates practical distributed systems concepts including:

- Distributed task scheduling
- Driver vs Executor architecture
- Spark partitions and shuffling
- Small files problem
- Object storage architecture
- S3 APIs
- Streaming ETL pipelines
- Event-driven systems
- Kafka topics and consumers
- Structured Streaming micro-batches
- Delta Lake transactions
- Checkpointing and fault tolerance
- Distributed dependency management
- Lakehouse architecture

---

# Why This Project?

Most Spark tutorials focus only on local DataFrame operations.

This project focuses on understanding how modern distributed data platforms actually work internally:

- distributed compute
- cluster scheduling
- streaming ingestion
- object storage
- partition optimization
- lakehouse architecture

The goal is to simulate production-style data engineering systems locally using open-source technologies.

---

# Future Improvements

Planned enhancements:

- Apache Airflow DAG orchestration
- Bronze / Silver / Gold medallion architecture
- Stream aggregation pipelines
- Kafka multi-topic ingestion
- Data quality framework
- Monitoring and observability
- Stream replay and recovery
- Partition optimization and compaction
- Lakehouse analytics layer

---

# Learning Goals

This project is designed to provide hands-on experience with:

- Modern data engineering systems
- Distributed computing
- Event-driven architectures
- Real-time stream processing
- Cloud-style object storage
- Lakehouse architecture
- Production-style Spark workflows
- Streaming ETL pipelines