# Changelog

### 0.10.0

Introduced node connection improvements: node kick option is added, fixed an issue with updated agents getting kicked, and added an agent connection mechanism which will attempt connection with the stored token first, then the environment token if the first attempt fails. Delivered a fix to agents occasionally crashing when a container is deleted. Fixed deployment logs and container events logs overwriting each other. Added Rocket.Chat and Mattermost notification integrations. Added working directory as a container option. Integrated PostHog for quality assurance purposes (more details about it [**here**](https://docs.dyrector.io/learn-more/quality-assurance-qa)) - tracking can be disabled. Private Docker Hub registries are now supported. Added healthchecks to CLI upon `up` command. Added show icon feature to relevant pages. Minor fixes and improvements.

Shouts to **chandhuDev** for his contribution in this release.

More details about this release on [**GitHub**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.10.0).

### 0.9.0

Container settings (docker inspect) are now available in the platform. Updated deployment process screen with a progress bar. Container config fields are node type based now. Various fixes and updates: ory/kratos identity listing, unnecessary websocket error toasts, audit event filtering, key-value input error messages. Other fixes and improvements. Thanks to our **Hacktoberfest** contributors:

* PapePathe
* pedaars
* GuptaPratik02
* harshsinghcs
* akash47angadi

More details about this release on [**GitHub**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.9.0).

### 0.8.2

Improved yup validation on the UI of the platform. Agent improvements: added `updating` status to agent, update button is disabled when there's no update available, fixed an agent update issue when the agent stuck at an older version. Deployments are listed on the node detail page. Fixed a deployment issue when secrets are copied to a different node's deployment. Other fixes and improvements. More details about this release on [**GitHub**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.8.2).

### 0.8.1

Reworked agent connection handling to offer a more secure and stable user experience for node management. Added category labels to the platform's containers for better usability. Stack's Go toolchain is upgraded, deploymentStrategy is now utilized, and port routing is explicit. Implemented a fix for port range exposion. Minor fixes and improvements. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.8.1).

### 0.8.0

Implemented two new capabilities: configuration bundles and protected deployments. [**Configuration bundles**](../../features/configuration-management/configuration-bundle.md) are configuration templates you can apply to other stacks you manage with the platform. [**Protected deployments**](../tutorials/deploy-your-product.md) prevent overwriting certain stacks on an infrastructure. Self-managed dyrector.io stack now pulls the latest image when a new version is available. Made several improvements to the UI of the platform: added deployment creation card, table sorting, and images are listed now on the page of a registry. We turned image and instance configuration settings more distinct from each other. Improved sign up and team validation workflow. Added [**MLflow**](https://github.com/mlflow/mlflow) template. Minor fixes and improvements. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.8.0).

### 0.7.0

Added team slug to API endpoints. Implemented node check before deletion. Self-managed dyrector.io improvements: added HEALTCHECK directives to self-managed dyrector.io images, upgraded ory/kratos to 1.0 in dyrector.io stack. dagent improvements: host rule removed when no domain is given, unix socket based healthcheck. Configuration screen improvements: renamed ingress to routing in container configuration to simplify domain specification in config editor, swapped internal and external port inputs, port validation fixes. Made improvements to teams. Other fixes and improvements. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.7.0).

### 0.6.1

Implemented fixes to dagent related issues, deployment token migration. UI improvements. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.6.1).

### 0.6.0

Local images can be added as unchecked registry. Fixed a bug that prevented users from generating a CD token. Minor fixes. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.6.0).

### 0.5.5

Made continuous deployment token improvements: name can be added to tokens for better usability, CD events show up in audit log, CD token has never expire option. Social sign-in is now available: GitHub, GitLab, Google, Azure. Fixed node edit bug. Made improvements to agent, onboarding checklist. Minor fixes and updates. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.5.5).

### 0.5.4

Added deployment tokens to trigger CD pipelines. Versionless projects can be converted to versioned. You can select what images you'd like to deploy. Improved registry workflow. Added reload when Kratos isn't available. Small UI improvements. Minor fixes and updates. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.5.4).

### 0.5.3

Added crane to signer image and add additional cache restore. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.5.3).

### 0.5.2

Implemented principle of least privilege RBAC when managing a Kubernetes cluster through the platform. Improvements to node setup flow, container management, dagent registry auth. Minor fixes and improvements. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.5.2).

### 0.5.1

The release includes a fix for minor versioning in the CI process and a change in the release script to incorporate the version of Golang components. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases).

### 0.5.0

Added onboarding checklist to the dashboard to guide users through deployment process. Automated multiarch builds to dyrector.io agent, including ARM. Renamed products to projects and their types: simple to versionless, complex to versioned. Improved audit logs with agent connectivity data. Rolling projects are now copyable. Fixes and improvements. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.5.0).

