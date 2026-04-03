# On-Premises Data Infrastructure Overview
## Building Your Own Data Center: The Complete Stack

---

## 🏗️ The Foundation (Hardware & OS)

### Linux Servers: The Base Infrastructure

**What it is:**
- Physical server hardware (bare metal) organized in server racks
- The raw computing foundation equivalent to AWS, Google Cloud, or Azure data centers
- Requires data center space with power, cooling, and network infrastructure

**Linux Distribution Options:**
- **Ubuntu Server**: Popular, user-friendly, strong community support
- **Red Hat Enterprise Linux (RHEL)**: Enterprise-grade, commercial support, highly stable
- **CentOS Stream**: Free alternative to RHEL, community-driven
- **Rocky Linux / AlmaLinux**: RHEL alternatives after CentOS changes
- **Debian**: Stable, lightweight, excellent for server workloads

**Key Considerations:**
- **Hardware Requirements:**
  - High-core CPUs (Intel Xeon, AMD EPYC) for parallel processing
  - Large RAM (256GB - 1TB+ per server) for in-memory analytics
  - Fast storage: NVMe SSDs for hot data, HDDs for cold storage
  - High-speed networking: 10Gbps+ network cards for data transfer

- **Infrastructure Needs:**
  - **Rack Space**: Standard 42U racks to house multiple servers
  - **Power**: Redundant power supplies, UPS systems, generator backup
  - **Cooling**: HVAC systems to prevent overheating
  - **Networking**: Core switches, ToR (Top of Rack) switches, firewalls
  - **Physical Security**: Locked data center, access controls

**Cloud Equivalent:**
- **AWS**: EC2 instances running on Amazon's physical infrastructure
- **Azure**: Virtual Machines on Microsoft's hardware
- **Google Cloud**: Compute Engine instances

---

## ☸️ The "Data Center OS" (Orchestration)

### Kubernetes (K8s): Container Orchestration Platform

**What it is:**
- The "operating system" for your private cloud infrastructure
- Manages containerized applications across multiple servers
- Abstracts away the complexity of running distributed systems

**Why You Need It:**
In modern infrastructure, you don't install software directly on Linux servers anymore. Instead:
1. Package applications in **containers** (using Docker)
2. Use **Kubernetes** to manage, scale, and monitor those containers
3. K8s handles deployment, failure recovery, load balancing automatically

**Key Capabilities:**
- ✅ **Auto-scaling**: Automatically adds/removes containers based on workload
- ✅ **High Availability**: If a server dies, K8s reschedules containers elsewhere
- ✅ **Resource Management**: Intelligently allocates CPU, memory, storage
- ✅ **Service Discovery**: Applications can find each other automatically
- ✅ **Rolling Updates**: Update services without downtime
- ✅ **Self-healing**: Automatically restarts failed containers

**Kubernetes Distributions for On-Prem:**
- **Rancher**: Enterprise Kubernetes management platform
- **Red Hat OpenShift**: Enterprise-grade K8s with additional tooling
- **Canonical Kubernetes**: Ubuntu's K8s distribution
- **VMware Tanzu**: Kubernetes for VMware environments
- **Vanilla Kubernetes**: Install K8s from scratch (most control, most complex)

**What Runs on Kubernetes:**
- Apache Spark clusters
- Trino/Presto query engines
- DataBricks runtime
- MinIO storage nodes
- Monitoring tools (Prometheus, Grafana)
- ETL/orchestration tools (Airflow, Dagster)

**Cloud Equivalent:**
- **AWS**: EKS (Elastic Kubernetes Service)
- **Azure**: AKS (Azure Kubernetes Service)
- **Google Cloud**: GKE (Google Kubernetes Engine)

---

## 💾 The Storage Layer (The "Data Lake")

### Option 1: Apache Hadoop HDFS (Hadoop Distributed File System)

**What it is:**
- The original open-source distributed file system for big data
- Designed to store massive datasets across many commodity servers
- Battle-tested, mature technology (created in 2006)

**How it Works:**
- Data is split into blocks (typically 128MB each)
- Each block is replicated across 3 servers (configurable)
- NameNode tracks where all data blocks are stored
- DataNodes store the actual data blocks

