# Overview
Run github runner as a docker container with access to the docker daemon on the host machine.

# Setup
- `docker compose up -d`
- `docker compose exec github-runner ./config.sh --url <github-url> --token <runner-token>`
