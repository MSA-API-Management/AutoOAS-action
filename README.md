# GitHub Action usage
The GitHub Action requires the following inputs:
```yaml
  - uses: API-Evolution-Management/AutoOAS-ci@v1
    with:
      # Path to the directory of the pom.xml file
      mvn_src_path: 
```
The output of the action is stored in the summary of the triggered workflow as an artifact.

## Pitfalls
The AutoOAS action requires the project's source to be loaded inside the runner at an earlier step. For this, the [checkout](https://github.com/actions/checkout) action can be used.

## Example
An example project with a configured workflow can be found [here](https://github.com/API-Evolution-Management/AutoOAS-ci-example).

# GitLab Configuration usage
Link the GitLab configuration file in your `.gitlab-ci.yml`:
```yaml
include:
  - remote: 'https://raw.githubusercontent.com/API-Evolution-Management/AutoOAS-ci/refs/heads/main/AutoOAS-ci.gitlab-ci.yml'
    inputs:
      mvn_src_dir: '.' # Relative path to the directory of the pom.xml file from the project's root directory
```
