# GitHub Actions Workflow

The workflow in the [push_pr.yaml](push_pr.yaml) file runs on push and pull requests to the ubuntu-20-04-upgrade branch.
It uses the following reusable workflows in the `reuseable-flows` folder.

+ [lint.yaml](reuseable-flows/lint.yaml)
   This workflow runs the linting with flake8.
+ [buildimage.yaml](reuseable-flows/buildimage.yaml)
   This workflow builds the dockerimages and pushes them to the GHCR.
+ [test.yaml](reuseable-flows/test.yaml)
   This workflow runs the tests inside the uploaded docker images.
+ [buildpackages.yaml]reuseable-flows/(buildpackages.yaml)
   This workflows builds the python and debian packages. It also uploads them to the workflow.
+ [publish_artifacts.yaml](reuseable-flows/publish_artifacts.yaml)
   This workflow uploads the packages to PYPI and Artifactory.