# 200 - Trigger pipelines for mirror updates

If this option is enabled, pipelines trigger when branches or tags are updated from the remote repository. Depending on the activity of the remote repository, this may greatly increase the load on your CI runners. Only enable this feature if you know they can handle the load. CI uses the credentials assigned when you set up pull mirroring.
