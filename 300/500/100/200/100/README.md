# 100 - Connect with a Personal Access Token

Personal access tokens can only be used to connect GitHub.com repositories to GitLab, and the GitHub user must have the [owner role](https://docs.github.com/en/get-started/learning-about-github/access-permissions-on-github).

To perform a one-off authorization with GitHub to grant GitLab access your repositories:

1. In GitHub, create a token:
   
  - a. Open [https://github.com/settings/tokens/new](https://github.com/settings/tokens/new). **NOTE**: Nowadays, choose the ```Fine-grained tokens```, instaed of the ```Tokens (classic)```.
  
  - b. Create a Personal Access Token by clicking **Generate new token**.
  
  - c. Enter a **Token description** (here: ```Agility-Game Agility-Game PAT```) with as the Resource owner **agility-game** with an expiration to the end of the current year (hence: 12/31/2025) and a description of ```Personal Access Token (PAT) for GitLab Agility-Game project's Agility-Game subproject.```. Set the repository access to **only select repositories** and choose ```agility-game/agility-game```.
    
  - d. For Repository Permissions set (other than the default values):
    - Actions: Access: **Read and write**
    - Commit statuses: Access: **Read and write** to update commit statuses
    - Metadata: Access: **Read-only**
    - Webhooks: Access: **Read and write** to notify GitLab of new commits
       
  - e. For Organization Permissions keep with the default values.

After creating the Personal Access Token, make sure to safe its value somewhere where it can be retrieved alter, but kept from prying eyes.

2. In GitLab, enter the Personal Access Token from GitHub:
  - a. On the [Agility Game](https://gitlab.com/agility-game) group page, click on **Settings**, followed by **Projects**.
  - b. Click on **New project**.
  - c. Choose **Run CI/CD for external repository**.
  - d. Click **GitHub**
  - e. Enter the **Personal Access Token** from GitHub, created in step 1 (named: ```Agility-Game Agility-Game PAT```).
  - f. Click **Authenticate**.
  - g. On the [Import repositories from GitHub](https://gitlab.com/import/github/status) page, choose the **Collaborated** tab.
  - h. Pick the From Github **agility-game/agility-game** line and choose **Import**. **NOTE**: If this repository is not listed, make sure that you (here: wvanheemstra) as you are known in GitLab are a collaborator of the repository in GitHub.
  - 
Select Run CI/CD for external repository.
Select GitHub.
For Personal access token, paste the token.
Select List Repositories.
Select Connect to select the repository.


MORE 
