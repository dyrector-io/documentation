# Storage

File injection to containers is possible with the Storage function. It's S3 compatible, as of now only Azure Blob Storage isn't supported.

**Amazon S3** is a scalable and highly available object storage service. We decided to go with S3 as it’s one of the most popular solutions that offer interoperability with a fair number of open-source projects. They offer a bunch of functions as a flat structure file storage, including versioning, different types of access control, and so on.

One example of S3 use cases is to upload the object via a REST endpoint and the object will be available through a simple URL.

Amazon S3 isn’t open-source but a few open-source implementations are listed below:

* MinIO,
* OpenIO,
* Scality.

{% hint style="info" %}
You can set up the S3 implementations as mentioned above. Find out how to do in the [**Tutorials**](broken-reference) section.
{% endhint %}
