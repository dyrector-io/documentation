# Container configuration

### Container routing

Container routing is available for nodes where Traefik is enabled on node install.

Expose strategy of the container you wish to be exposed should be set to HTTP or HTTPS, instead of none. In the [**routing section of the configuration screen**](./), you need to specify a domain and a port. The additional variables are optional.

When a path is specified, the Traefik container will exclusively route requests with URLs containing that designated path prefix.

Enabling path stripping will result in forwarding the request without including the specified path.

The generated Traefik router's name will be automatically generated as "prefix + name."

If the router uses HTTPS, all necessary Let's Encrypt labels will also be added. It's important to note that middlewares can only be applied by adding them as custom Docker labels.

#### Docker labels

If you have Docker labels set for your container, you can specify them as key-value pairs in the config screen under the Docker labels section.
