# Databricks
## Databricks Architecture and Workspace UI

The Databricks Lakehouse platform is a cloud-native implementation of the lakehouse model. Another way of saying this is that it's a data storage layer that resides on top of the data lake. This offers several advantages, including the performance and reliability of a data warehouse, combined with the flexibility, cost, efficiency and scale of data lake. 

All together, this makes for a powerful platform.

![](Databricks_Platform_Lakehouse.png?raw=True)

Another advantage of this architecture is that it allows a variety of data practitioners––including data analysts, data engineers, and machine learning engineers––to perform their roles in a unified, scalable way. 

![](Datbricks_practitioners.png?raw=True)

# Databricks architecture
**overview of Databricks architecture.**

![](Databricks_Architecture.png?raw=True)

**The data plane** is where your data is processed. It resides in your own cloud account. The data plane hosts compute resources that we call clusters and connects to the data store backing the Databricks file system. It also provides connections to external data sources, either within the same cloud account or elsewhere on the Internet. Some examples of data sources include JDBC or SQL connections to databases or the data lake stored on AWS S3, Azure blob storage, or Google cloud storage. 

**The control plane** consists of the back-end services that are managed and provided by Databricks, aligned with the cloud service in use by the customer (you!), which might be AWS, Azure, or GCP. Though the majority of your data doesn't live here, some elements, such as notebook commands and workspace configurations, are stored in the control plane.
The control plane features several different services. Let's cover them one-by-one:

  **Webapp**, which serves the Databricks UI for you
     
  **Workflow manager**, which provides job workflows and delta live tables or DLT to orchestrate tasks in a number
     
  **Cluster Manager**, which can help you configure and set up Spark Clusters jobs to schedule tasks 
     
  **Unity Catalog**, which provides data governance around access control, metadata management, data lineage, and data discovery.

 # Compute Resources and Cluster Management

 Clusters consist of a set of one or more virtual machine instances, over which computational workloads are distributed. In the typical case, a cluster has a driver node alongside one or more worker nodes, although Databricks provides a single-node model as well. Workloads are distributed across available worker nodes by the driver.

 ![](Clusters.png?raw=True)

Databricks provides two types of clusters:

 - **All-purpose:** clusters: primarily intended for interactive and collaborative development

 - **Job clusters:** clusters for running automated jobs and pipelines in an expeditious and robust way

## All-purpose clusters vs Job clusters

![](Cluster_Types.png?raw=True)

**All-purpose clusters** analyze data collaboratively using interactive notebooks. You can create an all-purpose cluster using the workspace UI or programmatically using the command line Interface, CLI, or Rest API. You can manually terminate and restart an all-purpose cluster. Multiple users can share an all-purpose cluster to do collaborative interactive analysis. 

**Job clusters** allow you to run automated jobs quickly, efficiently, and in a robust fashion. The Databricks Job Scheduler creates a job cluster each time you run a job and terminates the cluster when the job is complete. Keep in mind that you cannot restart a job cluster. 

### Cluster configurations

![](Cluster_Modes.png?raw=True)
A cluster mode is an operating mode. There are two types of operating modes: 

- **Single-node cluster**, which needs only one VM instance hosting the driver. There are no worker instances in this configuration. This low-cost configuration is useful for single-node machine learning workloads that use Spark to load and save data, as well as lightweight exploratory data analysis.

- **Standard cluster**, which is a general purpose configuration consisting of a virtual machine instance hosting the driver and at least one additional instance for the worker.

### Databricks Runtime

Databricks runtime is a collection of core software components running on the cluster, including Apache Spark, Pytorch, Tensorflow, and many other components, and updates that substantially improve the usability, performance, and security of big data analytics. 

![](Runtime_Version.png?raw=True)

Additionally, there is an add-on called Photon for optimizing the performance and cost of SQL workloads. Finally, Databricks also offers an augmented runtime catering to the needs of machine learning workloads in general. 

Pro tip: it's a great practice to select the most recent version that you can!

### Access Mode

The Access mode specifies the overall security model of the cluster. For standard clusters, there are up to four options to choose from. Keep in mind that only two are relevant when connecting the unity catalog, however. 

![](Acess_Mode.png?raw=True)

**Single User:** as the name suggests, clusters using this mode can only be used by a single user who is designated when creating or editing the cluster. Others cannot attach to this cluster. This might seem like a major downside, but this disadvantage is countered by the functionality made available. Single user clusters support SQL, Python, Scala, and R workloads. Init scripts, library installation, and DBFS fuse mounts are also supported on single user clusters. 

**Shared:** clusters with shared settings can be shared by multiple users using SQL and Python workloads, but advanced cluster features like library installation, init scripts, and the DBFS fuse mount are prohibited in order to ensure security isolation between users of the cluster.

### Cluster Policies

Restricted cluster creation can be achieved through the use of policies. 

What are cluster policies? In essence, cluster policies represent a compromise between allowing users to create clusters in an unrestricted manner and completely prohibiting them from creating clusters, thus forcing them to request clusters through their workspace admin. Using a policy offers a third path: the workspace admin bottleneck can be removed from the cluster creation process, while still offering admins some control over resource consumption. Only admin users can create, edit, and delete cluster policies.

![](Cluster_policies.png?raw=True)

Users or service principles can create their own cluster when needed, subject to limits set out in the policy. Policies can help you achieve many different aims: 

Prescribing cluster settings to limit access to costly options

Provide a standardized/pre-set cluster configuration for certain kind of job

Enforce a tagging strategy to simplify housekeeping or ensure accurate chargeback
