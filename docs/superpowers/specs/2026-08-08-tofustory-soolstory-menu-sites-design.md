# TofuStory / Sool Story Menu Website Design Spec

## Overview

Three example menu websites for a Korean restaurant at 85 Harvard Ave, Allston, MA 02134, rebranding from a single concept into two:

- **Tofu Story** — daytime lunch + dinner, tofu-focused Korean comfort food
- **Sool Story** (술 이야기) — nighttime drinks + anju (drinking food)

The primary use case is an **in-restaurant QR code menu**. Customers scan at the table and browse the menu on their phones. Mobile-first, image-focused, fast-loading.

## Three Sites to Present

1. **Site 1 — Separate Sites:** Tofu Story and Sool Story as distinct sites that link to each other. Each has its own visual identity.
2. **Site 2 — Combined, Drinks-First:** Single site ordered Drinks → Night Menu → Lunch+Dinner.
3. **Site 3 — Combined, Food-First:** Single site ordered Lunch+Dinner → Drinks → Night Menu.

Recommendation: Site 1 (separate) is the strongest for brand clarity, but all three are built so the owner can compare.

## Tech Stack

- Static HTML/CSS/JS — no frameworks, no build step
- Google Fonts (Noto Serif KR, Noto Sans KR)
- Vanilla JS for scroll-spy category nav and expand/collapse dish details
- Placeholder images as CSS gradients (no external image dependencies for the demo)
- Each site is fully self-contained and can be opened directly in a browser

## Project Structure

```
TofuStory/
├── site1-separate/
│   ├── tofu-story/
│   │   ├── index.html
│   │   ├── styles.css
│   │   └── assets/
│   └── sool-story/
│       ├── index.html
│       ├── styles.css
│       └── assets/
├── site2-drinks-first/
│   ├── index.html
│   ├── styles.css
│   └── assets/
├── site3-food-first/
│   ├── index.html
│   ├── styles.css
│   └── assets/
└── shared/
    └── assets/
```

## Menu Content (Placeholder)

### Drinks Menu (Sool Story)

**Soju Cocktails ($10-$14)**
- Watermelon Soju 수박 소주 — Fresh watermelon blended with chilled soju — $12
- Yuzu Highball 유자 하이볼 — Sparkling yuzu citrus with soju — $13
- Peach Soju 복숭아 소주 — Sweet peach with premium soju — $12
- Grapefruit Soju 자몽 소주 — Tart grapefruit with soju over ice — $12
- Lychee Soju 리치 소주 — Floral lychee with soju — $13

**Makgeolli ($9-$14)**
- Original Makgeolli 막걸리 — Traditional unfiltered rice wine — $9
- Mango Makgeolli 망고 막걸리 — Tropical mango-infused rice wine — $12
- Sparkling Makgeolli 스파클링 막걸리 — Effervescent modern makgeolli — $14

**Beer & More ($8-$16)**
- Hite Extra Cold 하이트 — Korean lager, ice cold — $8
- Cass Fresh 카스 — Light Korean beer — $8
- Sapporo Draft 삿포로 — Japanese premium lager — $9
- Hot Sake 열간 사케 — Warm sake, served traditional — $14

### Night Menu / Anju ($10-$18)

**Small Plates**
- Korean Fried Chicken 양념치킨 — Double-fried, gochujang glaze — $16
- Tteokbokki 떡볶이 — Spicy rice cakes in gochujang sauce — $13
- Kimchi Pancake 김치전 — Crispy kimchi and scallion jeon — $14
- Japchae 잡채 — Glass noodles with seasonal vegetables — $13
- Mandu 만두 — Pan-fried pork and vegetable dumplings — $12
- Corn Cheese 콘치즈 — Sweet corn baked with mozzarella — $11

**Skewers & Grill**
- Bulgogi Skewers 불고기 꼬치 — Marinated beef, grilled — $16
- Spicy Pork Belly 매운 삼겹살 — Thick-cut, gochugaru spiced — $18
- Chicken Yakitori 치킨 야키토리 — Soy-glazed chicken skewers — $14

