# Use cases

### Self-service container management

The platform abstracts away interactions with containers. You can deploy images, start, restart, and delete containers with the platform. Logs and container inspection allows you to dig deeper into a container's operation when needed.

### Self-hosted stacks for indie hackers

If you're passionate about self-hosting the tools you use every day, you can add all of your environments to the platform as nodes, where you can manage all the containers you run. Instead of setting up dashboards and adding each service individually, you can interact with all of your ecosystem through one GUI.

{% hint style="success" %}
Pro tip: you can [**self-manage dyrector.io**](broken-reference), too.
{% endhint %}

### Multi-Instance Deployments

The key purpose of multi-instance deployments is to avoid repetitive tasks when the same stack needs to be deployed to dozens or hundreds of deployment targets. After configuring the stack once, you're able to select all the nodes where you'd like to set it up.

Below you can see a flowchart that illustrates how you can deploy the same stack to multiple environments at the same time.

![](../docs/.gitbook/assets/dyrector-io-multi-instance-deployments-dark.png)

Another scenario is when a 3rd-party redistributes the business application your organization develops. In the flowchart below you can see how this process differs from direct distribution as described above.

![](<../docs/.gitbook/assets/dyrector-io-multi-instance-deployments-outsourcing-dark (1).png>)

> **In progress:** Bundled configurations enable your team to assign templatized configurations through the whole process.

### Instant test environments

QA, PMs and salespeople can spark up your stack instantly on their own by deploying the stack to their local machine or a demo environment as a project.

### **And more, including**

* Installing Next.js apps with NGINX to a VPS or a Kubernetes cluster
* Installing single images (like RabbitMQ or a database)
* Checking server/cluster status
