# Cal.com

**Cal.com is a meeting scheduler application. Users can set up its self-hosted stack with dyrector.io.**

### **Why use dyrector.io to set up Cal.com**

Cal.com is awesome. We like it and use it everyday, people like it, too. Chances are, if you're here, you like it, as well. Even better that they provide self-hosted usage. But as some users pointed out on [**Hacker News**](https://news.ycombinator.com/item?id=34507672), self-hosting Cal.com is a challenging process. So, we turned it into a template you can set up easily via the easy-to-use and straightforward UI of dyrector.io.

### **Set up Cal.com**

After the Node where you'd like to run Cal.com is [**registered**](../../docs/tutorials/register-your-node.md), you can set it up by following the steps of deployments as documented [**here**](../../docs/tutorials/deploy-your-product.md).

#### Configuration

* **cal-db (latest)**
  * `POSTGRES_PASSWORD` has to be specified.
* **cal-com (2.5.10)**
  * `DATABASE_URL` needs to contain `POSTGRES_PASSWORD`'s value in `postgresql://cal-user:${`**`POSTGRES_PASSWORD`**`}@cal-db:5432/cal-db` for **cal-db**.
  * `NEXTAUTH_SECRET` and `CALENDSO_ENCRYPTION_KEY` needs to be specified. We recommend [**OpenSSL**](https://www.openssl.org/) to generate these secrets.
  * If you have a node with Traefik enabled you can use `http://cal.localhost` (or any other domain setup in the ingress settings) by setting `NEXT_PUBLIC_WEBAPP_URL` to the public URL.

Once the deployment is successful, self-hosted Cal.com is ready to use at [**localhost:7000**](https://localhost:7000) by default, as seen below.

<figure><img src="../../.gitbook/assets/cal-com-docker-setup-dyrectorio.png" alt=""><figcaption></figcaption></figure>
