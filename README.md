# Docker Image with Models for LibreTranslate

This project provides automated Docker images of [LibreTranslate](https://github.com/LibreTranslate/LibreTranslate) that include all language models. It is a modified fork of [t-lo/LibreTranslate-ghcr-publisher](https://github.com/t-lo/LibreTranslate-ghcr-publisher).

## Benefits

- Faster container start-up time: The container with models included starts faster as it avoids downloading approximately 14 GB of data during start-up. This improves responsiveness and prevents liveness probe timeouts, avoiding unnecessary container restarts.
- Reduced bandwidth usage: By including the models in the container, each restart doesn't require re-downloading the language models, resulting in significant bandwidth savings (around 14 GB per restart) in container orchestration environments like Kubernetes or Docker Swarm.
- Offline usability: The self-contained image allows you to use LibreTranslate in private networks without internet connectivity.

## Drawbacks

- Larger container image size: The resulting container image size is 16 GB due to the inclusion of language models.

## GitHub Action

A GitHub Action is set up to automatically run on the first day of every month, ensuring that the Docker images are up to date.

## Notes

For more details and usage instructions, please refer to the [LibreTranslate repository](https://github.com/LibreTranslate/LibreTranslate).
