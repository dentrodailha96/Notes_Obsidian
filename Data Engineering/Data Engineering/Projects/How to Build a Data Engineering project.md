![[Pasted image 20241002104139.png]]

https://www.startdataengineering.com/post/parts-of-dataengineering/
## Parts of a project

1) Define Requirements:
	+ https://www.startdataengineering.com/post/n-questions-data-pipeline-req/
	
	*Identify the end users interests:*
	Who is going to use your pipeline, for what is being done. 

	![[Pasted image 20241002104750.png]]
		When the user doesn't get the reason of the pipeline, create together with him the output of the process. ==Make questions.==
		+ For what do you need data A?
		+ What does the data represent? 
		+ Where this data comes from? 
		+ How fresh does the data need to be? Real time? Daily? Monthly? 
		+ Does historical data need to be stored? When loading data into a warehouse? 
		+ Are you aware about any flaws in the data? Some days it is not loaded? Data format doesn't match? Come from different types or structure?
		+ How is the end user access? SQL, dashboard, APIs, cloud? What is the expected access latency?
		+ What are the data quality metrics to the end-users? Do you have an example of an output? 
	
	*Share steps and create a transparent progress line with the client:*
	Like Trello, JIRA etc.
	
	*Validate the process:*
	Provide a sliced analysis of the data, based on the expected output. 
	Validation includes ensuring that the data has expected business metrics, can be “sliced and diced” as needed and is easy to use by the end-user.
	
	*Deliver Iteratively:*
	Define stakeholders and timeline based on priorities.
	Delivering small chunks enables a short feedback. 
	
	*Create boundaries regarding new features and requirements:*
	Align changes and clarify priorities.
	
2) Data flow design:
	+ [[The multi-hop architecture]].
	+ [[Data Model]]
	
3) Orchestrator and scheduler:
	+ [[Orchestrator]]
	+ [[Scheduler]]
	
4) Data processing design: 
	+ [[Data processors]]
	
5) Code organization:
	+ Keep the data organized for people outside of the team be able to understand.
	
6) Data Storage design:
	+ Storages (AWS, Azure, Google Cloud).
	
7) Monitoring & Alerting:
	+ Define the metrics and thresholds and monitor them.
	+ Software: Datadog, Python library etc.
	
8) Infrastructure:
	+ [[DevOps]]