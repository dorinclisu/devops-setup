# Overview
Run github runner as a docker container with access to the docker daemon on the host machine.

# Setup
- `export GITHUB_URL=`
- `export RUNNER_TOKEN=`
- `docker compose up -d`
- `docker compose run --rm github-runner ./config.sh --url $GITHUB_URL --token $RUNNER_TOKEN --work _work --name docker-$HOSTNAME --unattended`
