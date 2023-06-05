# How it works

dyrector.io consists of an agent – crane for Kubernetes API and dagent for Docker API, both written in Go – and a platform (UI developed in React.js, Next.js. Backend developed in Node.js, Nest.js). Communication between the agents and the platform takes place in gRPC with TLS encryption. The data is managed in a PostgreSQL database which we use with Prisma ORM.

### Cloud-hosted dyrector.io (alpha access)

![](../docs/.gitbook/assets/dyrector-io-cloud-hosted-architecture-dark.png)

{% hint style="warning" %}
dyrector.io alpha is suggested for non-production purposes. If you want to use dyrector.io for production, reach out to us at [**hello@dyrector.io**](mailto:hello@dyrector.io).
{% endhint %}

### Self-managed dyrector.io

![](../docs/.gitbook/assets/dyrector-io-self-hosted-architecture-dark.png)

Self-hosted dyrector.io is free and will always be, without feature and usage restrictions.

![](https://static.scarf.sh/a.png?x-pxid=04316d37-a90c-4df6-9ca9-cc75bd843ba9)
