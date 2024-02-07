# 100 - Connect to an external repository

To connect to an external repository (here: GitHub) from within GitLab:

1. In GitLab: On the left sidebar, at the top, select **Create new (+)** and **New project/repository**.
2. In GitLab: Select **Run CI/CD for external repository**.

If the **Run CI/CD for external repository** option is not available, the GitLab instance might not have any import sources configured. Ask an administrator for your instance to check the import sources configuration.

3. In GitLab: Select **GitHub**.
4. In GitLab: You will be prompted to enter a **Personal Access Token**. To connect to GitHub repositories, you must first authorize GitLab to access your GitHub repositories. Create and provide your GitHub [personal access token](https://github.com/settings/tokens?type=beta). **NOTE**: We choose ```Fine-grained tokens```.
5. In Github: For **Token name** enter ```Agility-Game Home PAT```. For **Expiration** choose ```Custom``` end set the date to the last day (here: 31 December) of the current year, so we know when to extend our access tokens. For **Description** enter ```Agility Game Home Personal Access Token```. For **Resource owner** choose ```agility-game```. For **Repository access** choose ```Only select repositories``` and pick ```agility-game/home```. For **Permissions**, for **Commit Status** enter ```Read-only```, for **Contents** enter ```Read-only```, for **Discussions** enter ```Read-only```, for **Issues** enter ```Read-only```, for **Metadata** (mandatory) enter ```Read-only```, for **Pages** enter ```Read-only```, for **Pull requests** enter ```Read-only```. Please note, ```admin``` access is not required. **IMPORTANT**: Copy its value (github_pat_*****************************************) to a safe place for later use.
6. In GitLab: After having created the Personal Access Token in GitHub, enter its value (github_pat_*****************************************) into the input field in GitLab. Click **Authenticate**.
7. In GitLab: You will be prompted ```Import repositories from GitHub```. Switch to the tab **Collaborated**. Untick the checkboxes under **Advanced import settings**, especially uncheck ```Import collaborators``` as they consume seats on our GitLab instance, which is costly.
8. Choose the following:
   | From GitHub | To GitLab |
   | -- | -- |
   | agility-game/home | agility-game/home |
9. Click **Connect**
