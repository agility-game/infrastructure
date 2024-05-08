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
8. In GitLab: Choose the following:
   | From GitHub | To GitLab |
   | -- | -- |
   | agility-game/home | agility-game/home |
   
   **NOTE**: If agility-game/home is not listed, make sure in GitHub [agility-game/home](https://github.com/agility-game/home/settings/access) to have added ```wvanheemstra``` as 1 member under **Direct Access** with Role:**Admin**, by clicking **Add people** and search for ```wvanheemstra```. If a repository with the same group and project is in a ```pending deletion``` status, you need to wait for it to have been deleted.
10. In GitLab: Click **Connect**.
11. In GitLab: If in the column **Status** the value is green and labelled **Complete**, the GitHub repository has successfully been connected to Gitlab.
12. In GitLab: Visit https://gitlab.com/agility-game/home to see it.
13. In GitLab: If you see a banner that states: ```You can't push or pull repositories using SSH until you add an SSH key to your profile.```, push the button **Add SSH key** and follow the instructions.
14. In GitLab: If you see a banner that states: ```Your account is authenticated with SSO or SAML. To push and pull over HTTPS with Git using this account, you must set a password or set up a Personal Access Token to use instead of a password. For more information, see Clone with HTTPS.```, click the link **set up a Personal Access Token** and follow the instructions.

**NOTE**: Gitlab allows [automatic mirroring](https://docs.gitlab.com/ee/workflow/repository_mirroring.html) but it appears to be a [paid](https://about.gitlab.com/pricing/) feature.

Navigate to your project’s Settings > Repository and expand the Mirroring repositories section (only seen if you have a paid for version).

- Enter a repository URL. For example: ```https://github.com/agility-game/home```

- Select **Pull** from the Mirror direction dropdown.

- Select an authentication method from the Authentication method dropdown, if necessary.

- If necessary, check the following boxes:

- - Overwrite diverged branches.

- - Trigger pipelines for mirror updates.

- - Only mirror protected branches.

- Click the Mirror repository button to save the configuration.
