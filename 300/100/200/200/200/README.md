# 200 - Configure pull mirroring

Prerequisites:

- If your remote repository is on GitHub and you have [two-factor authentication (2FA) configured](https://docs.github.com/en/authentication/securing-your-account-with-two-factor-authentication-2fa), create a [personal access token for GitHub](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) as explained in previous section. If 2FA is enabled, this personal access token serves as your GitHub password.
- [GitLab Silent Mode](https://docs.gitlab.com/ee/administration/silent_mode/index.html) is not enabled.
  
1. On the left sidebar, select **Search or go to** and find your project.
2. Select **Settings > Repository**.
3. Expand **Mirroring repositories**.
4. Enter the **Git repository URL**.

**INFO**: To mirror the ```gitlab``` repository, use ```gitlab.com:agility-game/home.git``` or ```https://gitlab.com/agility-game/home.git```.

5. In **Mirror direction**, select **Pull**.
6. In **Authentication method**, select your authentication method. For more information, see [Authentication methods for mirrors](https://docs.gitlab.com/ee/user/project/repository/mirror/index.html#authentication-methods-for-mirrors).
7. Select any of the options you need:
  - **[Overwrite diverged branches](https://docs.gitlab.com/ee/user/project/repository/mirror/pull.html#overwrite-diverged-branches)**
  - **[Trigger pipelines for mirror updates](https://docs.gitlab.com/ee/user/project/repository/mirror/pull.html#trigger-pipelines-for-mirror-updates)**
  - **Only mirror protected branches**
8. To save the configuration, select **Mirror repository**.

## 100 - Overwrite diverged branches

See [README.md](./100/README.md)

## 200 - Trigger pipelines for mirror updates

See [README.md](./200/README.md)

== WE ARE HERE ==
