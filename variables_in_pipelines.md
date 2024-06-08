# ADO

## In-built Variables
### Agent Variables:
1. **Agent.BuildDirectory:** The local path on the agent where all the folders for a given build pipeline are created. (C:\agent_work\1)
2. **Agent.HomeDirectory:** The directory the agent is installed into. (C:\agent)
3. **Agent.JobName:** The name of the running job. This will usually be "Job" or "_default".
4. **AGENT_JOBSTATUS:** Canceled, Failed, Succeeded, SucceededWithIssues (partially successful)
   
### Build Variables:
1. **`Build.ArtifactStagingDirectory:`** The local path on the agent where any artifacts are copied to before being pushed to their destination (**`c:\agent_work\1\a)`**. Build.ArtifactStagingDirectory and Build.StagingDirectory are interchangeable. This directory is purged before each new build, so you don't have to clean it up yourself.
2. **Build.BuildId**: The ID of the record for the completed build.
3. **Build.BuildNumber**: The name of the completed build, also known as the run number.
4. **`Build.BinariesDirectory`**: The local path on the agent you can use as an output folder for compiled binaries. By default, new build pipelines are not set up to clean this directory. **`(c:\agent_work\1\b)`**.
5. **Build.DefinitionName:** The name of the build pipeline.
6. **Build.SourceBranchName:** The name of the branch the build was queued for.
7. **`Build.SourcesDirectory`:** The local path on the agent where your source code files are downloaded. **`(c:\agent_work\1\s)`**

### Release Variables:
1. **System.ArtifactsDirectory:** Same as Build.ArtifactStagingDirectory

### Example
```yaml
trigger:
- master

pool:
  vmImage: ubuntu-latest

stages:
- stage: Print
  jobs:
  - job: Job1
    steps:
    - bash: echo $(Build.BuildId)
      displayName: 'Print Build.BuildId'
    - bash: echo $(Build.BuildNumber)
      displayName: 'Print BuildNumber'
    - bash: echo $(Build.StagingDirectory)
      displayName: 'Print Build.StagingDirectory'
    - bash: echo $(Build.SourcesDirectory)
      displayName: 'Print Build.SourcesDirectory'
    - bash: echo $(Build.DefinitionName)
      displayName: 'Print Build.DefinitionName' 
    - bash: echo $(Build.SourceBranchName)  
      displayName: 'Print Build.SourceBranchName'
```
   
