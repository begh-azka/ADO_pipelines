# ADO
### To add a variable in the pipeline script
```yaml
trigger:
- master

pool:
  vmImage: ubuntu-latest

stages:
- stage: Build
  variables:
    environment: Dev
  jobs:
  - job: Job1
    steps:
    - bash: echo This is a build job.
      displayName: 'Just Printing'
    - bash: echo $(environment)
      displayName: 'Run a one-line script'
- stage: Test
  dependsOn: Build
  jobs:
  - job: Job2
    steps:
    - script: echo testing
      displayName: 'Run a multi-line script'
```
