# Azure Devops 

- **`Boards`**: Track Work
- **`Pipelines`**: Build and Deploy
- **`Repositories`**: Cloud Based Source Control
- **`Test Plans`**: Test Apps


## Boards Work Process
- Basic
- Agile
- Scrum
- Capability Maturity Model Integration (CMMI)

### Basic Workflow in Boards
- To-Do
- Doing
- Done

## Two Types of Azure Repos
- **Git** -> Distributed
- **TFVC** _(Team Foundation Version Control)_ -> Centralized

### Git
- Local Copy
- Complete Version Control
- Commit work
- Sync to cloud

## Azure Pipelines
### Build Pipelines
These pipelines clone the code and build the artifacts based on instructions provided in yaml file. \

### Release Pipelines
These pipelines are generally used to deploy artifacts.

## Jobs: Multiple jobs can run paralelly inside a pipeline on different agents.

- In pipeline yaml files, we can write
```yaml
jobs:
- job: job1
  steps:
  - script: echo Job1 - Hello!
    displayName: 'Run a multi-line script'
- job: Job2
  steps:
  - script: echo Job2!!
    displayName: 'Run another multi-line script'
```

- Lets add dependency between the jobs. Job2 will run when Job1 finishes.
```yaml
jobs:
- job: Job1
  steps:
  - script: echo Job1 - Hello!
    displayName: 'Run a multi-line script'
- job: Job2
  dependsOn: Job1
  steps:
  - script: echo Job2!!
    displayName: 'Run another multi-line script'
- job: Job3
  dependsOn:
  - Job1
  - Job2
  steps:
  - script: echo Job2!!
    displayName: 'Run another multi-line script'
```
