# AutoOAS
[AutoOAS](https://arxiv.org/abs/2410.23873) is a static analysis approach for generating accurate and detailed OpenAPI descriptions from Java Spring Boot and JAX-RS source code. The approach is available as a [Docker image](https://hub.docker.com/repository/docker/alexx882/auto-oas/general).

If you use AutoOAS for research purposes please cite our preprint:
```bibtex
@misc{lercher2024generatingaccurateopenapidescriptions,
      title={Generating Accurate OpenAPI Descriptions from Java Source Code}, 
      author={Alexander Lercher and Christian Macho and Clemens Bauer and Martin Pinzger},
      year={2024},
      eprint={2410.23873},
      archivePrefix={arXiv},
      primaryClass={cs.SE},
      url={https://arxiv.org/abs/2410.23873}, 
}
```

## GitHub Action usage
The GitHub Action requires the following inputs:
```yaml
  - uses: MSA-API-Management/AutoOAS-action@v1.2
    with:
      # Path to the source directory
      source_dir:
      # Path to the REST API module (defaults to source_dir if not specified)
      rest_api_module_path:
      # Name of the artifact that will be uploaded to GitHub, default: 'OpenAPI descriptions'
      artifact_name:
      # Output directory of AutoOAS, default: autooas
      output_dir:
```
The output of the action is stored in the summary of the triggered workflow as an artifact.

### Pitfalls
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
