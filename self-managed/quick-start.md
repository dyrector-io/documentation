---
description: >-
  Self-managed setup is only supported in Docker as of now, Kubernetes support
  is in the works.
---

# Quick start

### Production

Use [**docker-compose.yaml**](https://github.com/dyrector-io/dyrectorio/blob/develop/docker-compose.yaml).

### Pilot

{% hint style="danger" %}
The docker-compose below is only designed for demoing the platform, we don't suggest using it for any other use.
{% endhint %}

Use [**docker-compose.http-only.yaml**](https://github.com/dyrector-io/dyrectorio/blob/develop/docker-compose.http-only.yaml).

### Development

Use [**CLI**](cli.md).

### System Recommendations

* 1 CPUs
* 8 GB RAM
* Docker or Podman installed

{% hint style="info" %}
**Disabling Sign Up**

We don't have an option to disable signup, but you can restart the Kratos container with the following variables in the docker-compose:

`SELFSERVICE_FLOWS_REGISTRATION_ENABLED=false`

It should disable the registration flow and the platform will throw an error on the registration page.

More details in [**Kratos documentation**](https://www.ory.sh/docs/kratos/reference/configuration).
{% endhint %}

#### Why it's worth it

**Self-managed dyrector.io is free, unlimited, forever.**

This freedom comes with a trade-off. While we'll still offer support on our [**Discord**](https://discord.gg/pZWbd4fxga) server, we take no responsibility for maintaining your own instance of the platform and we won't prioritize giving support over other users. Make sure you use the latest version for a consistent experience.

While we won't put a cap on the number of nodes, deployments, projects you manage with your self-managed instance, as with every self-managed software, environment or database related problems might occur, which we take no responsibility for. For a seamless experience, give the [**cloud-hosted platform**](../tutorials/getting-started.md) a look.
