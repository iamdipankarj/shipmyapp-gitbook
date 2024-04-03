---
description: A feature section is typically to showcase essential components of your app.
---

# Feature Section

The feature section is a component structure that encourages the use of composition via `children` prop in react. An example below:

```tsx
import { FeatureHeader } from '@/components/feature-header'
import { FeatureDescription } from '@/components/feature-description'
import { FeatureBadge } from '@/components/feature-badge'
import { FeatureListContainer } from '@/components/feature-list-container'
import { FeatureListItem } from '@/components/feature-list-item'
import { FeatureContainer } from '@/components/feature-container'
import { FeatureContent } from '@/components/feature-content'
import { FeatureImage } from '@/components/feature-image'

/**--------**/

<FeatureContainer>
  <FeatureContent>
    <FeatureBadge>20 Hours Saved</FeatureBadge>
    <FeatureHeader>Ready-to-Ship Landing Pages</FeatureHeader>
    <FeatureDescription>Fully responsive, customizable landing pages for your next project. Simply add your content and you&apos;re good to go.</FeatureDescription>
    <FeatureListContainer>
      <FeatureListItem icon={<LayoutTemplate className="h-6 w-6 text-primary" />}>
        Multiple Page Templates
      </FeatureListItem>
      <FeatureListItem icon={<Activity className="h-6 w-6 text-primary" />}>
        Waitlist System
      </FeatureListItem>
      <FeatureListItem icon={<PanelsTopLeft className="h-6 w-6 text-primary" />}>
        Unique Header and Footer components
      </FeatureListItem>
    </FeatureListContainer>
  </FeatureContent>
  <FeatureImage imagePath="/banner1.png" imageHeight={1080} imageWidth={900} />
</FeatureContainer>
```

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption><p>The first feature component in shipmyapp.com</p></figcaption></figure>
