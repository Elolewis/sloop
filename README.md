![logo](logo)
# Introduction
Welcome to sloop - a simple, lightweight, open data orchestration platform. Tailored to meet the requirements of data scientists, engineers, and business users, sloop simplifies data engineering without the need for extensive time spent on microservice infrastructure maintenance. This documentation delves into the architecture, components, deployment options, code examples, connectors, best practices, and troubleshooting of our versatile orchestration platform.

## What is sloop?
Sloop is a Unified data infrastructure tool and data developer platform designed for compatibility and ease of integration. At its core, sloop comprises a few key open-source components:

### Orchestration: Dagster
Dagster takes a data-centric approach to task orchestration. Built in python and designed to treat data as assets rather than tasks, it makes it easy to keep track of data dependencies and lineage.Developed specifically to enable local development of data pipelines, unit testing, CI, code review, staging environments, and debugging, but with an elegant syntax. Comes bundled with Dagit, a user interface for visualizing pipelines and monitoring data assets and execution.

### Storage: MinIO
MinIO is an object storage service that is API compatible with Amazon S3 cloud. Provides a storage container for testing data workflows in a local environment using identical commands and skills needed for handling data on Amazon S3. In a disconnected environment it can be extended into a multi-node instance for stable offline storage.
File Format: Apache Parquet column-oriented data file format designed for efficient data storage and retrieval. Small and highly compressible, Parquet files allow for fast read and write times and support both nested and evolving data structures, making them ideal for storing complex data. Columnar format allows queries to fetch specific values faster

### Table Format: Iceberg
Iceberg is a table format that uses metadata to impose a table structure on top of Parquet files allowing for millions of files to be modified, and queried as if they were a relational database. Iceberg metadata files describe a distributed table structure with snapshots allowing partitioning and time travel, allowing for structured and scalable management of tables within the data lakehouse.

### Query Engine: Trino
Trino (formerly known as PrestoSQL) is a distributed SQL query engine designed for high-performance analytics distributed data sources. Trino's can reference Iceberg tables and efficiently perform SQL operations across multiple files at once.

### SQL and lineage: dbt
dbt (Data Build Tool) is a templating workflow that places guardrails around data, enabling analysts to Collaborate on data models, version them, and test and document queries before safely deploying them to production. Complex queries can be decomposed and recompiled for ease of testing, allowing developers to focus on business logic

## Architecture
![Architecture](architecture)

[architecture]: https://github.com/Elolewis/sloop/images/sloop_architecture.jpg
[logo]: 