**Pros:**
- ✅ Proven at massive scale (exabytes of data)
- ✅ Built-in data replication for reliability
- ✅ Tight integration with Hadoop ecosystem (Hive, Pig, MapReduce)
- ✅ Free and open-source

**Cons:**
- ❌ Complex to set up and maintain
- ❌ Requires dedicated NameNode servers (single point of failure)
- ❌ Not S3-compatible (requires different APIs)
- ❌ Older architecture compared to modern object storage

**Best For:**
- Existing Hadoop environments
- Very large datasets (petabytes+)
- Batch processing workloads

**Cloud Equivalent:**
- **AWS S3** (Simple Storage Service)
- **Azure Data Lake Storage Gen2**
- **Google Cloud Storage**

---

### Option 2: MinIO (Modern Object Storage)

**What it is:**
- High-performance, cloud-native object storage system
- **S3-compatible API**: Works with tools built for AWS S3
- Designed for containerized environments and Kubernetes
- The modern choice for on-premises "data lake" storage

**How it Works:**
- Stores data as objects (like files) with metadata
- Distributed across multiple servers for redundancy
- Erasure coding for data protection (more efficient than replication)
- RESTful API for programmatic access

**Pros:**
- ✅ **S3-compatible**: Drop-in replacement for AWS S3 in your code
- ✅ Simpler architecture than HDFS
- ✅ Works great on Kubernetes
- ✅ High performance (optimized for SSD storage)
- ✅ Lightweight and easy to deploy
- ✅ Modern data lake format support (Iceberg, Delta Lake, Hudi)

**Cons:**
- ❌ Newer than HDFS (less battle-tested at extreme scale)
- ❌ Less mature ecosystem compared to Hadoop

**Best For:**
- New data lake implementations
- Organizations wanting S3 compatibility on-premises
- Kubernetes-based infrastructure
- Projects using modern table formats (Delta Lake, Iceberg)

**Key Features:**
- **Multi-tenancy**: Support for multiple departments/projects
- **Encryption**: At-rest and in-transit encryption
- **Versioning**: Keep multiple versions of objects
- **Lifecycle policies**: Automatically move/delete old data
- **Replication**: Multi-site replication for disaster recovery

**Cloud Equivalent:**
- **AWS S3** (MinIO is API-compatible)
- **Azure Blob Storage**
- **Google Cloud Storage**

---

### Storage Comparison Table

| Feature | HDFS | MinIO | Cloud (S3/GCS/ADLS) |
|---------|------|-------|---------------------|
| **API** | Custom HDFS API | S3-compatible | Native cloud APIs |
| **Deployment** | Complex | Simple (containers) | Managed service |
| **Performance** | Good (batch) | Excellent (SSD) | Excellent |
| **Maturity** | Very mature | Newer | Very mature |
| **S3 Compatibility** | No (requires gateway) | Yes (native) | Yes |
| **Best Use Case** | Hadoop ecosystem | Modern data lakes | Cloud-native |

---

## ⚙️ The Processing & Query Layers (The "Engines")

### Processing Engine: Apache Spark

**What it is:**
- The industry-standard open-source framework for large-scale data processing
- Performs ETL (Extract, Transform, Load) operations on big data
- In-memory processing for speed (100x faster than older MapReduce)

**Key Capabilities:**
- **Batch Processing**: Process large datasets in scheduled jobs
- **Stream Processing**: Real-time data processing with Spark Streaming
- **SQL Queries**: Run SQL on data with Spark SQL
- **Machine Learning**: Built-in ML library (MLlib)
- **Graph Processing**: GraphX for graph analytics

**How You'd Use It:**
1. Run Spark jobs on your Kubernetes cluster
2. Read data from MinIO/HDFS
3. Transform data using Python (PySpark), Scala, or SQL
4. Write results back to storage or a database

**Pros:**
- ✅ Industry standard, huge community
- ✅ Very fast in-memory processing
- ✅ Unified API for batch and streaming
- ✅ Multiple language support

