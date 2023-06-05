---
description: >-
  CLI is a tool for deploying a complete dyrector.io stack locally, for
  demonstration, testing, or development purposes.
---

# CLI

### **Dependencies**

Before using the dyrector.io CLI, make sure you have the following dependencies installed on your local machine:

* Docker installed on your system but [**Podman**](https://podman.io/) works, too.
* Go (1.20 or higher) to run the `go install`.

{% hint style="info" %}
When you use **Podman**, make sure you have the `network_backend` set to `netavark`, if you have an older installation (before 4.0 released) as the old CNI network backend doesn't support name resolutions we use.

You also have to get the aardvark-dns plugin for the same reason.

If you use rootless containers, set your `DOCKER_HOST` environmental variable correctly, because if it's missing, Docker will assume it's `/var/run/docker.sock` and you can get misleading errors from it.
{% endhint %}

### Go install

**Step 1:** Execute `go install github.com/dyrector-io/dyrectorio/golang/cmd/dyo@develop`

**Step 2:** Execute `dyo up`

**Step 3:** After you navigated to `localhost:8000` (this is the default traefik port) you will see a Login screen

**Step 4:** Register an account with whatever e-mail address you see fit (doesn't have to be valid one)

**Step 5:** Navigate to `localhost:4436` where you will find your mail as all outgoing e-mails will land here

**Step 6:** Open your e-mail message and using the link inside you can activate your account

**Step 7:** Happy deploying! 🎬

### Run CLI from codebase

**Step 1:** By using command line – posix shells, Git Bash or PowerShell –, pull dyrector.io's [**GitHub repository**](https://github.com/dyrector-io/dyrectorio) by executing `git pull`, if you don't already have the repository on your local machine you have to clone the repository by executing `git clone https://github.com/dyrector-io/dyrectorio.git`.

**Step 2:** Open the project folder, and execute `make up` – alias to `go run ./golang/cmd/dyo up` – and wait until you get back the command prompt. It should take a few minutes the first time running, as it will pull a few docker images.

**Step 3:** Enter `localhost:8000` in your browser's address bar. **You're ready to use dyrector.io.**

dyrector.io's command-line interface (CLI) lets you run a complete dyrector.io development environment locally with the following services: UI Service (crux-ui), Backend Service (crux), PostgreSQL databases, Authentication, Migrations, and SMTP mock mail server. The CLI also runs the migration services. The default container names are listed below:

* dyo-stable\_traefik
* dyo-stable\_crux-postgres
* dyo-stable\_kratos-postgres
* dyo-stable\_kratos
* dyo-stable\_kratos-migrate
* dyo-stable\_crux
* dyo-stable\_crux-migrate
* dyo-stable\_mailslurper
* dyo-stable\_crux-ui

The dyo-stable prefix can be changed in the [**settings.yaml**](cli.md#configuration) file of the application.

{% hint style="info" %}
When you contribute to [**dyrector.io**](https://github.com/dyrector-io/dyrectorio), you can turn off crux and crux-ui with the global options listed below or overriding the values in the settings file.
{% endhint %}

### CLI commands

```
USAGE:
   dyo [global options] command [command options] [arguments...]

COMMANDS:
   up, u    Run the stack
   down, d  Stop the stack
   help, h  Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --disable-crux, --dc      disable crux(backend) service (default: false) [$DISABLE_CRUX]
   --disable-crux-ui, --dcu  disable crux-ui(frontend) service (default: false) [$DISABLE_CRUXUI]
   --local-agent, --la       will set crux env to make dagent connect to localhost instead of container network, it's useful when you use a non-containerized agent (default: false) [$LOCAL_AGENT]
   --write, -w               enables writing configuration, storing current state (default: false)
   --debug                   enables debug messages (default: false)
   --disable-forcepull       try to use images locally available (default: false) [$DISABLE_FORCEPULL]
   --disable-podman-checks   disabling podman checks, useful when you run the CLI in a container (default: false) [$DISABLE_PODMAN_CHECKS]
   --config value, -c value  persisted configuration path (default: /home/sziszi/.config/dyo-cli/settings.yaml) [$DYO_CONFIG]
   --imagetag value          image tag, it will override the config [$DYO_IMAGE_TAG]
   --prefix value, -p value  prefix that is preprended to container names (default: dyo-stable) [$PREFIX]
   --local-imagetag value    special local image tag, CLI will try to find it and use it, otherwise it will fall back to config [$DYO_LOCAL_IMAGE_TAG]
   --network value           custom network, overriding the configuration [$DYO_NETWORK]
   --expect-container-env    when both the stack and observer are running inside containers, like during e2e tests (default: false) [$DYO_FULLY_CONTAINERIZED]
   --silent, -s              hides the welcome message and minimizes chattiness (default: false)
   --help, -h                show help
   --version, -v             print the version
```

As you seen above you can start the application with the `up` subcommand, after you finished your work, you can stop and remove the containers with the `down` subcommand.

Running the stack again without stopping it will result in containers stopped, removed then recreated.

### Configuration

The CLI generates a `settings.yaml` file containing the default configurations if the program doesn't find a configuration on the given path, or a default path if there isn't. Default paths is depending on your OS, you can find these on:

* Linux: `$XDG_CONFIG_HOME/dyo-cli/settings.yaml` where the `$XDG_CONFIG_HOME` usually resolving to `$HOME/.config`.
* Mac OSX: `$HOME/Library/Application Support/dyo-cli/settings.yaml`.
* Windows: `%AppData%/dyo-cli/settings.yaml`.

The settings.yaml file contains the following:

{% code title="settings.yaml" %}
```yaml
# This option directly affects the docker images' tags. 
# This applies to kratos, crux, and crux-ui. Currently we offer stable and latest tags.
version: latest
# The network's name where the containers will run. Agent will be installed here by
# agent's install script.
network-name: dyo-stable
# The following settings are mostly self-describing, you can see the default values
# here. If an option isn't available here, the CLI will use a predefined default, 
# where the secrets will be a new 32 character long random string. The ports here 
# will be exposed for your convenience, if theres any local address that is bound to a 
# defined port here, feel free to change it, and restart the CLI.
options:
    # Timezone of the application affects both crux and crux-ui.
    timezone: UTC
    crux-agentgrpc-port: 5000
    crux-http-port: 1848
    crux-ui-port: 3000
    crux-secret: c8S9683U4eXHWr5ikqijZKAaQ89Lb9KJ
    cruxPostgresPort: 5432
    cruxPostgresDB: crux
    cruxPostgresUser: crux
    cruxPostgresPassword: rHNxQdtNQCMywNLAT07HtYKBOJw659rL
    traefikWebPort: 8000
    traefikUIPort: 8080
    traefikDockerSocket: /var/run/docker.sock
    # Necessary for Windows installations
    traefikIsDockerSocketNamedPipe: false
    kratosAdminPort: 4434
    kratosPublicPort: 4433
    kratosPostgresPort: 5433
    kratosPostgresDB: kratos
    kratosPostgresUser: kratos
    kratosPostgresPassword: PHKZhJpdTcWO7KoKdkSVAJjvoiHum597
    kratosSecret: A7ovxCOyBt8hbPfslcD37ZDcKGLKi8of
    mailSlurperSMTPPort: 1025
    mailSlurperWebPort: 4436
    mailSlurperWebPort2: 4437
    FROM_NAME: dyrector.io Platform
    FROM_EMAIL: noreply@dyrectorio.com
```
{% endcode %}

Please note, this file stores some state too, in this case passwords and secrets. These have to match to use the installation multiple times as with bad passwords you won't be able to update or use the databases.

### Get help[​](https://docs.nhost.io/platform/overview/get-started-with-nhost-cli#get-help) <a href="#get-help" id="get-help"></a>

To get usage tips and learn more about available commands from within CLI, run the following as we described above:

```
dyo help
```

If you have additional questions or ideas for new features, you can [start an issue](https://github.com/dyrector-io/dyrectorio/issues) or a new discussion on our CLI’s open-source repository. You can also chat with our team on [Discord](https://discord.com/invite/hMyT9cbYFD).

We’d love to hear from you!
