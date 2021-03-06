---
description: >-
  You will need to create and register a GitHub App under your personal account
  or under any organization you have administrative access to.
---

# GitHub Application Setup

{% hint style="info" %}
Learn more about [creating GitHub Apps](https://developer.github.com/apps/building-github-apps/creating-a-github-app/).
{% endhint %}

**Org vs. Personal**

Depending on your usage, your entry point for creating a GitHub app will differ:

* Personal Accounts: [`https://github.com/settings/apps/new`](https://github.com/settings/apps/new)
* GitHub Accounts `https://github.com/organizations/[your-org-name]/settings/apps/new`

You'll be asked provide details for the app, here are the **required** values:

| Field | Description |
| :--- | :--- |
| **GitHub App name** | Can be anything, suggest using `colophon` + `you-org-name` as a suffix |
| **Homepage URL** | Set to `https://colophon.id` |
| **User authorization callback URL** | The full URL to redirect to after a user authorizes an installation. Use `https://your-app-domain` + `/auth/callback` |
| **Webhook URL** | Events will `POST` to this URL. Use the root url of the app `https://your-app-domain` |
| **Webhook secret _(optional)_** | While optional, this is recommended to ensure your Colophon data is secure from external manipulation |

### Permissions

{% hint style="info" %}
Learn more about [GitHub Permissions](https://developer.github.com/v3/apps/permissions/) from the official GitHub documentation
{% endhint %}

Colophon will require access the following permissions to your GitHub account:

| Name | Access |
| :--- | :--- |
| **Repository contents** | `Read-only` |
| **Repository metadata** | `Read-only` |
| **Organization members** | `Read-only` |

### Events

{% hint style="info" %}
Learn more about [GitHub Event](https://developer.github.com/v3/activity/events/types/) from the official GitHub documentation
{% endhint %}

{% hint style="warning" %}
**Note**: you'll have to set all the permissions above first, to enable all the events needed below
{% endhint %}

| Event Name | Description |
| :--- | :--- |
| **Create** | Branch or tag created. |
| **Delete** | Branch or tag deleted. |
| **Push** | Git push to a repository. |
| **Repository** | Repository created, deleted, archived, unarchived, publicized, or privatized. |

### Where can this GitHub App be installed?

If you're forking for the purpose of using this for your self, or your organization, you should pick _**"Only on this account"**_.

### Generated App Information _\(Keys & Secrets\)_

Once created, GitHub will generate a few key items you'll need to pass to Colophon:

| name | environment variable |
| :--- | :--- |
| App ID | `GITHUB_APP_ID` |
| Client ID | `GITHUB_CLIENT_ID` |
| Client secret | `GITHUB_CLIENT_SECRET` |
| Public link | `GITHUB_APP_LINK` |

### Generating a Private key

You need a private key to sign access token requests to GitHub.

Click _"Generate Private Key"_ and store the downloaded `.pem` file somewhere safe. You'll need to use this for the app environment configuration
