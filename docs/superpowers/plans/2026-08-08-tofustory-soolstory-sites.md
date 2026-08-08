# TofuStory / Sool Story Menu Sites Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build three example menu websites (separate branded, combined drinks-first, combined food-first) for a Korean restaurant rebranding into Tofu Story (day) and Sool Story (night).

**Architecture:** Static HTML/CSS/JS sites, no build step. Each site is self-contained with its own index.html and styles.css. Shared vanilla JS handles scroll-spy category nav and expand/collapse dish cards. CSS gradients serve as placeholder food images.

**Tech Stack:** HTML5, CSS3 (custom properties, flexbox, grid), vanilla JavaScript, Google Fonts (Noto Serif KR, Noto Sans KR)

## Global Constraints

- Mobile-first: design for 375px viewport, scale up to desktop
- No frameworks, no build tools, no npm
- No external image dependencies — CSS gradients only for placeholders
- Google Fonts loaded via `<link>` tags
- Each site openable directly via `file://` or any static server
- All dish names include English + Korean characters
- Tap-to-call phone link on mobile
- Allergen notice in every footer

---

### Task 1: Site 1 — Tofu Story (Daytime Site)

**Files:**
- Create: `site1-separate/tofu-story/index.html`
- Create: `site1-separate/tofu-story/styles.css`

**Interfaces:**
- Consumes: Nothing (first task)
- Produces: Complete standalone daytime menu site; CSS patterns and JS scroll-spy/expand logic reusable as reference for subsequent tasks

- [ ] **Step 1: Create the HTML structure**

