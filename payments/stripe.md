---
description: Collect payments using stripe.
---

# Stripe

### Subscriptions

In every pricing component the `Pay Now` button is linked with a component called `<CheckoutButton />` button.

The component accepts two props, `mode` and `priceId`

The `mode` can be either `subscription` or `payment` .

And the `priceId` you can get from stripe dashboard when you've created your product.

```tsx
import { CheckoutButton } from '@/components/checkout-button';

<CheckoutButton mode="subscription" priceId="price_1OyFWZSabc5frhqBOQ71f6lQ">
  Get Started
</CheckoutButton>
```

#### Hooks

Use the `src/hooks/use-profile.ts` to check if the user is subscribed or not.

```typescript
import { useProfile } from "@/hooks/use-profile";

const { subscribed } = useProfile()

useEffect(() => {
  if (subscribed) {
    console.log("The user is subscribed")
  }
}, [subscribed])

// Add your business logic based on the the value of `subscribed`.
```

### Database

The `User` model contains a key called `isSubscribed` and `stripeCustomerId`

Whenever a user is subscribed the `isSubscribed` key will return true.

```prisma
model User {
  //--------------//
  isSubscribed     Boolean        @default(false)
  stripeCustomerId String?        @unique
  //--------------//
}
```

### One Time Purchase

```tsx
import { CheckoutButton } from '@/components/checkout-button';

<CheckoutButton mode="payment" priceId="price_1OyFWZSabc5frhqBOQ71f6lQ">
  Get Started
</CheckoutButton>
```

### Database

For one time purchase products, you will need to pass informations such as `productId` and `userId` in the fetch body of the `checkout-session` api.

```typescript
fetch("/api/stripe/checkout-session", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    mode,
    priceId,
    userId: "cluiawmlt00023drn6wcc5v2k",
    productId: "product_1OyFWZSDcM5frhqB1Q71f6lQ",
  })
})
```

Once the product is purchased by the user, you can use the following hook to get the purchases made by the user.

```typescript
import { usePurchases } from "@/hooks/use-purchases";

const { data: purchases } = usePurchases();

useEffect(() => {
  if (purchases.length > 0) {
    console.log(purchases)
  }
}, [purchases])
```

The above will print all the purchases made by the user.
