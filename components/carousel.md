---
description: >-
  An Image slider component that you can use to showcase your work. This is
  typically used in banners and hero sections.
---

# Carousel

```tsx
import {
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselNext,
  CarouselPrevious,
} from "@/components/carousel"

const images = [
  "/carousel/1.jpg",
  "/carousel/2.jpg",
  "/carousel/3.jpg",
  "/carousel/4.jpg",
  "/carousel/5.jpg",
  "/carousel/6.jpg",
  "/carousel/7.jpg"
]

/**------**/
<Carousel>
  <CarouselContent>
    {images.map((image, index) => (
      <CarouselItem key={index}>
        <Image
          className="w-full"
          src={image}
          width={1200}
          height={800}
          alt={image}
          priority
        />
      </CarouselItem>
    ))}
  </CarouselContent>
  <CarouselPrevious />
  <CarouselNext />
</Carousel>
```

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
