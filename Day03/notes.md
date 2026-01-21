# Day 3 – PySpark Operations That Changed How I Think About Data
@Databricks @Codebasics @indiandataclub #DatabricksWithIDC.
Today I went deeper into **how PySpark actually differs from Pandas** and learned some powerful concepts like joins, window functions, and UDFs. This day made distributed data processing feel practical.

---

## PySpark vs Pandas – What I Clearly Understood

What became very clear to me today is that **Pandas and PySpark are built for very different scales**.

- Pandas works well for small datasets and runs on a single machine.
- PySpark is designed for large-scale data and runs in a **distributed environment**.

The most important difference I noticed:
- Pandas executes operations **immediately**
- PySpark follows a **plan first, execute later** approach (lazy evaluation)

Because PySpark optimizes the execution plan before running, it is **much faster and more efficient** when dealing with large datasets.

---

## Understanding Joins in a Practical Way

I learned how different joins behave when combining two datasets:

- **Inner Join** → returns only rows that match in both tables
- **Left Join** → returns all rows from the left table and matching rows from the right
- **Right Join** → returns all rows from the right table and matching rows from the left
- **Full Outer Join** → returns all rows from both tables; non-matching values appear as `NULL`

Seeing join outputs on sample datasets helped me understand **why join choice directly affects data completeness and analysis results**.

---

## Window Functions – Aggregation Without Losing Rows

Window functions were one of the most interesting concepts today.

Normally, aggregation operations like `sum()` or `count()` **shrink multiple rows into a single row**.  
Window functions behave differently.

What I understood:
- A **window** is created over rows or columns
- Each row keeps its identity
- Calculations are performed **without collapsing the dataset**

This makes window functions extremely useful for:
- Running totals
- Rankings
- Comparing current values with previous or next values

I also learned:
- `lag()` → fetches the previous row value
- `lead()` → fetches the next row value

This allows row-level comparisons without complex joins.

---

## User-Defined Functions (UDFs)

I learned that **UDFs are created when built-in functions are not sufficient** for custom logic.

- UDFs allow users to define their own transformation logic
- They are powerful but should be used carefully
- Built-in functions are usually faster and preferred when available

This helped me understand why UDFs are considered a **last-resort tool**, not the first choice.

---

## Hands-on Practice I Tried Today

I experimented with multiple operations on a sample dataset, including:
- `filter`
- `groupBy`
- `orderBy`
- `pivot`
- Aggregations like `sum`

Running these operations helped reinforce how PySpark handles data efficiently at scale.

---
I also learnt some new concepts like Data skew and Salting,which helped me to understand and solve real world data issues.
DATA SKEW : When performing a join, A particular data is present in more than 90% of rows and thus all these huge amount of data is sent to the system usibg a single executor node,while all other nodes sit idle.this makes the system to slow down and may even crash in large datasets and thus the job takes too much of its time to finish its execution .To avoid this we introduce SALTING.

SALTING : we add random numbers into the dataset to spread out the load and minimize the concentration on one particular node,this splits the job in multiple executor nodes and job gets done quickly.

## My Key Takeaway from Day 3

What stood out to me today is that **PySpark focuses on optimizing how data is processed, not just processing it**.  
Concepts like lazy evaluation, window functions, and distributed joins explain why PySpark is the preferred choice for large-scale analytics.
