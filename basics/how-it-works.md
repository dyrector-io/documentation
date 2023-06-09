# How it works

dyrector.io consists of 2 major components:

* **an agent** that's installed on your environment where you want to deploy images – crane is the agent that communicates with Kubernetes API and dagent is the agent for communication with Docker API, both written in Go –,
* **and a platform** (UI developed in React.js, Next.js. Backend developed in Node.js, Nest.js). Communication between the agents and the platform takes place in gRPC with TLS encryption. The data is managed in a PostgreSQL database mapped by Prisma ORM.

### dyrector.io cloud (alpha access)

![](../docs/.gitbook/assets/dyrector-io-cloud-hosted-architecture-dark.png)

{% hint style="warning" %}
Alpha is suggested for non-production purposes. If you want to use it for production, reach out to us at [**hello@dyrector.io**](mailto:hello@dyrector.io).
{% endhint %}

### Self-managed

![](../docs/.gitbook/assets/dyrector-io-self-hosted-architecture-dark.png)

Self-hosted dyrector.io is free and will always be, without feature and usage restrictions.

![](https://static.scarf.sh/a.png?x-pxid=04316d37-a90c-4df6-9ca9-cc75bd843ba9)
