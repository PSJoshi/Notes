## MapReduce
Mapreduce(MR) is the computing paradigm used in Hadoop cluster for parallel processing of large datasets.Its hypothesis is designed by google to achieve:
* parallel execution
* data distribution 
* fault tolerance
MR processes data in the form of key-value pairs. A key-value(KV) pair is a mapping element between the linked data items - key and its value.
Mapreduce architecture consists of two stages- map stage and reduce stage ( along with intermediate process like shuffling, splitting, sorting). Actual MR process happens in task traker.

## How Hadoop provides solution to big data problems:

### Storage issues
HDFS provides distributed way to store big data. Data is stored in blocks across datanodes and you can specify size of blocks.e.g. 512MB is datasize and you have 128MB hadoop data blocks, HDFS will create 4 blocks and store it across different nodes. It will also replicate data blocks on different datanodes. It focuses on horizontal scaling instead of vertical scaling.


### Variety of data
You can store all kinds of data - structured, unstrucutred or semi-structured data. There is no pre-dumping schema validation. It follows write onces and read many model. 

### Accessing and processing data in faster way
This is one of the challange of big data. In order to solve it, the processing is moved towards data and not the data towards processing/computing node.-i.e. moving data to master mode and processing it. In mapreduce, processing logic is sent to various slave node and data is processed parallely across different slave nodes. Processed results are sent to master node where the results are merged and response is sent to the client.

### YARN
YARN is used for resource management between data nodes and master nodes. In YARN architecture, we have ResourceManager and NodeManager. ResourceManager might or might not be configured on the same machine as NameNode. But, NodeManagers should be configured on the same machine where DataNodes are present.

### Use case where Hadoop is not effective
* Low latency data access - quick access to small parts of data
* Multiple data modification - Hadoop is better fit only if we are concerned about reading the data and not modifying data
* Lots of small files - Hadoop is suitable for scenerios where we have few but large files.

### References
* http://a4academics.com/tutorials/83-hadoop/840-map-reduce-architecture
* https://www.edureka.co/blog/what-is-hadoop/

## Cloud computing vs Grid computing vs Cluster computing

### Grid Computing
* Loosely coupled(Decentralization)
* Diversity and Dynamism
* Distributed Job Management & scheduling

### Cloud computing
* Dynamic computing infrastructure
* IT servicecentric approach
* Self service based usage model
* Minimally or self managed platform

### Cluster computing
* Tightlycoupled systems
* Single system image
* Centralized Job management & scheduling system

Distributed Computing
It is a technique to solve a single  large problem by breaking it down into several tasks where each task is  computed in the individual computers of the distributed system.

### CAP theorm

This is proposed by Eric Brewer in 2000 with a set of 3 basic requirements for distributed system consisting of multiple nodes:
* Consistency - All the servers will have same data. So, the users will get same copy regardless of which server they query
* Availability - The system will always respond to request ( even if it's not having the latest data)
* Partition tolerance - The system will continue to operate as a whole even if individual server fails or can't be reached.

All 3 requirements are impossible to be met.So, a combination of 2 is chosen and is the deciding factor while technology is used.

* Ref - https://www.quora.com/What-is-the-relation-between-SQL-NoSQL-the-CAP-theorem-and-ACID
