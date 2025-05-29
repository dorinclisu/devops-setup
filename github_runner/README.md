# Overview
Run github runner as a docker container with access to the docker daemon on the host machine.

# Limitation
Workflows with a custom container image will not work (see bellow), due to fundamental limitations of the github runner itself.
If that is important for you, just install the runner on the host machine directly.
```yaml
jobs:
  <job-name>:
    runs-on: self-hosted
    container: <your-cicd-tooling-image>  # will give runtime error like `sh: can't open '/__w/_temp/13d08d8e-53fe-428f-b01f-6966b1845547.sh': No such file or directory`
```

# Setup
- `export GITHUB_URL=`
- `export RUNNER_TOKEN=`
- `docker compose run --rm --entrypoint "" github-runner sh -c "./config.sh --url $GITHUB_URL --token $RUNNER_TOKEN --work _work --name docker-$HOSTNAME --unattended && sudo cp -a . /config"`
- `docker compose up -d`