**Cons:**
- ❌ Can be complex to tune for performance
- ❌ Resource-intensive (requires lots of RAM)

**Cloud Equivalent:**
- **Azure Synapse Spark Pools**
- **AWS EMR (Elastic MapReduce)**
- **Google Cloud Dataproc**
- **Databricks on cloud platforms**

---

### Commercial Platform: Databricks

**What it is:**
- A commercial platform built on top of Apache Spark
- Makes Spark much easier to use with polished UI and management tools
- Includes **Delta Lake**: An optimized storage layer on top of data lakes
- Created by the original creators of Apache Spark

**Key Features:**
- **Collaborative Notebooks**: Jupyter-style notebooks for data science
- **Delta Lake**: ACID transactions, time travel, schema evolution for data lakes
- **Optimized Spark**: Performance-tuned Spark runtime (faster than open-source)
- **Unity Catalog**: Data governance and metadata management
- **MLflow**: Machine learning lifecycle management
- **Job Scheduling**: Built-in orchestration and scheduling

**Deployment Options:**
- **Databricks on your own K8s cluster** (on-premises)
- **Databricks on AWS/Azure/GCP** (cloud-hosted but your account)

**Pros:**
- ✅ Much easier to use than raw Spark
- ✅ Delta Lake adds critical features to data lakes
- ✅ Great for data science teams (notebooks, ML tools)
- ✅ Commercial support and managed service

**Cons:**
- ❌ **Expensive**: Requires commercial licensing
- ❌ Vendor lock-in (Delta Lake works elsewhere but best on Databricks)
- ❌ On-prem deployment still requires significant infrastructure

**When to Use:**
- You have budget for commercial software
- Data science team needs collaborative notebooks
- Want ACID transactions in your data lake (Delta Lake)
- Need enterprise support

**Cloud Equivalent:**
- **Azure Synapse Spark Pools** (similar managed Spark)
- **AWS Glue** (managed ETL service)
- **Google Cloud Dataproc** (managed Spark/Hadoop)

---

## 🔍 Query Engines (The "SQL" Part)

Your analysts need to run fast SQL queries on your data lake, just like using Redshift or BigQuery.

### Option 1: Trino (formerly PrestoSQL)

**What it is:**
- Open-source distributed SQL query engine
- **Query federation**: Query data where it lives (no need to load it first)
- Designed for interactive analytics (subsecond to minutes)
- Architecture similar to Google BigQuery's Dremel engine

**How it Works:**
- Analysts write SQL queries in any BI tool (Tableau, Power BI, etc.)
- Trino connects to multiple data sources simultaneously
- Executes queries in parallel across many nodes
- Returns results fast (optimized for low-latency queries)

**Key Features:**
- **Query Multiple Sources**: Join data from MinIO, PostgreSQL, MySQL, etc. in one query
- **No ETL Required**: Query data directly without loading it
- **MPP Architecture**: Massively Parallel Processing for speed
- **Standards-Compliant SQL**: ANSI SQL support

**Supported Data Sources:**
- MinIO/S3
- HDFS
- PostgreSQL, MySQL, SQL Server
- Hive, Iceberg, Delta Lake
- Kafka (streaming)
- Many more via connectors

**Pros:**
- ✅ Free and open-source
- ✅ Very fast for interactive queries
- ✅ Query federation eliminates data movement
- ✅ Scales to hundreds of nodes
- ✅ Active community and development

**Cons:**
- ❌ Stateless (no data storage, so needs underlying storage)
- ❌ Less mature than some commercial options
- ❌ Requires tuning for optimal performance

**Best For:**
- Interactive analytics on data lakes
- Organizations with data in multiple systems
- Teams comfortable managing open-source software

**Cloud Equivalent:**
- **Google BigQuery** (similar query federation architecture)
- **AWS Athena** (serverless Presto/Trino)
- **Azure Synapse Serverless SQL Pool**

---

### Option 2: Apache Impala

**What it is:**
- Open-source MPP SQL query engine designed for Hadoop
- Created by Cloudera specifically for low-latency SQL on HDFS
- Direct alternative to Hive (older Hadoop query tool)

