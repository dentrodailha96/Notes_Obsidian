
| Trigger Type | Behavior                                                                                                              |
| ------------ | --------------------------------------------------------------------------------------------------------------------- |
| Scheduled    | Triggers a job run based on a time-based schedule.                                                                    |
| File Arrival | Triggers a job run when new files arrive in the monitored Unity Catalog storage location                              |
| Continuous   | To keep the job always running, trigger another job run whenever a job run completes or fails.                        |
| None         | Runs are triggered manually with the run now button or programmatically using other orchestration tools. (Single run) |
** Only a single run of a job can be active at the time. 

### Structure 

»  Specifying time-base intervals:
* Default: micro-batches of 500ms.
* Using "processingTime=" : define a specify duration as a string. 
* Using "AvailableNow=" : incremental batch processing workloads, a micro-batch processing ahead of processing all available records.
* Using "Once=True": trigger only one time. 

When moving from time-based interval to using `AvailableNow`, this might result in a micro-batch processing ahead of processing all available records as an incremental batch. When moving from `AvailableNow` to a time-based interval, this might result in continuing to process all records that were available when the last `AvailableNow` job triggered. This is the expected behaviour.

*** Continuous processing mode does not relate at all to continuous processing as applied in Delta Live Tables.

