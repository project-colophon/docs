---
description: >-
  You will need to create and register a GitHub App under your personal account
  or under any organization you have administrative access to.
---

# GitHub Application Setup

{% hint style="info" %}
_Learn more about_ [_creating GitHub Apps_](https://developer.github.com/apps/building-github-apps/creating-a-github-app/)_._
{% endhint %}

**Org vs. Personal**

Depending on your usage, your entry point for creating a GitHub app will differ:

* Personal Accounts: [`https://github.com/settings/apps/new`](https://github.com/settings/apps/new)\`\`
* GitHub Accounts `https://github.com/organizations/[your-org-name]/settings/apps/new`

You'll be asked provide details for the app, here are the **required** values:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Example</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">GitHub App name</td>
      <td style="text-align:left">Can be anything, suggest using <code>colophon</code> + <code>you-org-name</code> as
        a suffix</td>
      <td style="text-align:left"><em><code>my-company-colophon</code></em>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Homepage URL</td>
      <td style="text-align:left">Set to <code>https://colophon.id</code>
      </td>
      <td style="text-align:left"><code>https://colophon.id</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">User authorization callback URL</td>
      <td style="text-align:left">
        <p>The full URL to redirect to after a user authorizes an installation.</p>
        <p></p>
        <p>Use <code>https://your-app-domain</code> + <code>/auth/callback</code>
        </p>
      </td>
      <td style="text-align:left"><em><code>https://colophon.my-company.com/auth/callback</code></em>
      </td>
    </tr>
  </tbody>
</table>