**Pros:**
- ✅ Excellent integration with Hadoop ecosystem
- ✅ Very fast on HDFS data
- ✅ Production-proven at large scale

**Cons:**
- ❌ Primarily designed for HDFS (less flexible than Trino)
- ❌ Smaller community than Trino
- ❌ Less active development

**Best For:**
- Existing Hadoop/HDFS environments
- Teams already using Cloudera

---

### Option 3: ClickHouse (Full MPP Database)

**What it is:**
- Open-source columnar database management system (DBMS)
- Designed for **blazing-fast analytics** on massive datasets
- You load data into ClickHouse (unlike Trino which queries external data)

**Architecture:**
- **Column-oriented storage**: Optimized for analytical queries
- **Compression**: 10x-100x data compression
- **Distributed**: Shards data across multiple servers
- **Vectorized query execution**: Uses CPU SIMD instructions for speed

**Key Features:**
- **Extremely fast**: Queries often 100x faster than traditional databases
- **Real-time ingestion**: Can handle millions of inserts per second
- **SQL support**: Standard SQL with extensions
- **Materialized views**: Pre-compute aggregations for instant results

**Pros:**
- ✅ **Fastest query performance** of all options
- ✅ Excellent compression (save on storage costs)
- ✅ Great for time-series and event data
- ✅ Real-time analytics (no batch ETL delays)

**Cons:**
- ❌ Requires data to be loaded into ClickHouse (not query federation)
- ❌ Limited UPDATE/DELETE support (designed for append-only data)
- ❌ Steeper learning curve

**Best For:**
- Real-time analytics dashboards
- Time-series data (logs, events, IoT)
- High-performance analytics workloads
- When query speed is critical

**Cloud Equivalent:**
- **AWS Redshift** (similar MPP columnar database)
- **Google BigQuery** (columnar, but different architecture)
- **Azure Synapse Dedicated SQL Pool**
- **Snowflake** (cloud data warehouse)

---

### Option 4: Greenplum Database

**What it is:**
- Open-source MPP database originally by Pivotal (now VMware)
- Based on PostgreSQL (full ACID compliance)
- Full-featured data warehouse system

**Key Features:**
- **PostgreSQL compatible**: Use familiar PostgreSQL tools
- **ACID transactions**: Full transactional support
- **Advanced analytics**: Built-in ML and geospatial functions
- **Hybrid storage**: Row and column-oriented storage

**Pros:**
- ✅ PostgreSQL compatibility (easy migration)
- ✅ Full SQL support with ACID guarantees
- ✅ Mature and stable
- ✅ Good for mixed workloads (OLTP + OLAP)

**Cons:**
- ❌ Heavier weight than ClickHouse
- ❌ Slower than ClickHouse for pure analytics
- ❌ Requires more operational expertise

**Best For:**
- Organizations using PostgreSQL
- Need ACID transactions in data warehouse
- Mixed transactional and analytical workloads

**Cloud Equivalent:**
- **AWS Redshift** (similar MPP architecture)
- **Azure Synapse Dedicated SQL Pool**
- **Google BigQuery**

---

## 📊 Query Engine Comparison

| Engine | Type | Query Speed | Data Location | Best Use Case | Cloud Equivalent |
|--------|------|-------------|---------------|---------------|------------------|
| **Trino** | Query Federation | Fast | External (no load) | Multi-source analytics | BigQuery, Athena |
| **Impala** | Query Engine | Fast | HDFS | Hadoop environments | Athena |
| **ClickHouse** | Database | Very Fast | Internal (load data) | Real-time dashboards | Redshift, BigQuery |
| **Greenplum** | Database | Fast | Internal (load data) | ACID + Analytics | Redshift, Synapse |

---

