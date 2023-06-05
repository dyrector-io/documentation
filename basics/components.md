---
description: >-
  To better understand how you’ll be able to manage your applications in
  dyrector.io, there are certain components – entities and concepts – within the
  platform that need to be cleared.
---

# Components

### **Team**

A group of users working on the same project. Without an invite to a team, on your first login you must define a team. Later you can invite others to your team, they will have access to every data and components, including configurations and secrets that belong to the team. To limit access to the data of one team, create a new team that'll have its own components.

Teams can have multiple Nodes, Projects and Registries.

### Node

Nodes are the deployment targets. A node can be any cloud or on-premises infrastructure. Without registering a node, your team can't use dyrector.io. We suggest [**registering a node**](../docs/tutorials/register-your-node.md) to be the first step you do after creating your team.

{% hint style="warning" %}
dyrector.io doesn't provide infrastructure. You can use the platform with your already existing infra.
{% endhint %}

Node setups require admin or sudo privilege. Without that, it's not possible to [**install**](../docs/tutorials/register-your-node.md) dyrector.io's agent on your node.

If you're curious about the install scripts of the agent, you can check them out at the link below:

* [**Docker**](https://github.com/dyrector-io/dyrectorio/blob/develop/web/crux/install-docker.sh.hbr)
* [**Kubernetes**](https://github.com/dyrector-io/dyrectorio/blob/develop/web/crux/install-k8s.sh.hbr)

### Registry

Container registries where the images that you plan to deploy are stored. You can use any Docker Registry API V2 compatible registry with dyrector.io, including Docker Hub, GitHub, GitLab, Google, Azure registries. Undefined sources are supported, too, as long as they're V2 compatible. Docker Hub Library is available to every user by default.

### Project

These are the applications you’ll manage in dyrector.io. There are two types of Projects.

<table><thead><tr><th width="168"> </th><th width="187">Versionless Project</th><th width="187">Versioned Project</th><th>Versioned Project</th></tr></thead><tbody><tr><td><strong>Version</strong></td><td>❌</td><td>Rolling</td><td>Incremental</td></tr><tr><td><strong>Rollbacks</strong></td><td>❌</td><td>❌</td><td>✅</td></tr><tr><td><strong>Ideal for</strong></td><td>Testing</td><td>Continuous Delivery</td><td>Continuous Delivery</td></tr></tbody></table>

* **Versionless Project:** these projects have only one hidden version and cannot be rolled back. These are mostly useful for testing purposes.
* **Versioned Project:** versioned projects can have multiple versions. The different versions can have different configuration and images. Versioning is suggested to be done in a semantic way.

### Deployment

After assembling your project, you can trigger a deployment to a node. Users can assign environment and configuration variables to the deployments, and can edit deployments depending on the type of project they want to deploy.

Each deployed project comes with a prefix. Prefixes are alphanumeric strings in the container names to signal the deployment of a version to a node. Prefixes are comprehended within nodes.

#### Versionless project deployment

Simple products have one abstracted away rolling version. The purpose of Simple products is to reduce infrastructure maintenance overhead.

Use cases:

* Messaging queues: RabbitMQ, MQTT, etc.
* Proxies: Traefik, NGINX, etc.
* Databases: Postgres, MySQL, etc.

#### Versioned project deployment

* **Rolling version**

Rolling versions have one deployment per version but they can have multiple prefixes since they can be deployed to different nodes. A rolling version can be deployed to one node with the same prefix just once. If another Rolling version needs to be deployed again, then dyrector.io won't create another one. Only In progress deployments aren't mutable and deletable.

* **Incremental version**

First made deployments remain mutable as long as they're not under In progress status. Incremental versions can have multiple deployments with the same prefix, but only one of them can have Preparing status. Only In progress deployments can't be deleted. After deploying the Incremental version, the deployment will get one of the two statuses below:

**Successful:** successful deployments remain immutable. Following successful deployments, the previous versions will be able to rolled back still with the corresponding database.

New successful deployments turn previous ones that belong to older versions obsolete. When a previous version gets rolled back, the deployment that belongs to the rolled back version turns all the deployments coming after downgraded.

**Failed:** if a deployment comes back failed, it can be mutable.

### Audit log

Audit logs collect team activity. It lists executed actions, the users who initiated them and the time of when the actions happened.

Logs are assigned to teams.

### Profile

Your user profile on dyrector.io. One profile can belong to multiple teams.
