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
## Pipelines
- DisplayName is used to name every step in a stage/job
### Jobs: Multiple jobs can run parallely inside a pipeline on different agents

### Lets add dependency between the jobs. Job2 will run when Job1 finishes.

### Stages in ado pipeline (stages are sequential). 

### Jobs and Stages run on different agents
     
