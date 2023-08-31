# Configuration bundle

You can create configuration bundles which you're able to apply to deployments later. These are templatized key-value pairs for environment variables.

* Configuration bundles are shared between the members of a team.
* Configuration bundles act as .env files.
* Multiple bundles can be applied to a deployment.
* Keys can't conflict between bundles applied to a deployment.
* Values of a bundle can be overwritten manually when you set up the deployment. This won't impact the value stored in the bundle.

{% hint style="info" %}
**Bundles and the deployments of incremental version**

In the case of an incremental version's successful deployment, all the values of the applied bundles are copied to the deployment but connection between the bundles and the deployment are terminated. The purpose of this is when a bundle is modified, it won't interfere with the values specified for an existing deployment.
{% endhint %}
