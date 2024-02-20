# Environment variables

### dyrectorio/.env.example

```shell
## Docker settings

# Traefik requires this file to be able to route the requests to the containers
DOCKER_SOCKET=/var/run/docker.sock

## General

# Tag for images. It's stable by default
DYO_VERSION=stable
# Required for Traefik's certification resolution
# It should be your domain where dyrector.io will be available
DOMAIN=example.com
# Your server's timezone
TIMEZONE=UTC
# Required for Traefik's certification resolution
# If there's an issue with the certificate, or when it expires,
# letsencrypt will send a notificatiom to this e-mail address
ACME_EMAIL=user@example.com
# NodeJS services can run in two modes: production and development
# These are the two values this key can have
NODE_ENV=production

## Crux service settings

# You can specify how thorough logging will be
# Options: verbose, debug, info, warning, error
# The settings come in a hierarchic order,
# meaning that in the order above they contain each other
# Example: 'warning' contains 'error'
LOG_LEVEL=debug

## Database passwords

# This value is the password to crux's database
CRUX_POSTGRES_PASSWORD=Random_Generated_String
# This value is the password to Kratos' database
KRATOS_POSTGRES_PASSWORD=Random_Generated_String

## External URL of the site https://example.com(:port if not 443)

# This setting is to define where your
# self-managed dyrector.io will be available
EXTERNAL_URL=https://example.com

## Cookie/JWT secrets

# Secret to sign JWTs.
CRUX_SECRET=Random_Generated_String
# Secret to sign Kratos cookies
# More details in Ory/Kratos documentation:
# https://www.ory.sh/docs/kratos/reference/configuration
KRATOS_SECRET=Random_Generated_String

## Mailserver settings

# The connection string for the mail server
# The protocol can be SMTP or SMTPS
# Example: protocol://smtp_user:smtp_password@mailserver_ip_or_domain:port
SMTP_URI=smtps://username:password@mailserver.example.com:465
# E-mail address for dyrector.io invitation links,
# password resets and others
FROM_EMAIL=from@example.com
# E-mail sender name for dyrector.io invitation links,
# password resets and others
FROM_NAME=dyrector.io

## ReCAPTCHA secrets

# In case you don't want to use ReCAPTCHA set DISABLE_RECAPTCHA to true
# Highly recommended to keep the default value, which is `false`
DISABLE_RECAPTCHA=false
# Create ReCAPTCHA V2 credentials in the ReCAPTCHA admin console
# It is recommended to use the inivisble type
RECAPTCHA_SECRET_KEY=Recaptcha_Secret_Key
RECAPTCHA_SITE_KEY=Recaptcha_Site_Key
```

### dyrectorio/web/crux/.env.example

```bash
NODE_ENV=development

## Development configurations

# Kratos public API
KRATOS_URL=http://localhost:8000/kratos
# Kratos admin API
# This should never be exposed
KRATOS_ADMIN_URL=http://localhost:4434
DATABASE_URL="postgresql://username:password@localhost:5432/crux?schema=public"
CRUX_UI_URL=http://localhost:8000

## Port settings

# Agent gRPC API port
GRPC_AGENT_PORT=5000
# RestAPI port
HTTP_API_PORT=1848
# Prometheus metrics port
METRICS_API_PORT=1956

# Podman has different alias host.containers.local:5000
CRUX_AGENT_ADDRESS=localhost:5000
# Signing secret for the generated JWTs
JWT_SECRET=jwt-secret-token

# The Docker image tag in the node install script
# Uncomment to use a different agent version
# Defaults to the version of dyrector.io
# CRUX_AGENT_IMAGE=latest

# Uncomment to prevent the install script from
# overwriting your locally built agent image
# AGENT_INSTALL_SCRIPT_DISABLE_PULL=true

# Possible values: trace, debug, info, warn, error, and fatal
# The settings above come in a hierarchic order
# Example: error contains fatal
LOG_LEVEL=debug

## Email service config
# SMTP URL for the mailslurper
SMTP_URI=smtps://test:test@localhost:1025/?skip_ssl_verify=true&legacy_ssl=true
# E-mail address for dyrector.io invitation links, password resets and others
FROM_EMAIL=from@example.com
# E-mail sender name for dyrector.io invitation links, password resets and others
FROM_NAME=dyrector.io

## Google ReCAPTCHA config
DISABLE_RECAPTCHA=true
# Required only when ReCAPTCHA is enabled
RECAPTCHA_SECRET_KEY=<recaptcha_secret_key>

# Using this number to determine the quantity of logs being returned from the Docker container.
DEFAULT_CONTAINER_LOG_TAIL=100

# For overriding the node DNS result order
# regardless of the NODE_ENV value
# It may be necessary for running the e2e tests,
# because node resolves localhost to IPv6 by default
# DNS_DEFAULT_RESULT_ORDER=ipv4first
```

### dyrectorio/web/crux-ui/.env.example

