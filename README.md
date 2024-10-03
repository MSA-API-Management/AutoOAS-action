# GitHub Action usage
Example for a job that uses the oas-gen action:
```yaml
jobs:
  oas-gen:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4 # Use checkout action to fetch project files
      - id: oas-gen
        uses: API-Evolution-Management/oas-gen@v1
        with: 
          mvn_src_path: ${{github.workspace}} # Path to the directory of the pom.xml file
``` 
# GitLab Configuration usage
Link the GitLab configuration file in your `.gitlab-ci.yml`:
```yaml
include:
  - remote: 'https://github.com/API-Evolution-Management/oas-gen/blob/6a2dd57a0495f92d147bd1b3eb1832383971fa1e/oas-gen.gitlab-ci.yml'
    inputs:
      mvn_src_dir: '.' # Relative path to the directory of the pom.xml file from the projects root directory
```
