# 300 - Trigger an update by using the API

Pull mirroring uses polling to detect new branches and commits added upstream, often minutes afterwards. You can notify GitLab using an [API call](https://docs.gitlab.com/ee/api/projects.html#start-the-pull-mirroring-process-for-a-project), but the [minimum interval for pull mirroring limits](https://docs.gitlab.com/ee/user/project/repository/mirror/index.html#force-an-update) is still enforced.

For more information, read [Start the pull mirroring process for a project](https://docs.gitlab.com/ee/api/projects.html#start-the-pull-mirroring-process-for-a-project).
