---
description: >-
  To better understand how you’ll be able to manage your applications on the
  platform, there are certain components – entities and concepts – within the
  platform that need to be cleared.
---

# Components

### **Team**

**A group of users working on the same project.** Without an invite to a team, on your first login you must define a team. Later you can invite others to your team, they will have access to every data and components, including configurations and secrets that belong to the team. To limit access to the data of one team, create a new team that'll have its own components.

Teams can have multiple Nodes, Projects and Registries.

### Node

**Nodes are the deployment target environments where either of the agents are installed.** A node can be any cloud or on-premises infrastructure. Without registering a node, your team can't use the platform. We suggest [**registering a node**](../docs/tutorials/register-your-node.md) to be the first step you do after creating your team.

{% hint style="warning" %}
dyrector.io doesn't provide infrastructure. You can use the platform with your already existing infra.
{% endhint %}

Node setups require admin or root privilege. Without that, it's not possible to [**install**](../docs/tutorials/register-your-node.md) the platform's agent on your node.

If you're curious about the install scripts of the agent, you can check them out at the link below:

* [**Docker**](https://github.com/dyrector-io/dyrectorio/blob/develop/web/crux/assets/install-script/install-docker.sh.hbr)
* [**Kubernetes**](https://github.com/dyrector-io/dyrectorio/blob/develop/web/crux/assets/install-script/install-k8s.sh.hbr)

### Registry

**Container registries where the images that you plan to deploy are stored.** You can use any Docker Registry API V2 compatible registry with the platform, including Docker Hub, GitHub, GitLab, Google, Azure registries. Unchecked sources are supported, too, as long as they're V2 compatible. Docker Hub Library is available to every user by default.

### Project

**Projects are the fundamental building blocks of dyrector.io, as these are the deployable units that contains the images with the corresponding configuration.** These are the stacks you’ll manage in dyrector.io. There are two types of Projects, as seen below.

<table><thead><tr><th width="168"> </th><th width="187">Versioned Project</th><th>Versioned Project</th><th width="187">Versionless Project</th></tr></thead><tbody><tr><td><strong>Version Type</strong></td><td>Rolling</td><td>Incremental</td><td>❌</td></tr><tr><td><strong>Rollbacks</strong></td><td>❌</td><td>✅</td><td>❌</td></tr><tr><td><strong>History</strong></td><td>Previous version is overwritten</td><td>Image and configuration inheritance</td><td>❌</td></tr><tr><td><strong>Ideal for</strong></td><td>Nightly Versions</td><td>Production</td><td>Testing, Single-container stacks</td></tr></tbody></table>

* **Versionless Project:** these projects have only one hidden version and cannot be rolled back. These are mostly useful for testing purposes.
* **Versioned Project:** versioned projects can have multiple versions. The different versions can have different configuration and images. Semantic versioning is suggested.

### Deployment

**Deployment is the process of delivering the images that make up a project to the environment you added as a node by installing an agent on it.** You can assign environment and configuration variables to the deployments, and also edit deployments depending on the type of project you want to set up on your node.

{% hint style="info" %}
Each deployed project comes with a prefix. Prefixes are alphanumeric strings in the container names to signal the deployment of a version to a node. Prefixes are comprehended within nodes.

The purpose of this is to avoid duplications of a stack on an environment.
{% endhint %}

#### Versioned project deployment

* **Rolling version**

**Rolling versions have one deployment per version on each node, because a new deployment will overwrite the existing stack on the node. These type of versions can have multiple deployment prefixes since you can deploy them to multiple nodes.** Only `In progress` deployments of rolling versions aren't mutable and deletable. Once the deployment of a rolling version is complete, you can't adjust or delete that.

* **Incremental version**

**You can deploy multiple incremental versions of the same project to a node, therefore different incremental versions can have the same deployment prefix.** The first deployment of an incremental version is mutable as long as it's not `In progress`. Incremental versions can have multiple deployments with the same prefix, but only one of them can have Preparing status. Only In progress deployments can't be deleted. After deploying an incremental version, the deployment will get one of the two statuses below:

**Successful:** successful deployments remain immutable. After successful deployments, you can roll back the previous version with the corresponding database.

New successful deployments turn previous ones that belong to older versions `obsolete`. When a previous version gets rolled back, the deployment that belongs to it turns all the deployments coming after `downgraded`.

**Failed:** if a deployment comes back failed, it can be mutable.

#### Versionless project deployment

Versionless projects come without a version. The purpose of versionless projects is to reduce infrastructure maintenance overhead.

Use cases:

* Messaging queues: RabbitMQ, MQTT, etc.
* Proxies: Traefik, NGINX, etc.
* Databases: Postgres, MySQL, etc.

{% hint style="info" %}
**Protected deployments**

There are protected deployments that prevent you from overwriting your deployments from another project. This is a helpful measure when you manage dozens or hundreds of environments, and a misplaced click can hurt your users by an outage.

* **Rolling versions:** You can't deploy it if a protected deployment exists with the same prefix on the node.
* **Incremental versions:** You can't deploy it if a protected deployment exists of a different version with the same prefix on the node.
{% endhint %}

### Audit log

Audit logs collect team activity. It lists executed actions, the users who initiated them and the time of when the actions happened.

Logs are assigned to teams.

### Profile

Your user profile. One profile can belong to multiple teams.
