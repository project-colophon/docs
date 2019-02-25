---
description: >-
  Colophon requires the following environment variables to operate successfully
  and interact with GitHub APIs
---

# Environment Setup

### GitHub Settings

Values generated by GitHub when [Creating a GitHub App](github-application-setup.md)

| Environment Variable | Example |
| :--- | :--- |
| **`GITHUB_APP_ID`** | _`22615`_ |
| **`GITHUB_APP_LINK`** | _`http://github.com/apps/colophon-dev`_ |
| **`GITHUB_CLIENT_ID`** | _`Iv1.c576b97bab9e78b4`_ |
| **`GITHUB_CLIENT_SECRET`** | _`17a59c0da3a8401a0e5b16d35153a26451b20f42`_ |
| **`GITHUB_PRIVATE_KEY`** | _`-----BEGIN RSA PRIVATE KEY-----\neIEogIBAAKCAQEA0d...\n-----END RSA PRIVATE KEY-----`_ |
| **`GITHUB_PRIVATE_KEY_PATH`** | _`/path/to/colophon-app.2019-03-01.private-key.pem`_ |
| **`GITHUB_WEBHOOK_SECRET`** | Created by you when [Creating a GitHub App](github-application-setup.md#generating-a-private-key) |

{% hint style="danger" %}
You have two methods of passing the private key to the application, only use **one of them**:

* Using **`GITHUB_PRIVATE_KEY`**with the inline content of the generated `.pem` file
* Using **`GITHUB_PRIVATE_KEY_PATH`** and uploading the `.pem` file to your server
{% endhint %}

{% hint style="info" %}
convert the `.pem` file into a single line with this command:

```bash
awk 'NF {sub(/\r/, ""); printf "%s\\n",$0;}' colophon-app.2019-03-01.private-key.pem
```
{% endhint %}

### App Settings

| Environment Variable | Example | Description |
| :--- | :--- | :--- |
| **`COLOPHON_LINK`** | `http://colophon.my-company.com:8080` | Domain where this service lives on the web. |
| **`COLOPHON_PORT`** | `8484` | Specifies the port we want to listen to on the server's network interface _\(Default: `3000`\)_ |
| **`COLOPHON_SESSION_SECRET`** | _`my-super-secret-cookie-secret`_ | Cookie Session secret |

{% hint style="danger" %}
**`COLOPHON_LINK`** is primarily used for the GitHub user authentication redirect, and should reflect the **public facing URL & port** your users will use.

This is used **independently** from the **`COLOPHON_PORT`** value.
{% endhint %}

{% hint style="info" %}
If you're using a PaaS environment that dynamically assigns **`PORT`** value, simply keep **`COLOPHON_PORT`** empty and Colophon will use **`PORT`** instead.
{% endhint %}

### Database config

Colophon requires a PostgreSQL database instance, you can find the database initialization scheams under the [`database`folder](https://github.com/project-colophon/app/blob/master/docs/database)

Please use an appropriately managed/scaled database server then direct Colophon to connect to it using the following environment variables:

| Environment Variable | Example | Description |
| :--- | :--- | :--- |
| **`POSTGRES_HOST`** | _`localhost`_ | The database server host address |
| **`POSTGRES_PORT`** | _`5432`_ | The database server port |
| **`POSTGRES_DB`** | _`colophon_db`_ | The database name |
| **`POSTGRES_USER`** | _`colophon_user`_ | The database user |
| **`POSTGRES_PASSWORD`** | _`colophon_user_password`_ | The database user password |