## 🏛️ Complete On-Premises Stack Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                     ANALYTICS & BI LAYER                        │
│  (Tableau, Power BI, Looker, Metabase, Apache Superset)       │
└─────────────────────────────────────────────────────────────────┘
                                ▲
                                │ SQL Queries
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                      QUERY ENGINE LAYER                         │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐      │
│  │  Trino   │  │ Impala   │  │ClickHouse│  │Greenplum │      │
│  │ (Query   │  │ (Query   │  │ (MPP DB) │  │ (MPP DB) │      │
│  │  Fed)    │  │ Engine)  │  │          │  │          │      │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘      │
└─────────────────────────────────────────────────────────────────┘
                                ▲
                                │ Reads
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                     PROCESSING LAYER                            │
│  ┌────────────────────┐        ┌───────────────────┐           │
│  │   Apache Spark     │        │    Databricks     │           │
│  │   (Open Source)    │   OR   │  (Commercial)     │           │
│  │   - ETL Jobs       │        │  - Delta Lake     │           │
│  │   - ML Pipelines   │        │  - Notebooks      │           │
│  └────────────────────┘        └───────────────────┘           │
└─────────────────────────────────────────────────────────────────┘
                                ▲
                                │ Reads/Writes
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                      STORAGE LAYER (DATA LAKE)                  │
│  ┌────────────────────┐              ┌───────────────────┐     │
│  │  Apache HDFS       │      OR      │      MinIO        │     │
│  │  (Hadoop DFS)      │              │  (S3-Compatible)  │     │
│  │  - Legacy          │              │  - Modern         │     │
│  │  - Proven Scale    │              │  - K8s Native     │     │
│  └────────────────────┘              └───────────────────┘     │
│                                                                 │
│  Table Formats: Iceberg, Delta Lake, Hudi                     │
└─────────────────────────────────────────────────────────────────┘
                                ▲
                                │ Managed by
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│            ORCHESTRATION LAYER (DATA CENTER OS)                 │
│                          Kubernetes (K8s)                       │
│  - Container orchestration                                      │
│  - Auto-scaling                                                │
│  - High availability                                           │
│  - Resource management                                         │
└─────────────────────────────────────────────────────────────────┘
                                ▲
                                │ Runs on
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│              FOUNDATION LAYER (HARDWARE & OS)                   │
│                    Physical Linux Servers                       │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐      │
│  │ Server 1 │  │ Server 2 │  │ Server 3 │  │ Server N │      │
│  │ Ubuntu/  │  │ Ubuntu/  │  │ Ubuntu/  │  │ Ubuntu/  │      │
│  │  RHEL    │  │  RHEL    │  │  RHEL    │  │  RHEL    │      │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘      │
│                                                                 │
│  Datacenter: Power, Cooling, Networking, Physical Security    │
└─────────────────────────────────────────────────────────────────┘
```

---

## 💰 Cost Considerations

### Capital Expenses (CapEx):
- **Hardware**: $10K-$50K per server × number of servers
- **Networking**: $50K-$500K for switches, routers, firewalls
- **Data Center**: $500K-$5M+ for building/upgrading data center space
- **Power & Cooling**: $100K-$1M+ for infrastructure
- **Initial Setup**: $100K-$500K in labor and consulting

### Operating Expenses (OpEx):
- **Power**: $5K-$50K/month depending on scale
- **Cooling**: Included in power costs typically
- **Network bandwidth**: $1K-$20K/month
- **Staffing**:
  - Data Center technicians: $80K-$120K/year
  - Linux/Kubernetes admins: $100K-$150K/year
  - Data engineers: $120K-$180K/year
  - Storage admins: $90K-$130K/year
- **Software licensing**:
  - Open source: Free (but support costs)
  - Databricks: $$$$ (contact for pricing)
  - Red Hat subscriptions: $1K-$5K per server per year
  - Monitoring tools: $10K-$100K/year

### Break-Even Analysis:
**On-premises makes financial sense when:**
- You have stable, predictable workloads (not bursty)
- You'll use at least 70%+ of capacity consistently
- You have compliance/regulatory requirements for on-prem
- You have skilled staff to manage infrastructure
- Scale is large enough (typically 100+ servers)

**Cloud makes more sense when:**
- Workloads are variable or bursty
- You're just starting out (no upfront CapEx)
- You don't have in-house infrastructure expertise
- Need global scale and distribution
- Want to outsource infrastructure management

---

## 🛠️ Additional Components Needed

### Orchestration & Workflow:
- **Apache Airflow**: Schedule and monitor ETL pipelines
- **Dagster**: Modern data orchestration platform
- **Prefect**: Workflow orchestration

### Metadata & Governance:
- **Apache Atlas**: Metadata management for Hadoop
- **DataHub**: Open-source metadata platform
- **Amundsen**: Data discovery and metadata engine
- **Unity Catalog** (Databricks): Centralized governance

### Monitoring & Observability:
- **Prometheus + Grafana**: Metrics and dashboards
- **ELK Stack** (Elasticsearch, Logstash, Kibana): Log management
- **Jaeger**: Distributed tracing

### Data Quality:
- **Great Expectations**: Data quality testing
- **Apache Griffin**: Data quality solution for big data
- **dbt**: Data transformation and testing

### Security:
- **Apache Ranger**: Security framework for Hadoop
- **Vault**: Secrets management
- **Kerberos**: Authentication
- **LDAP/Active Directory**: User management

---

## 📚 Learning Path & Resources

### For Infrastructure Team:
1. **Linux Administration** → Learn RHEL/Ubuntu server management
2. **Kubernetes** → Get certified (CKA - Certified Kubernetes Administrator)
3. **Networking** → Understand TCP/IP, DNS, load balancing
4. **Storage Systems** → Learn HDFS or MinIO administration

### For Data Engineering Team:
1. **Apache Spark** → Learn PySpark or Scala
2. **SQL** → Master SQL query optimization
3. **Data Modeling** → Learn dimensional modeling, star schemas
4. **Orchestration** → Learn Airflow or Dagster

### For Data Analysts:
1. **SQL** → Master query writing and optimization
2. **BI Tools** → Learn Tableau, Power BI, or Looker
3. **Data Visualization** → Best practices for dashboards

---

## 🎯 Recommended Starting Configuration

### Small/Medium Organization (< 5 TB data):

**Hardware:**
- 5-10 servers (128GB RAM, 20+ cores each)
- 10Gbps networking
- Mix of SSD (hot data) and HDD (cold data)

**Software Stack:**
- **Storage**: MinIO (S3-compatible)
- **Orchestration**: Kubernetes
- **Processing**: Apache Spark
- **Query**: Trino or ClickHouse
- **Orchestration**: Airflow

**Estimated Cost:**
- CapEx: $150K-$300K (hardware + setup)
- OpEx: $200K-$400K/year (power, staff, bandwidth)

### Large Organization (> 100 TB data):

**Hardware:**
- 50-100+ servers
- Dedicated storage cluster (MinIO or HDFS)
- Dedicated compute cluster (Spark/Databricks)
- Dedicated query cluster (Trino/ClickHouse)
- High-availability networking with redundancy

**Software Stack:**
- **Storage**: MinIO or HDFS (multi-petabyte scale)
- **Orchestration**: Kubernetes (multi-cluster)
- **Processing**: Databricks or Apache Spark
- **Query**: Trino + ClickHouse (complementary)
- **Orchestration**: Airflow + custom tooling
- **Governance**: Unity Catalog or DataHub

**Estimated Cost:**
- CapEx: $2M-$10M+ (data center, hardware, setup)
- OpEx: $1M-$5M/year (power, cooling, staff, licenses)

---

## ✅ Decision Matrix: On-Prem vs Cloud

| Factor | Choose On-Premises | Choose Cloud |
|--------|-------------------|--------------|
| **Data Size** | > 100TB predictable growth | Variable or < 100TB |
| **Budget** | Can afford $1M+ CapEx | Prefer OpEx model |
| **Staff** | Have infrastructure experts | Lean engineering team |
| **Compliance** | Must stay on-prem by law | Standard compliance OK |
| **Workload** | Steady, predictable | Bursty, variable |
| **Latency** | Need lowest latency | Can tolerate internet latency |
| **Control** | Want full control | Want managed services |
| **Timeline** | Can wait 6-12 months | Need to start in weeks |

---

**Document Version:** 1.0
**Last Updated:** November 5, 2025
**Prepared for:** City of Wichita Data Lake Project
