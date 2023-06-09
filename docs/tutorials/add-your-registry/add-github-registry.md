# Add GitHub Registry

**Step 1:** Open Registries on the left and click ‘Add’ on the top right.

**Step 2:** Enter your registry’s name and select an icon.

{% hint style="success" %}
**Tip:** You can write a description, so others on your team can understand what’s the purpose of this registry.
{% endhint %}

**Step 3:** Select GitHub Registry type.

![](../../../.gitbook/assets/dyrector-io-github-registry.png)

**Step 4:** Select if you'd like to add an organization or a user.

**Step 5:** In the corresponding fields, enter:

* Your GitHub user name,
* Personal access token generated in GitHub with the steps documented [**here**](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token). Select the `repo` and `read:packages` scopes. `Repo` scope is required due to GitHub's limitations. You're still able to add public GitHub registries, too.
* And your organization’s or your user's GitHub name.

{% hint style="danger" %}
Only classic tokens are supported. Fine-grained tokens aren't supported yet.
{% endhint %}

**Step 6:** Click ‘Save’ button on the top right.
