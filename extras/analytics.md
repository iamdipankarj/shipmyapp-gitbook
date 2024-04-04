---
description: >-
  Use analytics to evaulate a product is crucial for any online business.
  Collect the basic analytics with a privacy focused analytics tool.
  Plausible.io is a good option to start with.
---

# Analytics

### 🔧 Setup

Add this following snippet to `src/app/layout.tsx` inside the `<head />` component.

```html
<link rel="preconnect" href="https://plausible.io" crossOrigin="anonymous" />
<script defer data-domain="YOUR_DOMAIN" src="https://plausible.io/js/script.js" />
```

### Prevent Ad-blockers from blocking your script

Some browsers and ad-blockers might block the requests to the Plausible javascript file.

Next, Add this to `next.config.ts`

```typescript
async rewrites() {
    return [
      {
        source: "/plausible/js/script.js",
        destination: "https://plausible.io/js/script.js",
      },
      {
        source: "/plausible/api/event",
        destination: "https://plausible.io/api/event",
      },
    ];
}
```

After you add the rewrites, update the snipped in the `<head />` element that you added previously.

```html
<script defer data-domain="YOUR_DOMAIN" src="/plausible/js/script.js" />
```

👏 That is it. Once your site is live, you should be able to collect your analytics data immediately.
