
| Trigger Type | Behavior                                                                                                 |
| ------------ | -------------------------------------------------------------------------------------------------------- |
| Scheduled    | Triggers a job run based on a time-based schedule.                                                       |
| File Arrival | Triggers a job run when new files arrive in the monitored Unity Catalog storage location                 |
| Continuous   | To keep the job always running, trigger another job run whenever a job run completes or fails.           |
| None         | Runs are triggered manually with the run now button or programmatically using other orchestration tools. |
** Only a single run of a job can be active at the time. 

### Structure 
