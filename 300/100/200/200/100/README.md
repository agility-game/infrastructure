# 100 - How pull mirroring works

After you configure a GitLab repository as a pull mirror:

1. GitLab adds the repository to a queue.
2. Once per minute, a Sidekiq cron job schedules repository mirrors to update, based on:
  - Available capacity, determined by Sidekiq settings. For GitLab.com, read [GitLab.com Sidekiq settings](https://docs.gitlab.com/ee/user/gitlab_com/index.html#sidekiq).
  - How many mirrors are already in the queue and due for updates. Being due depends on when the repository mirror was last updated, and how many times updates have been retried.
3. Sidekiq becomes available to process updates, mirrors are updated. If the update process:
  - **Succeeds**: An update is enqueued again with at least a 30 minute wait.
  - **Fails**: The update is attempted again later. After 14 failures, a mirror is marked as a [hard failure](https://docs.gitlab.com/ee/user/project/repository/mirror/pull.html#fix-hard-failures-when-mirroring) and is no longer enqueued for updates. A branch diverging from its upstream counterpart can cause failures. To prevent branches from diverging, configure [Overwrite diverged branches](https://docs.gitlab.com/ee/user/project/repository/mirror/pull.html#overwrite-diverged-branches) when you create your mirror.
