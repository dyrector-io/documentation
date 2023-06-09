# Create your Project

**Projects are the deployable units made up of images and their configuration you're going to manage through the platform.**

|                  | Versioned Project            | Versioned Project                   | Versionless Project              |
| ---------------- | ---------------------------- | ----------------------------------- | -------------------------------- |
| **Version Type** | Rolling                      | Incremental                         | ❌                                |
| **Rollbacks**    | ❌                            | ✅                                   | ❌                                |
| **History**      | Previous version overwritten | Image and configuration inheritance | ❌                                |
| **Ideal for**    | Nightly Versions             | Production                          | Testing, Single-container stacks |

The different project types have different deployment capabilities. For more details about the differences, check out the [**Components**](../../../basics/components.md#deployment) section.

### **Versionless project**

Versionless projects have one abstracted-away version and cannot be rolled back. These are mostly useful for testing purposes.

### **Versioned project**

Versioned projects have two types of versions: rolling and incremental. You can define one version per versioned project as default. That'll be the version future versioned projects will inherit images and configurations later until you set another one as default.

#### **Rolling Version**

Rolling versions are similar to simple projects except they’re perfect for continuous delivery. They’re always mutable but contrary to incremental projects they aren’t hierarchic and lack a version number.

#### **Incremental Version**

Incremental versions are hierarchical. They can have a child version and once a deployment is successful, the deployed versions, the environment variables, and the deployed images can never be modified. This guarantees you’re able to roll back the deployed version and reinstate the last functional one if any error occurs to avoid downtime.

{% hint style="info" %}
**Versioned projects can have both rolling and incremental versions.**
{% endhint %}
