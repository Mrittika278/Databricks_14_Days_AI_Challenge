# Day 1 – My Understanding of Databricks

Today I focused on understanding **why Databricks exists and where it actually fits** compared to tools like Pandas and Hadoop.

---

## Why Databricks instead of Pandas or Hadoop?

What I clearly understood today is that **tool choice depends on scale and architecture**.

- Pandas works well when the dataset is small and fits into memory, but it breaks down when data grows because it runs on a single machine.
- Hadoop solves large data problems, but its **disk-based batch processing** makes it slow and operationally heavy.
- Databricks (built on Spark) stood out because of its **in-memory distributed processing**, which significantly reduces processing time.

Another important realization for me was that **Databricks removes a lot of Hadoop’s complexity**. Cluster setup, configuration, and scaling are mostly automated, allowing engineers to focus on data and logic instead of infrastructure.

---

## What I understood about Lakehouse Architecture

I understood the Lakehouse concept as a **practical compromise** between data lakes and data warehouses.

Instead of maintaining separate systems:
- one for cheap storage (data lake)
- another for analytics and performance (data warehouse)

Databricks combines both into a **single architecture**.

I also learned that data flows through the **Medallion Architecture**:
- Raw data first lands in the **Bronze layer**
- Cleaned and structured data moves to **Silver**
- Business-ready data is exposed through **Gold**

This layered approach made sense to me because it keeps raw data intact while still enabling reliable analytics.

---

## How I now see the Databricks Workspace

Today I got clarity on how Databricks is structured internally.

I understood that Databricks separates responsibilities using three planes:
- **Control Plane** handles notebooks, metadata, and job orchestration
- **Data Plane** stores customer data securely
- **Compute Plane** runs Spark clusters and executes workloads

This separation helped me understand **why Databricks is both scalable and secure**. I also learned that access is managed using **role-based access control** at both account and workspace levels.

---

## Real-world use cases that made it click

The industry examples helped me connect theory to reality.

- **Netflix** uses Databricks not just for text data but also for processing images, videos, and audio. It uses this data for content tagging, certification, and recommendations.
- **Comcast** uses Databricks to analyze telemetry data from routers and cables, enabling real-time analytics and failure prediction.
- **Shell** uses Databricks for business intelligence, machine failure prediction, and energy efficiency optimization.

These examples made me realize that Databricks is not just a “big data tool” but a **core decision-making platform**.

---

## My Key Takeaway from Day 1

What stood out to me most is that **Databricks simplifies large-scale data work without sacrificing performance**. It bridges the gap between raw data storage and high-speed analytics, which explains why it is widely adopted across industries.


@Databricks, @Codebasics and @indiandataclub along with #DatabricksWithIDC
