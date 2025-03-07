---
title: Automatic Git Provisioning
description: Automatically provision a Git repository when a project is created.
weight: 20
keywords: [git provisioning]
aliases:
  - /docs/0.18.x/api/git_provisioning
---


### Description

Keptn provides an extension point that can be used to automatically provision a Git repository.
When a project is created, Keptn performs a call to the service that adheres to a specific HTTP REST interface. The swagger documentation for this API can be found [here](../../../../api/).

Keptn calls the service that implements such interface passing the project name and the namespace in which Keptn is currently running. The service is expected to answer with the URL, username, and token to access the repository. Keptn uses this information to configure the upstream repository for the project.
Similarly, when a project is deleted, Keptn calls the service implementing such an API. This can be used to deprovision the repository and perform clean up actions.

This feature is enabled via the Helm value [`control-plane.features.automaticProvisioningURL`](https://github.com/keptn/keptn/blob/0.18.0/installer/manifests/keptn/charts/control-plane/values.yaml#L26). This value must contain the base URL of the service that implements the interface.

---

### Available Provisioners

- [Gitea](https://github.com/keptn-sandbox/keptn-gitea-provisioner-service)
- Help us add more by [creating an issue](https://github.com/keptn/integrations/issues/new?assignees=&labels=integrations&template=integration_template.yaml&title=%5Bintegration%5D+) and / or filing a Pull Request.

]---

### Resources

[Swagger Documentation](../../../../api/)
