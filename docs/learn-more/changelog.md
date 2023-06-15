# Changelog

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
