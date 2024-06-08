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
### We can add dependency between the jobs. Job2 will run when Job1 finishes.
### Stages in ado pipeline are sequential. 
### Jobs and Stages run on different agents (if you have multiple self-hosted agents or you are using microsoft-hosted agents).

## Create a Build Environment
- Install Node.js
- Install Git
- Install on IDE like Visual Studio
- GitHUb account

## Create a Repository
- You can either create a repo by clicking on the current (project-name) repo and selecting **Create New** or import a repo from somewhere else by selecting **Import**.

## CI/CD Pipelines
- Executes the Continuous Integration process
- Runs tasks when you submit code
- Uses a build agent. 
- Creates a build artifact.

## Build Agent
- An agent is installable software that runs one build or deployment job at a time. In Azure, we can use Microsoft hosted agent.
- Builds, tests and deploys code in the cloud
- Runs tasks in build definition.
- Pipeline -> Phases -> Task
- Tasks executed by agents.
- Agents can be grouped into agent pools.
- We can have **self-hosted agent** pools as well. Mostly though, it is better to work with **microsoft-hosted** agent pools.

