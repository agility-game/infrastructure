# 200 - Pull in GitLab from a remote GitHub repository

Based on "Pull from a remote repository" at https://docs.gitlab.com/ee/user/project/repository/mirror/pull.html

**WARNING**: This feature requires a **premium** subscription with GitLab.

You can use the GitLab interface to browse the content and activity of a repository, even if it isn’t hosted on GitLab. Create a pull [mirror](https://docs.gitlab.com/ee/user/project/repository/mirror/index.html) to copy the branches, tags, and commits from an upstream repository (in GitHub) to yours (in GitLab).

Unlike [push mirrors](https://docs.gitlab.com/ee/user/project/repository/mirror/push.html), pull mirrors retrieve changes from an upstream (remote, here GitHub) repository on a scheduled basis. To prevent the mirror from diverging from the upstream repository, **don’t push commits directly to the downstream (here: GitLab) mirror**. Push commits to the upstream (here: GitHub) repository instead. Changes in the remote (here: GitHub) repository are pulled into the GitLab repository:

- Automatically, 30 minutes after a previous pull. This cannot be disabled.
- When an administrator [force-updates the mirror](https://docs.gitlab.com/ee/user/project/repository/mirror/index.html#force-an-update).
- When an [API call triggers an update](https://docs.gitlab.com/ee/user/project/repository/mirror/pull.html#trigger-an-update-by-using-the-api).

UI and API updates are subject to default [pull mirroring intervals](https://docs.gitlab.com/ee/administration/instance_limits.html#pull-mirroring-interval) of 5 minutes. This interval can be configured by self-managed instances.

By default, if any branch or tag on the downstream pull mirror diverges from the local repository, GitLab stops updating the branch. This prevents data loss. Deleted branches and tags in the upstream repository are not reflected in the downstream repository.



== WE ARE HERE ==