### 0.4.2

Fixes and improvements to secrets, private V2 registry addition to the platform, and container view UI improvements. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.4.2).

### 0.4.1

Minor fixes. More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.4.1).

### 0.4.0

We made various improvements to the project codebase, including adding an offline bundle Makefile target for offline development. We also enhanced the documentation by refactoring the `README.md` file, including FAQs and a CLI docs link. Unused texts were removed, making the readme more concise. To improve usability, we enhanced the API descriptions and examples in the web documentation. We also introduced container config annotations for greater container configuration flexibility. Deployment management and tracking were improved with the implementation of deployment and event index functionalities.

We resolved a team invite captcha error and introduced code formatting for better readability. For logging and monitoring, we implemented HTTP and WebSocket audit log functionalities. Documentation organization was enhanced by adding .md files, and we improved the pull request labeling process. Title validation for pull requests was implemented, and OpenAPI descriptions and UUID parameter handling were validated. A PR labeler was added to automate labeling, and a deployment events API was introduced. In the `UI` module, we made the signup page responsive and implemented reCAPTCHA for team invites to enhance security.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.4.0).

### 0.3.4

This version includes various bug fixes, template refinements, and updates to container IDs and UI status. Additionally, technology labels were added to templates and a demo video was introduced in the release.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.3.4).

### 0.3.3

This release includes a number of bug fixes and new features across various components of the software stack. Notably, the `crane` component was fixed to use the original `containerPreName` as a name for namespace, the web component now has a Gitea template and a PowerShell script, and the `agent` component now has an option to not have CPU limits. The `ci` component has also been updated with new `e2e testing` and image building capabilities, as well as improved image signing and push to DockerHub. Other improvements include new templates and health checks, as well as updates to dependencies and minor UI fixes.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.3.3).

### 0.3.2

Agents - dagent and crane - support ARM powered nodes now. New templates are added: Gitea & Minecraft server. Minor fixes to deployments, JSON editor and mapper.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.3.2).

### 0.3.1

Dashboard is available to get a quick glance of the latest deployments and statistics. [**Templates**](../../features/templates/) are now available for 5 applications: WordPress, Strapi, self-managed GitLab, Google Microservices Demo, LinkAce. Configuration management improvements and fixes: previous secrets are reused, listing glitches of variables are fixed in filters. Improvements to dagent and crane: distroless image, abs path support for mounts, container builder extra hosts.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.3.1).

### 0.3.0

_dagent_ updated: posix, mingw64 is supported now. _dagent_ updates and deletes itself when new version of dagent is released. CLI improvements: verbose Docker & Podman error messages when CLI is setup. Config updates: common, Kubernetes & Docker variable filters & new variables (labels & annotations) added, unmatched secrets are invalidated, users can now mark secrets as required. Deployment updates: flow fixed, new capabilities (deletion & copy) available. Link navigation fixes in signup email. _crane_ registry auth update.

Thanks to our **Hacktoberfest** contributors:

* SilverTux (add unit test for crane clients),
* joremysh (add unit tests for agent/internal/crypt),
* oriapp (replaced all try-catch's with catch (err)),
* tg44 (zerolog introduced),
* raghav-rama (add new docker container builder attribute: shell),
* minhoryang (crane init for private-key generate on k8s, crane init at k8s deployment for shared secret, goair for new watch tool and makefile modified),
* clebs (Add unit tests for golang/internal/mapper)

659 files changed, 48182 insertions(+), 24050 deletions(-)

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/blob/develop/CHANGELOG.md#030-2022-12-06).

### 0.2.2

Fixed Prisma segfault.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.2.1).

### 0.2.1

CLI tool developed for quick local setup. Read [**here**](../../self-managed/cli.md) how to use CLI.

Container configuration & secret management improved. Google Container Registries are supported. Notifications are implemented for Discord, Slack and Microsoft Teams to notify teammates of new Nodes, Products, deployment statuses and new teammates. Google Microservices Demo is available with DemoSeeder implementation. Agent related improvements. E2E tested with Playwright. Improved Audit log with pagination and server side filtering. Status page available to check the statuses of the services of the platform. User facing documentation is available. Minor glitches and bugs fixed.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/0.2.1).

### 0.1.1

Vital fixes and cleanups. Extended & actualized unit tests in agent.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/v0.1.1).

### 0.1.0

Migration into a monorepo on GitHub to measure up to open-source requirements. Automations and multiple platform support – Apple Silicon, Windows – is now available to provide a convenient developer experience. Agent's install script is added with MacOS support. Guidelines of contribution – code of conduct and README.

More details about this release [**here**](https://github.com/dyrector-io/dyrectorio/releases/tag/v0.1.0).
