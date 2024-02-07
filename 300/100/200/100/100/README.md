# 100 - Connect to an external repository

To connect to an external repository from within GitLab:

1. On the left sidebar, at the top, select **Create new (+)** and **New project/repository**.
2. Select **Run CI/CD for external repository**.

If the **Run CI/CD for external repository** option is not available, the GitLab instance might not have any import sources configured. Ask an administrator for your instance to check the import sources configuration.

3. Select **GitHub**.
4. You will be prompted to enter a **Personal Access Token**. To connect to GitHub repositories, you must first authorize GitLab to access your GitHub repositories. Create and provide your GitHub [personal access token](https://github.com/settings/tokens?type=beta). **NOTE**: We choose ```Fine-grained tokens```. You must select the following scopes: **repo**: Used to display a list of your public and private repositories that are available to connect to. Let's name our GitHub Personal Access Token: ```Agility-Game Home PAT```. After entering it into the input field, click **Authenticate**.
