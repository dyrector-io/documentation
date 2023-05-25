---
description: >-
  To better understand how you’ll be able to manage your applications in
  dyrector.io, there are certain components – entities and concepts – within the
  platform that need to be cleared.
---

# Components

### **Team**

A group of users working on the same project. On your first login you must define a team, to which you can invite your teammates’ profiles who will have access to every data & components, including configurations and secrets that belong to the team. To limit access to the data of one team, create a new team that'll have its own components.

Teams can have multiple Nodes and Registries.

### Node

Nodes are the deployment targets provided by you. They can be Docker, Kubernetes, even on-premises environments; it really depends on your needs. Specifying at least one Node is a basic requirement of both using dyrector.io and deploying your application. For this reason, we suggest this should be the first step you do after creating your team.

{% hint style="warning" %}
dyrector.io doesn't provide infrastructure. You can use the platform with your already existing cloud or on-premises infrastructure.
{% endhint %}

Node setups require admin or sudo privilege. Without that, it's not possible to [**install**](../tutorials/register-your-node.md) dyrector.io's agent on your node in the case of both Docker and Kubernetes.

If you're curious about the install scripts of the agent, you can check them out at the link below:

* [**Docker**](https://github.com/dyrector-io/dyrectorio/blob/develop/web/crux/install-docker.sh.hbr)
* [**Kubernetes**](https://github.com/dyrector-io/dyrectorio/blob/develop/web/crux/install-k8s.sh.hbr)

### Registry

Registry is the place where you can store your images. You can use any Docker Registry API V2 compatible Registry with dyrector.io, and besides them GitHub and GitLab Registries. Docker Hub Library is available to every user by default.

### Product

These are the applications you’ll manage in dyrector.io. There are two types of Products.

<table><thead><tr><th> </th><th width="187">Simple Product</th><th width="187">Complex Product</th><th>Complex Product</th></tr></thead><tbody><tr><td><strong>Version</strong></td><td>❌</td><td>Rolling</td><td>Incremental</td></tr><tr><td><strong>Rollbacks</strong></td><td>❌</td><td>✅</td><td>✅</td></tr><tr><td><strong>Ideal for</strong></td><td>Testing</td><td>Continuous Delivery</td><td>Production</td></tr></tbody></table>

* **Simple:** these Products have only one version and cannot be rolled back. These are mostly useful for testing purposes, because simple Products come without versions.
* **Complex:** complex Products have two types of versions: Rolling and Incremental.
  * **Rolling Versions:** rolling versions are similar to simple Products except they’re perfect for continuous delivery. They’re always mutable but contrary to incremental Products they aren’t hierarchic and lack a version number.
  * **Incremental Versions:** incremental Products are hierarchical. They can have a child version and once a deployment is successful, the deployed versions, the environment variables, and the deployed images can never be modified. This guarantees you’re able to roll back the deployed version and reinstate the last functional one if any error occurs to avoid downtime.

Regardless of the type of product you want to manage, you can pick the images you want to include in the managed version and also specify configurations that belong to them.

### Deployment

After assembling your product, you can trigger a deployment to a Node. Users can assign environment and configuration variables to the deployments, and can edit deployments depending on the type and version of Product they want to deploy.

Each deployed version comes with a prefix. Prefixes are alphanumeric strings in the container names to signal the deployment of a version to a node. Prefixes are comprehended within nodes.

#### Simple Product Deployment

Simple products have 1 rolling version. The purpose of Simple products is to reduce infrastructure maintenance overhead.

Use cases:

* Messaging queues: RabbitMQ, MQTT, etc.
* Proxies: Traefik, NGINX, etc.
* Databases: Postgres, MySQL, etc.

#### Complex Product Deployment

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
