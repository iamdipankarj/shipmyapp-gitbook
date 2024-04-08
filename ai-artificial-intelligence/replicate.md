---
description: ShipMyApp comes with built in support for Replicate.
---

# Replicate

[Replicate](https://replicate.com/) is an online AI model provider that you can use to build your AI apps. You can also deploy your own models and use them in your project.

1. Checkout the branch `ai`.

{% code title="Terminal" %}
```git
git checkout ai
```
{% endcode %}

1. Go ahead and create your account on Replicate.
2. Create your api token at [https://replicate.com/account/api-tokens](https://replicate.com/account/api-tokens)
3. Paste it in the `.env` file as shown below.

{% code title=".env" %}
```
REPLICATE_API_KEY=
```
{% endcode %}

4. Go to the route [http://localhost:3000/text-to-image](http://localhost:3000/text-to-image)
5. Run your API model here. Two sample AI models are already integrate to help you understand the workflow.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption><p><a href="http://localhost:3000/text-to-image">http://localhost:3000/text-to-image</a></p></figcaption></figure>
