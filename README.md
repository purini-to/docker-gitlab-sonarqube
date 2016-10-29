# Introduction

Dockerfile to build a [GitLab](https://about.gitlab.com/) and [SonarQube](http://www.sonarqube.org/) container image.

# Quick Start

The quickest way to get started is using [docker-compose](https://docs.docker.com/compose/).

Clone repository and startup all docker container.

```bash
git clone https://github.com/purini-to/docker-gitlab-sonarqube
cd docker-gitlab-sonarqube
docker-compose up -d
```

# Access

| *App* | *Link* | *Credentials* |
| ------------- | ------------- | ------------- |
| SonarQube | http://${docker-machine ip default}:9000/ | admin/admin |
| GitLab | http://${docker-machine ip default}:10080/ | root/Change at the time of the first access |

# Run gitlab-runner in a container

Register the runner (Look into [runners documentation](http://doc.gitlab.com/ce/ci/runners/README.html) to learn how to obtain a token):

Replace `${gitlab-runner-container-id}`

```bash
docker exec -it ${gitlab-runner-container-id} gitlab-runner register

Please enter the gitlab-ci coordinator URL (e.g. https://gitlab.com )
http://${docker-machine ip default}:10080/
Please enter the gitlab-ci token for this runner
xxx
Please enter the gitlab-ci description for this runner
my-runner
INFO[0034] fcf5c619 Registering runner... succeeded
Please enter the executor: shell, docker, docker-ssh, ssh?
docker
Please enter the Docker image (eg. ruby:2.1):
ruby:2.1
INFO[0037] Runner registered successfully. Feel free to start it, but if it's
running already the config should be automatically reloaded!
```
