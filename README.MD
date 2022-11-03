## About reusable workflows
> IMPORTANT: This repo need to be public to start using owned reusable workflows (we dont store any sensitive data in this repo, only reusable steps of our pipelines)

To avoid code duplication of GitHub Actions workflow files across thousands of repositories, we utilize reusable workflows. This allows us to DRY (don't repeat yourself) configurations, so we don't have to copy and paste workflows from one repository to another.

## Calling reusable workflows
In the calling workflow file, use the uses property to specify the location and version of a reusable workflow file to run as a job.

```sh
name: Sample workflow
on:
  pull_request:
jobs:
  CI:
    uses: Lattice-Trade/membrane-github-template-actions/.github/workflows/{reusable-workflow-name}@main
    with:
        INPUT_1: xxx
        INPUT_2: xxx
    secrets:
        SECRET_1: ${{ secrets.XXXX }}
```
> replace {reusable-workflow-name} to the respective reusable workflow
