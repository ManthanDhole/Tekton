### Tekton Pipeline
This document contains important study notes about Tekton Pipelines

#### Tekton Architecture

##### Core Components
1. Definitions
    1. Steps: smallest unit with scripts containing commands to run 
    2. Task: combination of multiple steps required to complete a task, ex. Build or Deploy Task
    3. Pipelines: combination different task that are required to be run together 

2. Invocations
    1. TaskRun: actual invocation of task which would run the different steps in a pod
    2. PipelineRun: actual invocation of the different task for a pipeline
    3. Pods: steps or jobs, run inside a pod on the cluster


##### Event Handling Components

1. EventListener: listens to any external event, ex. webhooks / payload sent from Github or Gitlab when a PR is raised or merged
2. Interceptor: checks every webhooks and only allows Authenticated webhooks to pass to the associated pipeline configurations
3. Trigger Templates / Trigger Bindings: templates contain the different variables that are fetched from the event payloads to be passed to the pipeline run configurations using bindings

##### Tekton Workflow
GitHub > Event > Webhook > EventListener > Interceptor > Trigger Template/Binding > PipelineRun > TaskRun > Pod > Steps