Create `site1-separate/tofu-story/index.html` with:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tofu Story — Korean Comfort, Reimagined</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500&family=Noto+Serif+KR:wght@700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <!-- Sticky header -->
  <header class="site-header">
    <h1 class="logo">Tofu Story</h1>
    <p class="tagline">Korean Comfort, Reimagined</p>
  </header>

  <!-- Sticky category nav -->
  <nav class="category-nav">
    <div class="nav-scroll">
      <button class="nav-pill active" data-target="stews">Tofu Stews</button>
      <button class="nav-pill" data-target="bowls">Rice Bowls</button>
      <button class="nav-pill" data-target="sides">Sides & Extras</button>
    </div>
  </nav>

  <main class="menu">
    <!-- Tofu Stews Section -->
    <section id="stews" class="menu-section">
      <h2 class="section-title">Sundubu Jjigae <span class="kr">순두부찌개</span></h2>
      <p class="section-subtitle">Base vegetarian $14.99 &middot; Add protein: Beef/Chicken/Pork +$3, Seafood +$4</p>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image" style="background: linear-gradient(135deg, #E8C9A0 0%, #D4694A 50%, #C0392B 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Original Sundubu <span class="kr">순두부찌개</span></span>
            <span class="dish-price">$14.99</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Silky soft tofu in rich, spicy broth. Our signature dish served bubbling hot in a stone pot.</p>
          <div class="addons">
            <span class="addon">+ Beef $3</span>
            <span class="addon">+ Chicken $3</span>
            <span class="addon">+ Pork $3</span>
            <span class="addon">+ Seafood $4</span>
          </div>
        </div>
      </div>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image" style="background: linear-gradient(135deg, #C0392B 0%, #E74C3C 50%, #D4694A 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Kimchi Sundubu <span class="kr">김치 순두부</span></span>
            <span class="dish-price">$14.99</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Aged kimchi with soft tofu in a deep, fermented broth. Bold and tangy.</p>
          <div class="addons">
            <span class="addon">+ Beef $3</span>
            <span class="addon">+ Chicken $3</span>
            <span class="addon">+ Pork $3</span>
            <span class="addon">+ Seafood $4</span>
          </div>
        </div>
      </div>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image" style="background: linear-gradient(135deg, #2980B9 0%, #3498DB 50%, #E8C9A0 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Seafood Sundubu <span class="kr">해물 순두부</span></span>
            <span class="dish-price">$18.99</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Shrimp, clam, and squid with silky tofu in a rich seafood broth.</p>
        </div>
      </div>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image" style="background: linear-gradient(135deg, #7A9E7E 0%, #8B6914 50%, #E8DFD0 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Mushroom Sundubu <span class="kr">버섯 순두부</span></span>
            <span class="dish-price">$14.99</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Wild mushroom medley with soft tofu in an earthy, savory broth.</p>
          <div class="addons">
            <span class="addon">+ Beef $3</span>
            <span class="addon">+ Chicken $3</span>
            <span class="addon">+ Pork $3</span>
            <span class="addon">+ Seafood $4</span>
          </div>
        </div>
      </div>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image" style="background: linear-gradient(135deg, #E8C9A0 0%, #D4944C 50%, #C0392B 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Dumpling Sundubu <span class="kr">만두 순두부</span></span>
            <span class="dish-price">$16.99</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Handmade dumplings nestled in a spicy soft tofu stew.</p>
        </div>
      </div>
    </section>

    <!-- Rice Bowls Section -->
    <section id="bowls" class="menu-section">
      <h2 class="section-title">Rice Bowls <span class="kr">덮밥</span></h2>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image" style="background: linear-gradient(135deg, #8B4513 0%, #D2691E 50%, #F4A460 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Bulgogi Bowl <span class="kr">불고기 덮밥</span></span>
            <span class="dish-price">$16.99</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Marinated beef over steamed rice with a sunny-side egg and pickled vegetables.</p>
        </div>
      </div>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image" style="background: linear-gradient(135deg, #C0392B 0%, #E74C3C 50%, #F39C12 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Spicy Pork Bowl <span class="kr">제육 덮밥</span></span>
            <span class="dish-price">$15.99</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Gochujang-marinated pork over rice with fresh vegetables.</p>
        </div>
      </div>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image" style="background: linear-gradient(135deg, #7A9E7E 0%, #F4A460 50%, #E8DFD0 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Tofu Bibimbap <span class="kr">두부 비빔밥</span></span>
            <span class="dish-price">$14.99</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Crispy tofu with seasonal vegetables, gochujang sauce, and steamed rice.</p>
        </div>
      </div>
    </section>

    <!-- Sides Section -->
    <section id="sides" class="menu-section">
      <h2 class="section-title">Sides & Extras <span class="kr">반찬</span></h2>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image side-item" style="background: linear-gradient(135deg, #FAF7F2 0%, #E8DFD0 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Steamed Rice <span class="kr">밥</span></span>
            <span class="dish-price">$2</span>
          </div>
        </div>
      </div>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image side-item" style="background: linear-gradient(135deg, #E8DFD0 0%, #F4A460 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Extra Tofu <span class="kr">두부 추가</span></span>
            <span class="dish-price">$3</span>
          </div>
        </div>
      </div>

      <div class="dish-card" data-expanded="false">
        <div class="dish-image side-item" style="background: linear-gradient(135deg, #7A9E7E 0%, #E8DFD0 100%);">
          <div class="dish-overlay">
            <span class="dish-name">Banchan Set <span class="kr">반찬</span></span>
            <span class="dish-price">Free</span>
          </div>
        </div>
        <div class="dish-details">
          <p>Rotating selection of traditional Korean side dishes. Complimentary with any entree.</p>
        </div>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <div class="footer-content">
      <p class="footer-address">85 Harvard Ave, Allston, MA 02134</p>
      <p class="footer-phone"><a href="tel:+18573162104">(857) 316-2104</a></p>
      <p class="footer-allergen">Our food may contain peanuts, tree nuts, soy, milk, eggs, wheat, shellfish or fish.</p>
      <a href="../sool-story/index.html" class="cross-link">Visit Sool Story &rarr;</a>
      <p class="footer-copy">&copy; 2024 Tofu Story Boston</p>
    </div>
  </footer>

  <script>
    // Scroll-spy: highlight active category pill
    const sections = document.querySelectorAll('.menu-section');
    const pills = document.querySelectorAll('.nav-pill');

    const observerOpts = { rootMargin: '-80px 0px -60% 0px', threshold: 0 };
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          pills.forEach(p => p.classList.remove('active'));
          const active = document.querySelector(`[data-target="${entry.target.id}"]`);
          if (active) {
            active.classList.add('active');
            active.scrollIntoView({ behavior: 'smooth', inline: 'center', block: 'nearest' });
          }
        }
      });
    }, observerOpts);
    sections.forEach(s => observer.observe(s));

    // Nav pill click -> smooth scroll
    pills.forEach(pill => {
      pill.addEventListener('click', () => {
        const target = document.getElementById(pill.dataset.target);
        if (target) target.scrollIntoView({ behavior: 'smooth' });
      });
    });

    // Dish card expand/collapse
    document.querySelectorAll('.dish-card').forEach(card => {
      card.addEventListener('click', () => {
        const details = card.querySelector('.dish-details');
        if (!details) return;
        const isExpanded = card.dataset.expanded === 'true';
        card.dataset.expanded = isExpanded ? 'false' : 'true';
      });
    });
  </script>
</body>
</html>
```

- [ ] **Step 2: Create the CSS**

Create `site1-separate/tofu-story/styles.css` with complete Tofu Story daytime styling:

- CSS custom properties for Tofu Story palette
- Mobile-first base (375px), responsive scaling
- Sticky header + sticky category nav
- Horizontal scrollable pill nav
- Full-width dish cards with gradient overlays
- Expand/collapse animation for dish details
- Footer styling
- Typography: Noto Serif KR for headings, Noto Sans KR for body

Color tokens:
```
--bg: #FAF7F2
--accent: #7A9E7E
--text: #2C2C2C
--card-overlay: rgba(232, 223, 208, 0.9)
--text-on-image: #FAF7F2
```

- [ ] **Step 3: Open in browser and verify**

Run: `open site1-separate/tofu-story/index.html`

Verify:
- Header sticks on scroll
- Category pills scroll horizontally and highlight on scroll-spy
- Dish cards show gradient placeholder images with name/price overlay
- Tapping a card expands description
- Footer shows address, tap-to-call phone, allergen notice, cross-link
- Responsive at 375px mobile width

- [ ] **Step 4: Commit**

```bash
git add site1-separate/tofu-story/
git commit -m "feat: add Tofu Story daytime menu site (Site 1)"
```

---

### Task 2: Site 1 — Sool Story (Nighttime Site)

**Files:**
- Create: `site1-separate/sool-story/index.html`
- Create: `site1-separate/sool-story/styles.css`

**Interfaces:**
- Consumes: Same HTML structure and JS patterns from Task 1 (adapted for dark theme and drinks menu)
- Produces: Complete standalone nighttime menu site with Sool Story branding

- [ ] **Step 1: Create the HTML structure**

Create `site1-separate/sool-story/index.html` with the same structural pattern as Tofu Story but with:

- Logo: "Sool Story"
- Tagline: "술 이야기 — Drinks & Late Night Bites"
- Category nav pills: `Soju Cocktails | Makgeolli | Beer & More | Small Plates | Skewers & Grill`
- Menu sections with all drinks menu items (5 soju cocktails, 3 makgeolli, 4 beer & more) and night menu items (6 small plates, 3 skewers)
- Placeholder gradients in dark/warm tones (deep reds, ambers, dark browns)
- Cross-link in footer: "Visit Tofu Story →" pointing to `../tofu-story/index.html`
- Same JS scroll-spy and expand/collapse logic

Dish cards for drinks section — each with:
- Dark-toned gradient placeholder
- Drink name (English + Korean)
- Price

Dish cards for night menu — each with:
- Warm-toned gradient placeholder
- Dish name (English + Korean)
- Price
- Expandable description

All menu items from spec:

**Soju Cocktails:** Watermelon Soju $12, Yuzu Highball $13, Peach Soju $12, Grapefruit Soju $12, Lychee Soju $13

**Makgeolli:** Original $9, Mango $12, Sparkling $14

**Beer & More:** Hite Extra Cold $8, Cass Fresh $8, Sapporo Draft $9, Hot Sake $14

**Small Plates:** Korean Fried Chicken $16, Tteokbokki $13, Kimchi Pancake $14, Japchae $13, Mandu $12, Corn Cheese $11

**Skewers & Grill:** Bulgogi Skewers $16, Spicy Pork Belly $18, Chicken Yakitori $14

- [ ] **Step 2: Create the CSS**

Create `site1-separate/sool-story/styles.css` — same structure as Tofu Story CSS but with Sool Story dark palette:

Color tokens:
```
--bg: #1A1A1A
--accent: #D4944C
--accent-secondary: #C9A96E
--text: #F5EDE0
--card-overlay: rgba(26, 26, 26, 0.85)
--text-on-image: #F5EDE0
```

Same layout patterns, same responsive breakpoints, adapted for dark background.

- [ ] **Step 3: Open in browser and verify**

Run: `open site1-separate/sool-story/index.html`

Verify:
- Dark, moody aesthetic with amber/gold accents
- All 5 category pills present and scrollable
- Drinks and food items display correctly
- Cross-link to Tofu Story works
- Mobile responsive at 375px

- [ ] **Step 4: Commit**

```bash
git add site1-separate/sool-story/
git commit -m "feat: add Sool Story nighttime menu site (Site 1)"
```

---

### Task 3: Site 2 — Combined, Drinks-First

**Files:**
- Create: `site2-drinks-first/index.html`
- Create: `site2-drinks-first/styles.css`

**Interfaces:**
- Consumes: HTML patterns and JS from Tasks 1-2
- Produces: Single combined site with dark-to-light visual transition

- [ ] **Step 1: Create the HTML structure**

Create `site2-drinks-first/index.html` with:

- Header: "Tofu Story & Sool Story" or a combined branding
- Tagline: "Day & Night — Korean Kitchen & Bar"
- Category nav: `Soju Cocktails | Makgeolli | Beer & More | Small Plates | Skewers & Grill | Tofu Stews | Rice Bowls | Sides`
- All menu sections in order: Drinks → Night Menu → Lunch+Dinner
- A visual divider/transition section between night menu and lunch+dinner where the palette shifts from dark to light
- Same JS scroll-spy and expand/collapse logic
- Footer with address, phone, allergen notice (no cross-link needed)

All menu items from both Sool Story and Tofu Story specs combined into one page.

- [ ] **Step 2: Create the CSS**

Create `site2-drinks-first/styles.css` with:

- Dark palette for the top portion (drinks + night menu) using Sool Story colors
- Light palette for the bottom portion (lunch + dinner) using Tofu Story colors
- A gradient divider section: `background: linear-gradient(to bottom, #1A1A1A, #FAF7F2)` with a decorative separator
- Category nav adapts color based on scroll position (dark pills when in dark section, light pills when in light section) — or stays neutral (e.g., semi-transparent dark background with white text throughout)
- Same responsive patterns

- [ ] **Step 3: Open in browser and verify**

Run: `open site2-drinks-first/index.html`

Verify:
- Dark section flows into light section with smooth transition
- All menu items present from both menus
- Category nav works across all sections
- Mobile responsive at 375px

- [ ] **Step 4: Commit**

```bash
git add site2-drinks-first/
git commit -m "feat: add combined drinks-first menu site (Site 2)"
```

---

### Task 4: Site 3 — Combined, Food-First

**Files:**
- Create: `site3-food-first/index.html`
- Create: `site3-food-first/styles.css`

**Interfaces:**
- Consumes: HTML patterns and JS from Tasks 1-3
- Produces: Single combined site with light-to-dark visual transition

- [ ] **Step 1: Create the HTML structure**

Create `site3-food-first/index.html` with:

- Header: "Tofu Story & Sool Story" or combined branding
- Tagline: "Day & Night — Korean Kitchen & Bar"
- Category nav: `Tofu Stews | Rice Bowls | Sides | Soju Cocktails | Makgeolli | Beer & More | Small Plates | Skewers & Grill`
- All menu sections in order: Lunch+Dinner → Drinks → Night Menu
- Visual divider/transition section between lunch+dinner and drinks where palette shifts from light to dark
- Same JS scroll-spy and expand/collapse logic
- Footer with address, phone, allergen notice

All menu items from both Tofu Story and Sool Story specs combined, reversed order from Site 2.

- [ ] **Step 2: Create the CSS**

Create `site3-food-first/styles.css` with:

- Light palette for the top portion (lunch + dinner) using Tofu Story colors
- Dark palette for the bottom portion (drinks + night menu) using Sool Story colors
- Gradient divider: `background: linear-gradient(to bottom, #FAF7F2, #1A1A1A)`
- Same nav and responsive patterns as Site 2

- [ ] **Step 3: Open in browser and verify**

Run: `open site3-food-first/index.html`

Verify:
- Light section flows into dark section with smooth transition
- All menu items present
- Category nav works across all sections
- Mobile responsive at 375px

- [ ] **Step 4: Commit**

```bash
git add site3-food-first/
git commit -m "feat: add combined food-first menu site (Site 3)"
```

---

### Task 5: Final Polish & Cross-Site Verification

**Files:**
- Modify: All four HTML files and four CSS files as needed

**Interfaces:**
- Consumes: All four completed sites from Tasks 1-4
- Produces: Polished, consistent, presentation-ready set of three example sites

- [ ] **Step 1: Visual consistency pass**

Open all four HTML files side by side. Check:
- Typography is consistent (same font weights, sizes across all sites)
- Dish card dimensions and spacing match
- Gradient placeholders look appetizing and varied (no two adjacent cards same gradient)
- Category pill styling is consistent
- Footer layout matches across all sites

Fix any inconsistencies.

- [ ] **Step 2: Mobile testing**

Test each site at 375px width in browser dev tools:
- Header doesn't overflow
- Category nav scrolls horizontally without breaking
- Dish cards are full-width with readable text
- Tap targets are at least 44px
- No horizontal scroll on the page body
- Expand/collapse works on touch

Fix any mobile issues.

- [ ] **Step 3: Cross-links verification (Site 1 only)**

- From Tofu Story, click "Visit Sool Story →" — verify it loads
- From Sool Story, click "Visit Tofu Story →" — verify it loads

- [ ] **Step 4: Final commit**

```bash
git add -A
git commit -m "polish: final consistency and mobile fixes across all sites"
```
