# FAQ

### Can I use dyrector.io without containerization?

Unfortunately we don't support applications that don't run in a containerized environment.

### Is dyrector.io Kubernetes specified?

No. It can be configured with any environment, cloud or on-premises, Docker or Kubernetes. Read how you can [**set up Nodes**](../../docs/tutorials/register-your-node.md).

### **Can I use the self-managed platform with NGINX?**

Yes. Find the NGINX example [**here**](../../self-managed/proxies.md#nginx).

### **What is the difference between Image and Container configuration?**

**Short:** Generic configuration => Image, specific configuration => Container config, configuration is inherited from Image configuration.

Parameters that are generic and context independent should be defined on the Image level. Other, context dependent information, like an environment variable PUBLIC\_URL="https://example.com" should be defined on the Deployment's level. During deployment there is a one-way merge using these configurations with Container configuration having the higher priority. &#x20;

### Can I use the platform without a profile and teams?

Unfortunately no, but there are settings you can use to disable Kratos. More details [**here**](https://docs.dyrector.io/self-managed/quick-start).

### Can I deploy my images to a cluster orchestrated by Kind?

Yes.

### Can I schedule database backups with dyrector.io?

Unfortunately there's no such capability within the platform now, but creating a similar functionality is in our plans.

### Is it a CI/CD tool?

The platform provides [**CD capabilities**](../../features/continuous-deployment.md), but it doesn't offer CI, as of now. Such capabilities are in our long-term plans.

### Does the platform manage routing?

Unfortunately routing isn't managed by the platform itself. When you'd like to access your node or a deployed stack through a domain, you'll need to configure routing on your own.

### Is it only for businesses?

dyrector.io is for anyone who works with containerized applications. That means organizations, or independent developers can gain advantage of the platform's functions.

### Will the tool remain completely free in the future?

Self-managed use will stay 100% free and unrestricted. But most of our team works full-time on the platform. While we gain some revenue as a cloud consultancy, we accept [**donations**](https://opencollective.com/dyrectorio-platform) to fund the project.

### What was the motivation behind making this tool?

We needed a solution for self-service release management capabilities for an entirely different project. We couldn't find one that fit exactly our needs, so we made our own platform.

### I have a feature request. Can I send you a message about it?

Don’t hesitate, reach out to us at [**hello@dyrector.io**](mailto:hello@dyrector.io). Also drop us a mail to the same address if you find a bug or any other anomaly you experience. We’ll respond within 24 hours.

### My question isn’t answered here. Where can I reach you?

Send us an e-mail at [**hello@dyrector.io**](mailto:hello@dyrector.io) or check in on [**Discord**](https://discord.gg/pZWbd4fxga).
