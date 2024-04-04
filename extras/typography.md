---
description: >-
  ShipMyApp currently uses Google Fonts for text and headings. Simple replace
  the font import and you are set.
---

# Typography

> 💡TIP: Make sure to check the possible weights before choosing a font from [https://fonts.google.com/](https://fonts.google.com/)

{% code title="src/app/layout.tsx" %}
```tsx
import { Gabarito as FontSans } from "next/font/google";

const fontSans = FontSans({
  subsets: ["latin"],
  variable: "--font-sans",
})

<body className={fontSans.variable}>
  /* ...... */
</body>
```
{% endcode %}
