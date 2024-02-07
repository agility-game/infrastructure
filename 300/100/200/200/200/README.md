# 200 - Configure pull mirroring

Prerequisites:

If your remote repository is on GitHub and you have two-factor authentication (2FA) configured, create a personal access token for GitHub with the repo scope. If 2FA is enabled, this personal access token serves as your GitHub password.
GitLab Silent Mode is not enabled.
On the left sidebar, select Search or go to and find your project.
Select Settings > Repository.
Expand Mirroring repositories.
Enter the Git repository URL.

To mirror the gitlab repository, use gitlab.com:gitlab-org/gitlab.git or https://gitlab.com/gitlab-org/gitlab.git.
In Mirror direction, select Pull.
In Authentication method, select your authentication method. For more information, see Authentication methods for mirrors.
Select any of the options you need:
Overwrite diverged branches
Trigger pipelines for mirror updates
Only mirror protected branches
To save the configuration, select Mirror repository.

== WE ARE HERE ==

## 100 - Overwrite diverged branches

See [README.md](./100/README.md)

## 200 - Trigger pipelines for mirror updates

See [README.md](./200/README.md)