<pre class="language-bash"><code class="lang-bash">CRUX_UI_URL=http://localhost:8000

KRATOS_URL=http://localhost:8000/kratos
KRATOS_ADMIN_URL=http://localhost:4434

# Sets the severity level of logging
# Possible values: trace, debug, info, warn, error, and fatal
# The settings come in a hierarchic order
# Example: error contains fatal
LOG_LEVEL=trace

## Google ReCAPTCHA config

DISABLE_RECAPTCHA=true
# Required only when ReCAPTCHA is enabled
<strong>RECAPTCHA_SITE_KEY=&#x3C;public_recaptcha_site_key>
</strong>RECAPTCHA_SECRET_KEY=&#x3C;recaptcha_secret_key>

## Playwright test config (for e2e tests)

E2E_BASE_URL=http://localhost:8000

# Docker HUB Proxy (optional)
# HUB_PROXY_URL=http://&#x3C;proxy_url>
# HUB_PROXY_TOKEN=&#x3C;proxy_token>

# For overriding the node dns result order regardless of the NODE_ENV value
# It may be necessary for running the e2e tests,
# because node resolves localhost to IPv6 by default
# DNS_DEFAULT_RESULT_ORDER=ipv4first
</code></pre>

### dyrectorio/golang/cmd/crane.env.example

```bash
# Generic config options
# filled with defaults where it's applicable
DEFAULT_LIMITS_CPU=100m
DEFAULT_LIMITS_MEMORY=128Mi
DEFAULT_REQUESTS_CPU=50m
DEFAULT_REQUESTS_MEMORY=64Mi
DEFAULT_VOLUME_SIZE=1G
# GRPC_TOKEN=
IMPORT_CONTAINER_IMAGE=rclone/rclone:1.57.0
INGRESS_ROOT_DOMAIN=
READ_HEADER_TIMEOUT=15s
DEBUG=true
DEBUG_UPDATE_ALWAYS=false
DEBUG_UPDATE_USE_CONTAINERS=true
DEFAULT_REGISTRY=index.docker.io

# Crane specific options
# Put 'true' to use in-cluster auth
CRANE_IN_CLUSTER=false
# The duration amount that for a kubernetes API request to complete
DEFAULT_KUBE_TIMEOUT=2m
# Field manager name
FIELD_MANAGER_NAME=crane-dyrector-io
# Use 'Force: true' while deploying
FORCE_ON_CONFLICTS=true
# The key/label name for audit purposes
KEY_ISSUER=co.dyrector.io/issuer
# The "kubectl" configuration location
KUBECONFIG=
# Timeouts used in tests, no effect on deployment
TEST_TIMEOUT=15s
# For injecting SecretPrivateKey
SECRET_NAME=dyrectorio-secret
SECRET_NAMESPACE=dyrectorio
```

### dyrectorio/golang/cmd/dagent.env.example

```bash
# Generic config options
# filled with defaults where it's applicable
DEFAULT_LIMITS_CPU=100m
DEFAULT_LIMITS_MEMORY=128Mi
DEFAULT_REQUESTS_CPU=50m
DEFAULT_REQUESTS_MEMORY=64Mi
DEFAULT_VOLUME_SIZE=1G
# GRPC_TOKEN=jwt
IMPORT_CONTAINER_IMAGE=rclone/rclone:1.57.0
INGRESS_ROOT_DOMAIN=
READ_HEADER_TIMEOUT=15s
DEBUG=true
DEBUG_UPDATE_ALWAYS=false
DEBUG_UPDATE_USE_CONTAINERS=true

# DAgent specific options
AGENT_CONTAINER_NAME=dagent
DAGENT_IMAGE=ghcr.io/dyrector-io/dyrectorio/dagent
DAGENT_NAME=dagent-go
DAGENT_TAG=latest
# This should match the mount path that is
# the root of configurations and containers
DATA_MOUNT_PATH=/srv/dagent
DEFAULT_TAG=latest
DEFAULT_TIMEOUT=5s
GRPC_KEEPALIVE=60s
# Path of 'docker.sock' or other local/remote
# address where we can communicate with docker
HOST_DOCKER_SOCK_PATH=/var/run/docker.sock
# Containers mount path default
INTERNAL_MOUNT_PATH=/srv/dagent
# Loglines to skip if not defined on the request
LOG_DEFAULT_SKIP=0
# Loglines to take
LOG_DEFAULT_TAKE=100
MIN_DOCKER_VERSION=20.10
# E-mail address to use for dynamic certificate requests
TRAEFIK_ACME_MAIL=
TRAEFIK_ENABLED=false
# Loglevel for Traefik
# Set to "DEBUG" to access Traefik dashboard
TRAEFIK_LOG_LEVEL=
# Whether to enable Traefik TLS or not
TRAEFIK_TLS=false
DEFAULT_REGISTRY=index.docker.io
# Token used by the webhook to trigger the update
WEBHOOK_TOKEN=
```
