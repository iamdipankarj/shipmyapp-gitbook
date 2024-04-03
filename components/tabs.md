---
description: Use Tabs for segmented contents.
---

# Tabs

```tsx
import { Tab } from "@/components/tab";
import { TabContainer } from "@/components/tab-container";

/**----------**/

<TabContainer className="max-w-64 mx-auto mb-4">
  <Tab onClick={() => setSelectedTab(0)} selected={selectedTab == 0}>Monthly</Tab>
  <Tab onClick={() => setSelectedTab(1)} selected={selectedTab == 1}>Yearly</Tab>
</TabContainer>
<div className="text-center">
  {selectedTab == 0 ? (
    <p>Monthly subscription content</p>
  ) : (
    <p>Yearly subscription content</p>
  )}
</div>
```

<figure><img src="../.gitbook/assets/Apr-03-2024 6-18-57 PM.gif" alt=""><figcaption></figcaption></figure>
