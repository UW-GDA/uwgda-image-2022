# docker-template
This repository builds a [JupyterHub](https://jupyter.org/hub) environment with Repo2Docker [GitHub Actions CI](https://github.com/jupyterhub/repo2docker-action)

[![Action Status](https://github.com/uwhackweek/docker-template/workflows/CI/badge.svg)](https://github.com/uwhackweek/docker-template/actions)
[![Docker Pulls](https://img.shields.io/docker/pulls/uwhackweeks/template)](https://hub.docker.com/r/uwhackweeks/template/tags)
[![BinderHub](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/uwhackweek/docker-template/main?urlpath=git-pull?repo=https://github.com/uwhackweek/jupyterbook-template%26amp%3Bbranch=main%26amp%3Burlpath=lab)

### How to use this template repository

1. Click 'Use this Template' to create a copy of the configuration under your organization
2. Edit README.md to replace all occurances of `uwhackweek/docker-template` to your repo name (for example `uwescience/snowexhack2021`)
3. Ensure you have [GitHub Secrets](https://docs.github.com/en/actions/reference/encrypted-secrets) for DOCKER_USERNAME and DOCKER_PASSWORD
4. Build with GitHub Actions simply by pushing to GitHub:
    * Commits to 'main' branch build image, by git commit sha and 'latest', and push to DockerHub and Quay.io
    * Pull Requests trigger image building without pushing to DockerHub

```bash
git clone https://github.com/uwhackweek/docker-template
cd docker-template
git checkout dev
# make sure dev branch is up-to-date with master
git merge master
# modify environment.yml or other files in binder/
git commit -a -m "modified binder/environment to my liking"
git push
# go to github.com and create a pull request to merge dev changes into master
```

### Pull your image to run a local JupyterLab session

```bash
docker compose up
# Do things in JupyterLab w/ files in local directory
docker compose down
```

### Pull image from respository

* From [DockerHub](https://hub.docker.com/r/uwhackweeks/template/tags): `docker pull uwhackweek/template:latest`
* From [Quay](https://quay.io/repository/uwhackweek/template?tab=tags): `docker pull quay.io/uwhackweek/template:latest` 

### Point to a specific tagged image in JupyterHub config

https://zero-to-jupyterhub.readthedocs.io/en/latest/reference/reference.html?highlight=profile_list#singleuser-profilelist
