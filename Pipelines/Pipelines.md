### Tekton Pipelines

1. A way to define and manage CI/CD workflows
2. Enablement to string together sequence of Tasks to create CI/CD

#### Creating Pipelines

1. Specify/Reference which tasks should be a part of the pipeline
```
spec:
  tasks:
    - name: echo-task
      taskRef:
        name: echo-task
```
2. Create a PipelineRun file containing references to which pipeline to be run/executed
```
spec:
  pipelineRef: 
    name: example-pipeline
```
3. After execution is completed for pipeline-run, it creates a pod and runs the commands in it. <br>
To check the logs use the following command
```
kubectl logs <pipeline-run-pod-name>
```