# ADO

### Adding Variables at a Pipeline Level:
- While editing the yaml, there is a variables option right before Save. Here we can give the variable a name and a value. Then this variable can be called in the script. If Bash is used, then $(variable). For powershell, $(env:variable).

```yaml
trigger:
- master

pool:
  vmImage: ubuntu-latest

stages:
- stage: Build
  jobs:
  - job: Job1
    steps:
# Two steps and last one has a name
    - bash: echo This is a build job.
    - bash: echo $(PipelineLevelVariable)
      displayName: 'Run a one-line script'
- stage: Test
  jobs:
  - job: Job2
    steps:
    - script: echo testing
      displayName: 'Run a multi-line script'
```

## Variables at Stage Level
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
## Variables at Job Level
```yaml
trigger:
- master

pool:
  vmImage: ubuntu-latest

stages:
- stage: Build
  jobs:
  - job: Job1
    variables:
      environment: Dev2
    steps:
    - bash: echo $(environment)
      displayName: 'Run a one-line script'

- stage: Test
  dependsOn: Build
  jobs:
  - job: Job2
    variables:
      environment: dev3
    steps:
    - bash: echo $(environment)
      displayName: 'Run a one-line script'
```
