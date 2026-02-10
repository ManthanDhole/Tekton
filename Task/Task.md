### Important things about Task and TaskRun in Tekton

#### Commands
```
kubectl apply -f task.yml
kubectl get tasks
kubectl describe task <task-name-as-in-metadata-of-task.yml-file>
```

#### What are TaskRuns
1. TaskRuns are individual executions of Tekton Tasks
2. Represent the actual work being done in the CI/CD Pipeline
3. Tasks are Blueprint, TaskRuns are running instances of it
4. Each TaskRun is isolated, one-time execution of a Task
5. Here you'll add `TaskRef` to the `Tasks` you create and `want to Invoke`

6. To run and monitor the taskrun
```
kubectl apply -f taskrun.yml
kubectl get taskrun <task-name>
```