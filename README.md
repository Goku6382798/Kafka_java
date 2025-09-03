# Avro + JSON Kafka Producer & Consumer

This repository demonstrates an **end-to-end Kafka pipeline** with both **Avro (Schema Registry)** and **JSON serialization**.  
It is organized into multiple Gradle projects for schema management, producers, and consumers.

## 📂 Project Structure

├── Creating_new_schema

│ ├── avro-domain-events # Avro schema project (builds reusable JAR from .avsc)

│ │ └── src/main/avro/person_value.avsc

│ ├── avro-people-producer # Spring Boot producer using Avro + Schema Registry

│ └── avro-people-consumer # Spring Boot consumer for Avro messages

│

├── people-service_producer_adv # JSON-based Kafka producer (Spring Boot)

├── people-consumer_adv # JSON-based Kafka consumer (Spring Boot)

│

├── docker-compose.yml # Kafka + Zookeeper + Schema Registry setup


## 🧰 Tech Stack
- **Java 17**, **Spring Boot**, **Spring Kafka**
- **Apache Kafka**, **Confluent Schema Registry**
- **Avro & JSON Serialization**
- **Gradle (Avro plugin for code generation)**
- **Docker Compose** (for Kafka cluster)

## 🚀 Features
- Define schemas in `avro-domain-events` and generate POJOs.
- Producer services to publish events (Avro or JSON).
- Consumer services to read and log messages.
- Integration with Schema Registry for schema evolution.
- Side-by-side comparison of **schema-based (Avro)** vs **schema-less (JSON)** pipelines.

## ▶️ Getting Started
1. Start Kafka & Schema Registry:
   ```bash
   docker-compose up -d

2. cd Creating_new_schema/avro-domain-events
./gradlew build

3../gradlew bootRun
