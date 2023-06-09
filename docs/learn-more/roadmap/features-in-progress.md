# Features in progress

### Continuous Delivery

Manually triggered deployments at the end of a CD pipeline. Related features: scheduled releases. Configure your release and schedule a deployment time for the designated environment when the deployment won't be disruptive to users.

### Bundled configurations

Misconfiguration induced failures are very common, especially when you don't have to regularly deal with configuration variables. Add human factor to the equation and the chances of outages induced by faulty configurations increase significantly.

For this reason we're working on a feature that allows users to manage bundled configurations. This way you'll be able to treat your configurations in a templatized manner.

### Changelog generation

Unawareness of how one version of your image is different from another is a risky practice. To avoid this, the platform helps you create changelogs based on your commit messages with Conventional Commits service. Make sure developers working on your application leave meaningful commit messages, so everyone working on your project understands the details of each version.

Changelog generation can reduce knowledge gap between stakeholders, like developers who work every day on the project and outsiders who occasionally deal with the project, like decision-makers.

Besides the changelogs, you can also leave a comment related to nodes and projects on the platform which your teammates can see on the platform's UI.

#### Use cases

* **Auto send changelogs:** once the changelog is generated, you can send it via e-mail or chat, whichever your team uses to communicate. For further information, check the ChatOps section.

### Secrets management

You can use HashiCorp’s Vault Integration for secrets management to keep your passwords and encryption keys secure. This means the platform compliments your DevSecOps practices. Your secrets will be securely stored by HashiCorp, which you can access through the platform.

HashiCorp Vault is the de facto tool of security, used by most organisations. We encourage our users to use it, as well.

#### Use cases of HashiCorp’s Vault

* **General Secret Storage:** store your secrets, including sensitive configurations, tokens, API keys. Query them by using `vault read`.
* **Employee Credential Storage:** instead of using sticky notes around your screen, store and distribute credentials in one place. Vault has an audit log mechanism, which lets you know who had access to one of the stored secrets. This simplifies monitoring which keys have been rolled or not.
* **API Key Generation for Scripts:** generate temporary access keys for the duration of a script. The keys only exist for that duration and are logged by HashiCorp.
* **Data Encryption:** aligning with the purpose of the platform, HashiCorp’s Vault enables developers to focus on developing. The Vault takes care of data encryption and decryption, instead of the developers and other technical staff on the team.

### Role Based Access Control - RBAC

Role based access control allows you to manage the privileges of other users. This is an extra measure of security to your infrastructure and data. Using RBAC helps you to avoid situations when someone has unauthorised access to your account to execute harmful actions.

#### Use cases

* **Principle of Least Privilege:** consider the tasks of each user having access to your infrastructure. Only give them privileges necessary to complete their tasks, including modifying and managing configurations.

### ChatOps

The platform's functionality implemented into ChatOps commands.

### YAML export

In case you decide to stop using the platform, you can generate YAML files to easily setup their services using another platform without using data.
