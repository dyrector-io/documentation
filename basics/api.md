# API

### Registries

Registries are 3rd party registries where the images of versions are located. Learn more about registries [**here**](../docs/tutorials/add-your-registry/).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/registries" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/registries" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/registries/{registryId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/registries/{registryId}" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/registries/{registryId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Projects

There are two kinds of projects in dyrector.io: versionless and versioned. Versionless projects make up one deployable unit without versioning, while versioned projects come with multiple rolling or incremental versions. More details [**here**](../docs/tutorials/create-your-product/).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/convert" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Versions

Versions belong to versioned projects. Versionless projects act similar to a rolling version of a versioned project.

The purpose of versions is to separate different variations of your project. They can be either rolling or incremental. One versionless project can have multiple versions of both types. More details about rolling and incremental versions [**here**](../docs/tutorials/create-your-product/create-a-complex-product/).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}/default" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}/increase" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Version/Images

Images make up a versioned project's version, or a versionless project.

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}/images" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}/images" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}/images/{imageId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}/images/{imageId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}/images/{imageId}" method="patch" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/projects/{projectId}/versions/{versionId}/images/order" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Teams

Teams are the shared entity of multiple users. The purpose of teams is to separate users, nodes and projects based on their needs within an organization. Team owners can assign roles. More details about teams [**here**](components.md#team).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams/{teamId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams/{teamId}" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams/{teamId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams/{teamId}/users" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams/{teamId}/users/{userId}/role" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams/{teamId}/users/leave" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams/{teamId}/users/{userId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/teams/{teamId}/users/{userId}/reinvite" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Users/Me

Users/Me cover endpoints related to your user profile.

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/users/me" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/users/me/invitations/{teamId}" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/users/me/invitations/{teamId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/users/me/preferences/onboarding" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/users/me/preferences/onboarding" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Deployments

Deployments are the process that gets the installation of your versions or versionless projects done on the node of your choice. More details about deployments [**here**](../docs/tutorials/deploy-your-product.md).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}" method="patch" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}/instances/{instanceId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}/instances/{instanceId}" method="patch" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}/instances/{instanceId}/secrets" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}/start" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}/copy" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}/log" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}/token" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/deployments/{deploymentId}/token" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Tokens

Tokens are the access tokens that grant you access to a user profile and the teams the profile is a member of.

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/tokens" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/tokens" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/tokens/{tokenId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/tokens/{tokenId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Nodes

Nodes are the deployment targets. Nodes are registered by installing at least one of the agents – crane for Kubernetes, dagent for Docker. These agents connect the platform to your node. One team can have as many nodes as they like.

Node installation takes place with Shell or PowerShell scripts, which can be created or revoked. More details [**here**](../docs/tutorials/register-your-node.md).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/script" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/script" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/script" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/token" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/update" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/audit" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/{prefix}/containers/{name}/start" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/{prefix}/containers/{name}/stop" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/{prefix}/containers/{name}/restart" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/{prefix}/containers" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/{prefix}/containers/{name}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/containers" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/containers/{name}/start" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/containers/{name}/stop" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/containers/{name}/restart" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/nodes/{nodeId}/containers/{name}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Audit log

Audit log is a log of team activity generated by the platform.

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/audit-log" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Health

Health refers to the status of the different services that make up the platform. It can be checked to see if the platform works properly.

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/health" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Notifications

Notifications are chat notifications in Slack, Discord, and Teams. They send an automated message about deployments, new versions, new nodes, and new users. More details [**here**](../docs/tutorials/create-chat-notifications.md).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/notifications" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/notifications" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/notifications/{notificationId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/notifications/{notificationId}" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/notifications/{notificationId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/notifications/{notificationId}/test" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Templates

Templates are preset applications that can be turned into a project right away. They can be deployed with minimal configuration. More details about templates [**here**](../features/templates/).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/templates" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/templates" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/templates/{templateId}/image" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Dashboard

Dashboard summarizes the latest activities of a team.

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/dashboard" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

### Storages

Storages are S3 compatible memory storages. They can be used for file injection. More details [**here**](../features/storage.md).

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/storages" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/storages" method="post" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/storages/options" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/storages/{storageId}" method="get" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/storages/{storageId}" method="put" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}

{% swagger src="../.gitbook/assets/dyrectorio-api-0-7-0.json" path="/api/{teamSlug}/storages/{storageId}" method="delete" %}
[dyrectorio-api-0-7-0.json](../.gitbook/assets/dyrectorio-api-0-7-0.json)
{% endswagger %}
