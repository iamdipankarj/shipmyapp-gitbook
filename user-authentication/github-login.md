---
description: Adding Github Login is just as easy.
---

# 🔓 Github Login

1. Head over to [https://github.com/settings/tokens](https://github.com/settings/tokens) . In this page, we'll configure our tokens.
2. Click on **Generate new token (classic)**

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption><p>Github Account Settings</p></figcaption></figure>

3. Fill in all the required details.
4. Once you get your **Client ID** and **Client Secret,** paste them in the `.env` file as shown in [environment-variables.md](../environment-variables.md "mention")

```
GITHUB_CLIENT_ID=
GITHUB_CLIENT_SECRET=
```

👏 That is all that is required for setting up Github Auth. Remember that having multiple authentication mechanisms in your app is always beneficial for the end user.&#x20;

While ShipMyApp currently supports only Google and Github as OAuth logins, Next-Auth supports many other popular providers as well [https://next-auth.js.org/providers/](https://next-auth.js.org/providers/). You can integrate them in ShipMyApp in no time. If you need help setting them up, reach out to me at [https://twitter.com/iamdipankarj](https://twitter.com/iamdipankarj)
