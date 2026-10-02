# AutoOAS CI
[AutoOAS](https://github.com/MSA-API-Management/AutoOAS) is a static analysis approach for generating accurate and detailed OpenAPI descriptions from Java Spring Boot and JAX-RS source code. The approach is available as a [Docker image](https://hub.docker.com/r/alexx882/auto-oas).

## GitHub Action usage
The GitHub Action requires the following inputs:
```yaml
  - uses: MSA-API-Management/AutoOAS-action@v1.2
    with:
      source_dir:
      # Path to the source directory
      rest_api_module_path:
      # Path to the REST API module, default: <source_dir>
      artifact_name:
      # Name of the artifact that will be uploaded to GitHub, default: 'OpenAPI descriptions'
      output_dir:
      # Output directory of AutoOAS, default: 'autooas'
```
The output of the action is stored in the summary of the triggered workflow as an artifact.

### Prerequisite
The AutoOAS action requires the project's source to be loaded inside the runner at an earlier step. For this, the [checkout](https://github.com/actions/checkout) action can be used.

### Example
An example project with a configured workflow can be found [here](https://github.com/MSA-API-Management/AutoOAS-ci-example).

## GitLab Configuration usage
Link the GitLab configuration file in the `.gitlab-ci.yml`:
```yaml
include:
  - remote: 'https://raw.githubusercontent.com/MSA-API-Management/AutoOAS-action/refs/tags/v1.2/AutoOAS.gitlab-ci.yml'
    inputs:
      source_dir: '.' # Source directory
```


## Academic Use
If you use this project in your academic work, please cite the following paper:

> A. Lercher, D. Jamnig, C. Macho, C. Bauer, and M. Pinzger, “Generating accurate OpenAPI descriptions from Java source code,” Journal of Systems and Software, vol. 244, p. 113122, 2027.

```bibtex
@article{LERCHER2027113122,
  title = {Generating accurate OpenAPI descriptions from Java source code},
  journal = {Journal of Systems and Software},
  volume = {244},
  pages = {113122},
  year = {2027},
  issn = {0164-1212},
  doi = {https://doi.org/10.1016/j.jss.2026.113122},
  url = {https://www.sciencedirect.com/science/article/pii/S0164121226003559},
  author = {Alexander Lercher and David Jamnig and Christian Macho and Clemens Bauer and Martin Pinzger}
  }
```
