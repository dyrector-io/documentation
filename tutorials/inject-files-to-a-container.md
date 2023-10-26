# Inject Files to a Container

You can inject files into a container using [**S3 storages**](../features/storage.md) by following the steps below.

What you'll need:

* An S3 API compatible storage available

### **Add your storage to the platform**

**Step 1:** Navigate to Storage on the platform and click the `Add` button at the top right corner.

**Step 2:** Enter the following information to their respective fields:

* Name
* Your storage's URL
* Access key
* Secret key

**Step 3:** Click `Save`.

### Add a bucket in your storage to a container

**Step 1:** Navigate to your projects and select the project that has the container you'd like to inject files to.

{% hint style="info" %}
When the container is under a versioned project version's, there's an extra step you'll need to take by selecting the version you desire to deploy.
{% endhint %}

**Step 2:** Click on the gear icon on the right side of the container.

**Step 3:** If it's turned off, turn on the `Storage` filter in the sub filters.

**Step 4:** Select the storage you'd like to inject files from, and enter the bucket path.

{% hint style="success" %}
You can specify a folder within a bucket, too. (Example: "bucket/folder/sub-folder")
{% endhint %}
