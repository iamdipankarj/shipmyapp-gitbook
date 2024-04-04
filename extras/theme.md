---
description: Use built-in color themes to give your site the unique look and feel.
---

# Theme

ShipMyApp uses [DaisyUI](https://daisyui.com/docs/themes/) for theming. But also, ships with a custom theme named `signal`.

You can see the theme configrations in `tailwind.config.ts`

To change the theme, simple navigate to `src/app/layout.tsx` and replace the `data-theme`  attribute value with the ones as shown in the image below.

```html
<html lang="en" suppressHydrationWarning data-theme="darcula">
<!-------->
```

You can also override any built-in theme and also generate your own theme using [https://daisyui.com/theme-generator/](https://daisyui.com/theme-generator/).

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption><p>Image from daisyui.com</p></figcaption></figure>

