# ADO Pipelines

## Tasks
- Tasks include various assistants provided by ADO such as Copy task, Maven task etc
- These are included in  stage > jobs > job > steps

```yaml
stages:
- stage: Copy
  jobs:
  - job: Copy_Job
    steps:
    - task: CopyFiles@2
      inputs:
        SourceFolder: '$(Build.SourcesDirectory)'
        Contents: '**'
        TargetFolder: '$(Build.ArtifactStagingDirectory)'
```
- Here CopyFiles@2 means this is the second version of the copy task
