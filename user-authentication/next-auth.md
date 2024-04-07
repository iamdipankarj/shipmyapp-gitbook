---
description: User authentication using Next-Auth.
cover: ../.gitbook/assets/32dd-article-220805-nextauth-main-final_copy.jpg
coverY: 0
---

# 🔓 Next-Auth

### Google Login

ShipMyApp supports [NextAuth](https://next-auth.js.org/) to authenticate users. You can configure it in the `/src/app/api/auth/[...nextauth]/route.ts` file.

With NextAuth you can create two types of authentications such as Magic Links and Social Authentication using Google and Github.

<figure><img src="../.gitbook/assets/signin.png" alt=""><figcaption><p>Login Page</p></figcaption></figure>

### Configuring Google OAuth

1. Login to [https://console.cloud.google.com/](https://console.cloud.google.com/)
2. Create a new Project under **`APIs & Services`**
3. Navigate to **`OAuth consent screen`**
4. Fill in all the required details.
5. Set the scope to `userinfo.email` and `userinfo.profile`
6. Submit
7. Navigate to **`Credentials`**
8. Click on **`Create Credentials`**

<figure><img src="../.gitbook/assets/Screenshot 2024-04-03 at 3.00.13 PM.png" alt=""><figcaption></figcaption></figure>

9. Select **`OAuth Client ID`**
10. Select **`Web Application`**
11. Add http://localhost:3000 and https://yoursitename.com into the Authorized JavaScript Origins.
12. Add `http://localhost:3000/api/auth/callback/google` and `https://yoursitename.com/api/auth/callback/google` to Authorized redirect URLs.
13. Click **`Submit`**
14. Copy and paste the Client ID and Client Secret into the `.env` file as shown in [environment-variables.md](../environment-variables.md "mention")

{% code title=".env" %}
```
GOOGLE_CLIENT_ID=""
GOOGLE_CLIENT_SECRET=""
```
{% endcode %}

15. Go to "**OAuth Consent Screen**" and click "**Publish App**".
16. Google might request you to verify your domain in [Google Search Console](https://search.google.com/search-console). It requires you to configure a CNAME or TXT DNS record.

#### 👏 That is all. Now that you have setup the basic OAuth settings, the Google Login is already configured in the project. You should be able to login now.

***

### Github Login

1. Head over to [https://github.com/settings/tokens](https://github.com/settings/tokens) . In this page, we'll configure our tokens.
2. Click on **Generate new token (classic)**

<figure><img src="../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption><p>Github Account Settings</p></figcaption></figure>

3. Fill in all the required details.
4. Once you get your **Client ID** and **Client Secret,** paste them in the `.env` file as shown in [environment-variables.md](../environment-variables.md "mention")

{% code title=".env" %}
```
GITHUB_CLIENT_ID=
GITHUB_CLIENT_SECRET=
```
{% endcode %}

👏 That is all that is required for setting up Github Auth. Remember that having multiple authentication mechanisms in your app is always beneficial for the end user.&#x20;

While ShipMyApp currently supports only Google and Github as OAuth logins, Next-Auth supports many other popular providers as well [https://next-auth.js.org/providers/](https://next-auth.js.org/providers/). You can integrate them in ShipMyApp in no time. If you need help setting them up, reach out to me at [https://twitter.com/iamdipankarj](https://twitter.com/iamdipankarj)
