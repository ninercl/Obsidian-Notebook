
#Apacheairflow 
[[Apache Airflow]][[Pipelines]]]

- Open-source workflow orchestration tool
- A platform that lets you build and run workflows 
- A workflow is represented as a Directed Acyclic Graph (DAG) 
*Note: Airflow is not a data streaming solution*

![[Pasted image 20260811232218.png|579]]

![[Pasted image 20260811232303.png|580]]

<u>Benefits</u>

- Pure Python = Flexibility
- Useful UI = Full insight
- Integration = Plug and play
- Easy to use = Unlimited pipeline scope 
- Open source = Community of developers

Apache Airflow principles
- Scalable
- Dynamic
- Extensible
- Lean

----
**Advantages of representing data pipelines as DAG**

Directed Acyclic Graph (DAG)
- Graph: Nodes and edges 
- Directed graph: each graph has a direction
- Acyclic: No loops (cycles)


Tasks and Operators
- Tasks are  written in Python
- Task implement operators, for extample, Python, SQL, or bash operators
- Operators determine what each task does
- Sensor operators poll for a certain time or condition 
- Other operators include mail and HTTP request operators 

![[Pasted image 20260812000614.png|588]]
![[Pasted image 20260812000623.png|589]]

Airflow Scheduler 

Airflow -> deploys on worker array -> Follows your DAG -> First DAG run -> Subsequent runs 

Advantages of workflows as code
- Maintainable
- Versionable
- Collaborative
- Testable
---

Build a Dag 

*Python script blocks:*

- Python library imports
	- DAG arguments
		- Dag definition
			- Task definition
				- Task pipeline

Build an Airflow pipeline

$ simple_example_DAG.py

print greeting -> Print date and time -> sch 5 sec.

---
Logging

Logging capability is required for developers to monitor the status of taks in DAG runs and to diagnose and debug issues.

![[Pasted image 20260815014621.png|534]]

- Retrieving previous task events through UI on the web server 

*Monitoring metrics*
- Counters: Metrics that always increase; total count of task intance succeses, failures  
- Gauges: Metrics that may fluctuate; mi,ber of running tasks, DAG bag siZE 
- Timers:  Metrics related to time duration; milliseconds to finish a taks or reach a success/fail state.

![[Pasted image 20260816115907.png|611]]