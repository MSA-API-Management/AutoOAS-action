# Usage
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
    
          