### Lunch + Dinner Menu (Tofu Story)

**Sundubu Jjigae / Tofu Stews (Base $14.99 vegetarian)**
- Original Sundubu 순두부찌개 — Silky soft tofu in rich, spicy broth — $14.99
- Kimchi Sundubu 김치 순두부 — Aged kimchi with soft tofu stew — $14.99
- Seafood Sundubu 해물 순두부 — Shrimp, clam, and squid tofu stew — $18.99
- Mushroom Sundubu 버섯 순두부 — Wild mushroom medley tofu stew — $14.99
- Dumpling Sundubu 만두 순두부 — Handmade dumplings in tofu stew — $16.99

**Rice Bowls**
- Bulgogi Bowl 불고기 덮밥 — Marinated beef over rice with egg — $16.99
- Spicy Pork Bowl 제육 덮밥 — Gochujang pork over rice — $15.99
- Tofu Bibimbap 두부 비빔밥 — Crispy tofu, vegetables, gochujang — $14.99

**Sides & Extras**
- Steamed Rice 밥 — $2
- Extra Tofu 두부 추가 — $3
- Protein Add-ons: Beef/Chicken/Pork $3, Seafood $4
- Banchan Set 반찬 — Rotating Korean side dishes — Complimentary

## Visual Identity

### Tofu Story (Daytime)

- Background: `#FAF7F2` (warm white)
- Primary accent: `#7A9E7E` (sage green) — category pills, active states
- Text: `#2C2C2C` (charcoal)
- Card overlay: `#E8DFD0` (warm beige) at 90% opacity
- Placeholder gradients: Soft warm tones (creams, light oranges, greens)
- Vibe: Clean, natural, welcoming — bright lunch spot

### Sool Story (Nighttime)

- Background: `#1A1A1A` (deep charcoal)
- Primary accent: `#D4944C` (warm amber) — category pills, active states
- Secondary: `#C9A96E` (muted gold) — prices, subtle details
- Text: `#F5EDE0` (cream)
- Placeholder gradients: Rich dark tones (deep reds, ambers, dark browns)
- Vibe: Moody, intimate, warm — izakaya/bar atmosphere

### Combined Sites (2 & 3)

- Site 2 (drinks-first): Opens with Sool Story dark palette, transitions to Tofu Story light palette via gradient divider
- Site 3 (food-first): Opens with Tofu Story light palette, transitions to Sool Story dark palette via gradient divider

### Typography

- Headings / dish names: `Noto Serif KR` (700 weight)
- Body / descriptions / prices: `Noto Sans KR` (400/500 weight)
- Korean characters displayed alongside English: "Sundubu Jjigae 순두부찌개"

## Mobile-First Layout

### Header (sticky, compact)

- Text-based logo placeholder
- Tagline/subheader beneath
- Tofu Story: "Korean Comfort, Reimagined"
- Sool Story: "술 이야기 — Drinks & Late Night Bites"

### Category Navigation (sticky below header)

- Horizontal scrollable pill buttons
- Taps anchor-scroll to that section
- Active category highlights via scroll-spy (vanilla JS)
- Fixed below header for constant access

### Dish Cards

- Full-width image (16:9 ratio)
- Name + price overlaid on subtle dark gradient at bottom of image
- Cards stack vertically, one per row
- Tap expands inline: description slides down, add-ons appear
- No separate detail pages — single-page scroll

### Footer

- Address: 85 Harvard Ave, Allston, MA 02134
- Phone: (857) 316-2104 (tap-to-call link)
- Email: Tofustory617@gmail.com
- Allergen notice: "Our food may contain peanuts, tree nuts, soy, milk, eggs, wheat, shellfish or fish."
- Site 1 only: Cross-link to sibling site ("Visit Sool Story →" / "Visit Tofu Story →")

## Out of Scope

- Online ordering integration
- Reservation system
- CMS / admin panel
- Backend / database
- Real food photography (placeholder gradients used)
- Logo design (text placeholders)
