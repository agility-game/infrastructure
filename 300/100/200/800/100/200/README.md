# 200 - Configure Squash TM

1. Optional. Ask your system administrator to [configure a token in the properties file](https://tm-en.doc.squashtest.com/latest/install-guide/install-plugins/configure-plugins-third-party-tools.html#gitlab-integration-token).
2. Follow the [Squash TM documentation](https://tm-en.doc.squashtest.com/latest/admin-guide/configure-xsquash4gitlab/configure-xsquash4gitlab.html) to:
   - a. Create a GitLab server.
   - b. Enable the ```Xsquash4GitLab``` plugin
   - c. Configure a synchronization.
   - d. From the **Real-time synchronization** panel, copy the following fields to use later in GitLab:
       - **Webhook URL**.
       - **Secret token** if your Squash TM system administrator configured one at step 1.
