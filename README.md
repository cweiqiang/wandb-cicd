# wandb-cicd

- Small change to test pull request from VSCode to Github

[Weights-and-Biases-CICD-tutorial](https://www.wandb.courses/courses/take/ci-cd-for-machine-learning/lessons)

These are resources for CICD
See here for sample yaml files for [Github actions workflows](https://github.com/fastai/fastai/tree/master/.github/workflows)

- See Github Actions Quickstart and various sections [here](https://docs.github.com/en/actions/quickstart)

  - Essential [Features of Github Actions](https://docs.github.com/en/actions/learn-github-actions/essential-features-of-github-actions)

  - [Expressions](https://docs.github.com/en/actions/learn-github-actions/expressions)

  - [Contexts](https://docs.github.com/en/actions/learn-github-actions/contexts) e.g. github.event

  - [Variables](https://docs.github.com/en/actions/learn-github-actions/contexts#github-context)

  - [Workflow Billing](https://docs.github.com/en/actions/learn-github-actions/workflow-billing)

For code debugging, refer to payload in chatops.yaml output

```jobs:
  see-comment:
    # this filters for only comments made on a pull request
    if: (github.event.issue.pull_request != null)
    runs-on: ubuntu-latest
    steps:
    - name: see payload # this step is for debugging purposes only, so you can see the payload. 
      run: echo "PAYLOAD:\n${PAYLOAD}\n"
      env:
        PAYLOAD: ${{ toJSON(github.event) }}```
