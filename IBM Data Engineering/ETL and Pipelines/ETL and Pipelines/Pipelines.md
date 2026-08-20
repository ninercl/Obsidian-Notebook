
### [[Pipelines]]

- Series of connected processes connected sequentially. 
- The output of one process is the input of the next. 
- **Purpose**: move data from one place or form to another
- Any system which extracts, transforms, and loads data 


![[Pasted image 20260809013447.png|518]]


Data pipeline performance: Latency 

**Latency** is the total time it takes for a single packet of data to pass through the pipeline. 
**Throughput** is how much data can be fed through the piper per unit of time. 
- Larger data packers per time unit equals greater throughput. 

![[Pasted image 20260809013803.png|502]]


----

### Key data pipelines processes

#### Pipeline monitoring considerations

Some key monitoring considerations include:
Latency -> throughput -> Warnings, erros, failures 

*Be aware of utilization rate and logging and alerting system*

![[Pasted image 20260809234459.png|496]]

### Handing unbalanced loads

![[Pasted image 20260809234537.png|494]]

- Pipelines typically containt bottlenecks
- Slower stages may be parallelized to speed up throughput
- Processes can be replicated on multiple CPUs/cores/threads
- Data packets are then distributed across these channels
- Such pipelines are called dynamic or non-linear 

### Stage synchronization

Parallelization and I/O buffers can help mitigate bottlenecks. 


## Batch vs Streaming Data Pipeline 

**Batch data pipelines**
- Operate on batches of data 
- Usually run periodically - hours, days, weeks apart 
- Can be initiated based on data size or other triggers
- When the lates data isn't needed
- Typical choice when accuracy is critical

**Streaming data pipelines**
- Ingest data packets in rapid succession
- For real time result 
- Records/events processed as they happen
- Event streams can be loaded into storage
- Users publish/subscribe to event streams 

**Micro-batch data pipelines**
- Tiny micro-batches and faster processing simulate real-time processing
- Smaller batches improve load balancing, lower latency
- When short short windows of data are required.


![[Pasted image 20260810001302.png|554]]

**Lambda architecture**

- Hybrid architecture for both historical data and streaming data 
- Data stream fill in 'Latency gap'
- Used when data window is needed, but speed is critical
- Drawback is logical complexity 
- Lambda architecture = accuracy and speed

**Data pipeline tools and technologies**

Feature of modern pipeline tools

Typical enterprise grade technologies:
- Automation, easy of use, Drag-and-drop interface, Transformation support, security and compliance. 

 
Open source:
- Pandas Python library: 
	- Versatile and popular programming tool
	- Base on data frames. Great for ETL, EDA, and prototyping
	- Doesn't readily scale to Big Data
- Libraries with similar APIs: Vaex, Dask, and Spark help with scaling up. 

Apache Airflow and Python
+ Versatile "configuration" as code data pipeline platform
+ Open-sourced by Airbnb
+ Programmatically author, schedule, and monitor workflows
+ Scales to Big data. 

Talend Open Studio.
- Supports big data, data warehousing and profiling. 
- Includes collab, monitoring , and scheduling.
- Drag-and-drop GUI allows you to create ETL pipelines
- Automatically generates Java code
- Integrates with many data warehouses. 

#### **Enterprise data pipeline tools**

- AWS Glue: ETL service
- Panopoly: ELT service 
- Alteryx:
- IBM InforSphere DataStage 

**Streaming data pipeline tools**
- IBM Streams

![[Pasted image 20260810002736.png|579]]

