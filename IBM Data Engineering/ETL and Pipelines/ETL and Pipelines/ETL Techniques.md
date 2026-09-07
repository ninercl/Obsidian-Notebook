
![[Pasted image 20260807231211.png|521]]

### ETL Workflows as DAGs

- Complex ETL workflows can be broken into **tasks and dependencies**.
- Apache Airflow represents workflows as **Directed Acyclic Graphs (DAGs)**.
- DAG arrows define the order and dependencies between tasks.
- Independent tasks can run in parallel, while dependent tasks wait for previous tasks to finish.
- Airflow uses **operators** to execute tasks, such as:
    - **BashOperator** → runs Bash commands/scripts.
    - **PythonOperator** → runs Python code.

### Popular ETL Tools

Modern ETL tools commonly provide:

- **Automation** of data pipelines.
- **Ease of use** and transformation recommendations.
- **Drag-and-drop / low-code interfaces**.
- Support for **complex transformations and calculations**.
- **Security and compliance**, including encryption and standards such as GDPR or HIPAA.

**Key idea:** Airflow helps orchestrate ETL pipelines by defining **what tasks run, in what order, and under which dependencies**.

------
Create an ETL Shell script
![[Pasted image 20260808003439.png|521]]

Extract and buffer

![[Pasted image 20260808003513.png|521]]

Transform temperatures 

get_stats.py:
- Read temperatures from log file
- Calculates temperature stats
- Writes temperature stat to file
- input/outpu filenames specified as command-line arguments

| Call get_stats.py to aggregate the readings         |
| --------------------------------------------------- |
| python3 get_stats.py temperature.log temp_stats.csv |
Load the transforme data

Load the transformed data

| Load the status using load_stats_api |
| ------------------------------------ |
| load_stats_api temp_stats.csv        |
### Set permissions
$ chmod +x Temperature_ETL.sh

Schedule your ETL job

- Open crontab editor: $ crontab -e
	- Enter schedule: 1 * * * * path/Temperature_ETL.sh
	- Close and save
	- Now scheduled and running in production


[[MOC - IBM Data Engineering]]
