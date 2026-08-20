
### Examples of raw data sources

- Paper documents
- web pages
- analog audio/video
- survey, statistics, economics
- transactional data

- Event media from Social stream
- Weather station networks
- IoT
- Medical records
- Human genomes

Techniques
- Optical Character Recognition
- Analog to Digital sampling, CCD sampling
- Mail, phone, or in-person surveys and polls
- Cookies and user logs

Web scraping
 - APIs
- SQL and NoSQL
- Edge computing 
- Biomedical devices

![[Pasted image 20260806001614.png|573]]

[[Data extraction techniques]]

---
[[Introduction to Data Transformation Techniques]]

Data transformation can involve various operations:
- Data Typing
- Data Structuring
- Anonymizing, encrypting

- Cleaning
- Normalizing
- Filtering, sorting, aggregating, binning 
- joining or merging 

![[Pasted image 20260806002228.png|507]]

Information loss in transformation

Raw data is bigger in volume compared to transformed data

Examples of ways information can be lost:

- Lossy data compression
- Filtering
- Aggregation
- Edge computing device 

---
[[Data Loading Techniques ]]

### Types of incremental loading

- Stream loading 
	- Data is loaded in real-time
- Batch loading: data loaded in batches 

#### Stream loading: Continuous updates as data arrives. 
- Triggered by events: real-time data, such as sensor data, socail media feed, IoT
- Measures: such as data size, threshold values. 
- User requests, such as videos or music streaming, web pages. 

#### Batch loading
- Periodic loading, such as daily transactions to database
- Can be scheduled: 
	- Windos Task schedules
	- Cron
	- Daily stock update


### Push vs pull methodology

client-server or publisher-suscriber model

Push: 
- Source pushehs data to data warehouse
- Useful for real time data
Pull
- Data earehouse pulls the data from the source
- Useful for scheduled extranction and batch loading

### Loading plans

Serial or sequential loading
- Sequential: Data is added one after the other in sequence --> Default plan
 - Parallel loading: Data form different sources are loaded parallelly
	 - Data from oneo source is split into chunks and loaded
	 - Faster/optimized approach
	 