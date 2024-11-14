# Databricks
## Databricks Architecture and Workspace UI

The Databricks Lakehouse platform is a cloud-native implementation of the lakehouse model. Another way of saying this is that it's a data storage layer that resides on top of the data lake. This offers several advantages, including the performance and reliability of a data warehouse, combined with the flexibility, cost, efficiency and scale of data lake. 

All together, this makes for a powerful platform.

![](Databricks_Platform_Lakehouse.png?raw=True)

Another advantage of this architecture is that it allows a variety of data practitioners––including data analysts, data engineers, and machine learning engineers––to perform their roles in a unified, scalable way. 

![](Datbricks_practitioners.png?raw=True)

# Databricks architecture
**overview of Databricks architecture.**

![](

**The data plane** is where your data is processed. It resides in your own cloud account. The data plane hosts compute resources that we call clusters and connects to the data store backing the Databricks file system. It also provides connections to external data sources, either within the same cloud account or elsewhere on the Internet. Some examples of data sources include JDBC or SQL connections to databases or the data lake stored on AWS S3, Azure blob storage, or Google cloud storage. 

**The control plane** consists of the back-end services that are managed and provided by Databricks, aligned with the cloud service in use by the customer (you!), which might be AWS, Azure, or GCP. Though the majority of your data doesn't live here, some elements, such as notebook commands and workspace configurations, are stored in the control plane.
The control plane features several different services. Let's cover them one-by-one:

  **Webapp**, which serves the Databricks UI for you
     
  **Workflow manager**, which provides job workflows and delta live tables or DLT to orchestrate tasks in a number
     
  **Cluster Manager**, which can help you configure and set up Spark Clusters jobs to schedule tasks 
     
  **Unity Catalog**, which provides data governance around access control, metadata management, data lineage, and data discovery.

## Data Ingestion with Delta Lake

This module is designed for Data Engineers to deepen their understanding of Delta Lake to handle data ingestion, transformation, and management with ease. Using the latest features of Delta Lake, learners will explore real-world applications to enhance data workflows, optimize performance, and ensure data reliability.

## Deploy Workloads with Databricks Workflows

This module is designed for data engineer professionals who are looking to leverage Databricks for streamlined and efficient data workflows. By the end of this course, you’ll be well-versed in using Databricks' Jobs and Workflows functionalities to automate, manage, and monitor complex data pipelines. The course includes hands-on labs and best practices to ensure a deep understanding and practical ability to manage workflows in production environments.

## Build Data Pipelines with Delta Live Tables

This comprehensive module is designed to understand the Medallion Architecture using Delta Live Tables. Participants will learn how to create robust and efficient data pipelines for structured and unstructured data, understand the nuances of managing data quality, and unlock the potential of Delta Live Tables. By the end of this course, participants will have hands-on experience building pipelines, troubleshooting issues, and monitoring their data flows within the Delta Live Tables environment.

## Data Management and Governance with Unity Catalog

In this module, you'll learn about data management and governance using Databricks Unity Catalog. It covers foundational concepts of data governance, complexities in managing data lakes, Unity Catalog's architecture, security, administration, and advanced topics like fine-grained access control, data segregation, and privilege management.
