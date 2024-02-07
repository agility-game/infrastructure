# 100 - Configure GitHub as the source code repository for Gitlab

Based on "GitLab CI/CD for external repositories" at https://docs.gitlab.com/ee/ci/ci_cd_for_external_repos/index.html

**WARNING**: Connecting to a GitHub repository requires a **premium** account for GitLab.

GitLab CI/CD can be used with [GitHub](https://docs.gitlab.com/ee/ci/ci_cd_for_external_repos/github_integration.html), [Bitbucket Cloud](https://docs.gitlab.com/ee/ci/ci_cd_for_external_repos/bitbucket_integration.html), or any other Git server, though there are some [limitations](https://docs.gitlab.com/ee/ci/ci_cd_for_external_repos/index.html#limitations).

Instead of moving your entire project to GitLab, you can connect your external repository to get the benefits of GitLab CI/CD.

Connecting an external repository sets up [repository mirroring](https://docs.gitlab.com/ee/user/project/repository/mirror/index.html) and creates a lightweight project with issues, merge requests, wiki, and snippets disabled. These features [can be re-enabled later](https://docs.gitlab.com/ee/user/project/settings/project_features_permissions.html#configure-project-features-and-permissions).

## 100 - Connect to an external repository

See [README.md](./100/README.md)
