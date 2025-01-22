---
description: >-
  It is possible to use container registries with self-signed (private)
  certificates. Be warned, it is an advanced, less convenient matter.
---

# Self-signed certificates

### API

You can opt for using **unchecked registries,** that means images are not checked at all, image URLs are passed to the agent straight away. This way you can skip setting up certificates for the API.

The environment variable is **`NODE_EXTRA_CA_CERTS`**, the process expects a concatenated list of your certificates. More info: [https://nodejs.org/api/cli.html#cli\_node\_extra\_ca\_certs\_file](https://nodejs.org/api/cli.html#cli_node_extra_ca_certs_file)

Concatenating pem files to a single file:\
`cat *.cert.pem > node_extra_ca_certs`

Mount the generated file using and provide the environment variable. &#x20;

### Agent

The two supported target nodes require different approaches.

#### dagent

Assumed the host already trusts the CA, when adding a node the install script is visible, you can use this script also to add extra behavior, if it is not explicitly implemented in the UI.\
The component allows us to provide additional CA files using the `SSL_CERT_FILE` variable, it expects one crt file that you have to mount from the host.

The last command of the script will be extended with two lines:

```
 -e SSL_CERT_FILE=/path/to/ssl/ca.crt
 -p /host/cert/path/ca.crt:/path/to/ssl/ca.crt
```

Make sure you use the correct values.

#### crane

Using Kubernetes, you have to make sure that nodes already trust your CA: [example](https://stackoverflow.com/questions/53545732/how-do-i-access-a-private-docker-registry-with-a-self-signed-certificate-using-k).

You have to modify the install script to mount the crt file to crane.

You can create a secret from a file using this one liner, make sure it is in the dyrectorio namespace.

```
kubectl create secret generic my-cert --from-file=path/to/bar
```
