* Allow to ==orchestrate== data processing tasks. This means the ability to run and manage multiple tasks as a directed acyclic graph (DAG) in a job. 

### Job Clusters
* Dedicated clusters for a job or a task run. A job cluster auto terminates once the job is completed, which saves costs compared to all-purpose clusters. Also, it runs in a fully isolate environment. 
### Task
* represents a unit of logic to be run as a step in a job.
* ==Depends on:== can define the **order of execution** of tasks in a job. 

### Retries
* How many times a particular task should be re-run if the task fails with an error message. 