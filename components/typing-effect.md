---
description: An animated typing effect for your app
---

# Typing Effect

```tsx
import { useTypingEffect } from "@/hooks/use-typing-effect";

const { textToShow } = useTypingEffect({
  isTypeByLetter: true,
  duration: 50,
  texts: ["Text 1", "Text 2"]
});

/**-------------**/
<h3 className="font-semibold text-xl">{textToShow}</h3>
```

<figure><img src="../.gitbook/assets/Apr-07-2024 5-19-54 PM.gif" alt=""><figcaption><p>Animated Text</p></figcaption></figure>
