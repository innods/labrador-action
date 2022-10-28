# Labrador Scan

해당 repository의 Labrador 스캐너 분석 및 업로드를 수행한다.

## Usage

### Create Workflow

Create a workflow (eg: `.github/workflows/labrador.yml` see [Creating a Workflow file](https://help.github.com/en/articles/configuring-a-workflow#creating-a-workflow-file)) to utilize the labrador Scanner with content:

```yml
name: Labrador CI
on:
  pull_request:
    branches: [ master ]

jobs:
  scanner:
    runs-on: ubuntu-latest
    
    steps:
    - uses: innods/labrador-action@v1
      with:
        project-path: './'
        project-token: ${{ secrets.LABRADOR_APIKEY }}
        project-key: ${{ secrets.LABRADOR_PROJECTKEY }}
```

#### Inputs

| Name | Description | Default |
| - | - | - |
| `project-path` | 스캔을 수행할 repository내의 directory | ./ |
| `project-token` | api key |  |
| `project-key` | 업로드를 수행할 project key | 

# Contributions

Contributions are welcome!