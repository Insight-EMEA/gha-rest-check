---
title: DevOps Checklist
labels: enhancement
---
## Design
- [ ] [Follow the naming conventions in naming your repository](https://github.com/Insight-EMEA/github-getting-started/wiki/creating-repositories#naming-conventions)
- [ ] [Add a good About section that briefly explains what the project is about](https://github.com/Insight-EMEA/github-getting-started/wiki/creating-repositories)
- [ ] [Override the Languages section if it doesn’t match the right Languages used](https://github.com/github/linguist/blob/master/docs/overrides.md)
- [ ] Fill in the README file in the root of your repository to give much more details about your project
- [ ] Create a team in Github teams
- [ ] [Set the CODEOWNERS file and use the new team you just created](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners). [Example](./CODEOWNERS)
- [ ] [Create a branch protection policy for your main branch](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/managing-a-branch-protection-rule)
- [ ] Infrastructure should always be scripted, and be managed in the same way as the application code.

## Develop
- [ ] Create a .gitignore file according to your project and framework used. [A collection of gitignore files for common languages](https://github.com/github/gitignore).
- [ ] Always use feature branches rather than attempting to directly update the main branch
- [ ] Follow the checklist in the Pull request template.
- [ ] Follow the Git policies that is agreed by the team (merge, squash, rebase)
- [ ] Make sure to delete the feature branch when its merged to the main branch

## Build
- [ ] Create CI workflows to cover every aspect of your project; IAC, projects, code, etc.
- [ ] Ensure that the CI workflows are guarding your main branch
- [ ] If your repository has multiple projects or frameworks, create separate CI workflows for them.
- [ ] [Make sure that the right workflow is running according to the file or folder updated whenever a PR is raised](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#example-including-and-excluding-paths).
- [ ] [Always create an artifact as an output after building the main branch to be used in the CD pipelines](https://docs.github.com/en/actions/using-workflows/storing-workflow-data-as-artifacts#uploading-build-and-test-artifacts).
- [ ] [Always version your artifacts and publish to GitHub releases](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository)

## Test
- [ ] [Include Unit testing in your CI pipelines](https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-net)
- [ ] [If GHAS is enabled, make sure that the right language is used in the workflow](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/configuring-the-codeql-workflow-for-compiled-languages)
- [ ] Fail the Pull Request if the unit test doesn’t pass

## Deploy
- [ ] [Create GitHub Environments to represent your Environments (DEV, TEST, Prod)](https://github.com/Insight-EMEA/github-getting-started/wiki/Environments)
- [ ] Add policies to protect your GitHub environment from unwanted promotions.
- [ ] Have a universal CD pipeline that deploys your artifacts into your environments
- [ ] Always test to deploy the whole environment starting from zero to uncover the DR scenarios.

## Operate and Monitor
- [ ] [GitHub Insights and Security tabs should always be monitored for security flaws](https://docs.github.com/en/code-security/getting-started/securing-your-repository).
- [ ] [Dependabot Alerts should be monitored continously for updates and security issues](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/about-dependabot-alerts).
- [ ] Always make sure that your main branch's CI workflow is always green!

## Security
- [ ] [Save Environment related configurations in Environment Secrets like Azure_Credentials](https://github.com/Insight-EMEA/github-getting-started/wiki/Environments#creating-an-environment)
- [ ] [Protect your sensitive environments like prod with environment policies](https://docs.github.com/en/actions/deployment/targeting-different-environments/using-environments-for-deployment#environment-protection-rules)
- [ ] [Enable GitHub Advanced Security features whenever possible](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security)
- [ ] [Enable GitHub code scanning push protection rules](https://docs.github.com/en/enterprise-cloud@latest/code-security/secret-scanning/protecting-pushes-with-secret-scanning)
