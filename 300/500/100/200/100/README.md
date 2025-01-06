# 100 - Connect with a Personal Access Token

Personal access tokens can only be used to connect GitHub.com repositories to GitLab, and the GitHub user must have the [owner role](https://docs.github.com/en/get-started/learning-about-github/access-permissions-on-github).

To perform a one-off authorization with GitHub to grant GitLab access your repositories:

1. In GitHub, create a token:
  a. Open [https://github.com/settings/tokens/new](https://github.com/settings/tokens/new).
  b. Create a personal access token.
  c. Enter a **Token description** and update the scope to allow ```repo``` and ```admin:repo_hook``` so that GitLab can access your project, update commit statuses, and create a web hook to notify GitLab of new commits.




MORE 