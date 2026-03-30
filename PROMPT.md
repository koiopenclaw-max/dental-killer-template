# Dental Killer Template — Full Rebuild

## Goal
Rebuild `index.html` from scratch as a premium, award-worthy dental clinic website template. Single file, no external dependencies except Google Fonts and Lucide Icons CDN.

## Design System

### Palette: Noir Luxe (premium dental)
```
--bg-primary: #0F0F0F        (near-black background)
--bg-secondary: #1A1A1A      (cards, sections)
--bg-elevated: #242424        (hover states, inputs)
--text-primary: #F5F5F5       (main text)
--text-secondary: #A0A0A0     (muted text)
--accent: #C9A96E             (rose gold — primary accent)
--accent-light: #D4BA7A       (rose gold hover)
--accent-dark: #B8943D        (rose gold active)
--white: #FFFFFF
--success: #4CAF50
```

### Typography
```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```
- Headings: `Playfair Display`, serif — elegant, editorial
- Body: `Inter`, sans-serif — clean, modern readability
- H1: clamp(2.8rem, 5vw, 4.2rem)
- H2: clamp(2rem, 3.5vw, 2.8rem)
- Body: 1rem / 1.7 line-height

### Icons: Lucide Icons (CDN)
```html
<script src="https://unpkg.com/lucide@latest"></script>
```
Usage: `<i data-lucide="icon-name"></i>` then call `lucide.createIcons()` in script.

**Icon mapping for services:**
- Имплантология → `crown` (dental crown/implant)
- Естетична стоматология → `sparkles`
- Ортодонтия → `align-horizontal-space-between` (alignment)
- Детска стоматология → `baby` 
- Избелване → `sun`
- Орална хирургия → `scissors`

**Icon mapping for contact:**
- Адрес → `map-pin`
- Телефон → `phone`
- Имейл → `mail`
- Работно време → `clock`

**Other icons:**
- Hero CTA phone → `phone`
- FAQ expand → `plus`
- Checkmarks → `check`
- Star rating → `star`
- Arrow in links → `arrow-right`

## Page Structure

### 1. Header (fixed, glass morphism on scroll)
- Logo: "Д-р Иванова Дентал" — Playfair Display, rose gold accent on "Дентал"
- Nav links: Услуги, За нас, Галерия, Отзиви, Контакти
- Phone: `phone` icon + "0888 123 456" (rose gold)
- CTA button: "Запази час" — solid rose gold, rounded
- Mobile: hamburger menu with full-screen overlay, dark bg
- On scroll: background rgba(15,15,15,0.95) + backdrop-filter blur(20px)

### 2. Hero (full viewport, NO gradient overlay — use a dark dental photo)
- Image: `https://images.unsplash.com/photo-1629909613654-28e377c37b09?w=1600&q=80`
- Dark overlay: rgba(0,0,0,0.6) — simple, NOT gradient
- Badge: small pill — star icon + "Стоматологична клиника от 2009 г." — border: 1px solid rgba(201,169,110,0.4)
- H1: "Грижа за усмивката ви с *внимание към всеки детайл*" — italic part in rose gold
- Subtitle: "Модерна стоматология в сърцето на София..."
- Two buttons: "Запази час →" (solid rose gold) + "0888 123 456" (outline white)
- Content aligned LEFT, max-width 680px, margin-left ~8%

### 3. Trust Strip (dark bg, border top/bottom subtle)
- 3 stats in a row: "15+ Години опит" | "5 000+ Доволни пациенти" | "12 000+ Успешни процедури"
- Numbers in Playfair Display, rose gold color
- Labels in Inter, muted text
- Dividers between items (vertical line, subtle)

### 4. Services Section (bg-primary)
- Section label: "НАШИТЕ УСЛУГИ" — small, uppercase, letter-spacing 0.15em, rose gold
- H2: "Цялостна грижа за вашата усмивка"
- 6 cards in 3×2 grid (2 rows):
  - Card bg: #1A1A1A, border: 1px solid rgba(255,255,255,0.06)
  - Icon in 56×56px box: bg rose gold/dark, icon white
  - Title: Playfair, white
  - Description: Inter, muted text
  - Link: "Научи повече →" rose gold, with arrow icon
  - Hover: border color rgba(201,169,110,0.3), subtle gold glow shadow, translateY(-4px)
  - Top accent line on hover: 2px rose gold, scaleX animation

**Card content:**
1. crown icon → "Имплантология" → "Възстановяване на липсващи зъби с висококачествени импланти и естествен краен резултат."
2. sparkles icon → "Естетична стоматология" → "Фасети, бондинг и дизайн на усмивката за перфектен визуален ефект."
3. align-horizontal-space-between icon → "Ортодонтия" → "Невидими шини и брекети за правилна захапка при деца и възрастни."
4. baby icon → "Детска стоматология" → "Нежна грижа в приятна обстановка — формираме добри навици от малки."
5. sun icon → "Професионално избелване" → "Безопасно и ефективно избелване до 8 нюанса по-бяло за едно посещение."
6. scissors icon → "Орална хирургия" → "Екстракции, костни присадки и хирургични процедури с минимален дискомфорт."

### 5. About Section (bg-secondary #1A1A1A)
- 2-column grid: image left, text right
- Image: `https://images.unsplash.com/photo-1588776814546-1ffcf47267a5?w=800&q=80`, border-radius 12px, height 500px object-fit cover
- Gold decorative border element (3px, positioned bottom-right, offset)
- Badge on image: "15+" + "Години опит" — rose gold bg, white text
- Section label + H2: "Модерна клиника с *човешко отношение*" (italic in rose gold)
- Two paragraphs of text
- 6 features with check icons in rose gold circles:
  - Дигитален скенер
  - 3D планиране
  - Лазерно лечение
  - Седация при нужда
  - Гаранция за импланти
  - Безлихвено разсрочване

### 6. Trust Badges Section (bg-primary, centered)
Place BETWEEN About and Gallery. Two badges side by side, centered:

**Google Reviews Widget (inline SVG, NO external files):**
```html
<div style="display:inline-flex;align-items:center;gap:12px;padding:16px 24px;background:#1A1A1A;border:1px solid rgba(255,255,255,0.08);border-radius:12px;">
  <svg width="36" height="36" viewBox="0 0 48 48"><path fill="#EA4335" d="M24 9.5c3.54 0 6.71 1.22 9.21 3.6l6.85-6.85C35.9 2.38 30.47 0 24 0 14.62 0 6.51 5.38 2.56 13.22l7.98 6.19C12.43 13.72 17.74 9.5 24 9.5z"/><path fill="#4285F4" d="M46.98 24.55c0-1.57-.15-3.09-.38-4.55H24v9.02h12.94c-.58 2.96-2.26 5.48-4.78 7.18l7.73 6c4.51-4.18 7.09-10.36 7.09-17.65z"/><path fill="#FBBC05" d="M10.53 28.59c-.48-1.45-.76-2.99-.76-4.59s.27-3.14.76-4.59l-7.98-6.19C.92 16.46 0 20.12 0 24c0 3.88.92 7.54 2.56 10.78l7.97-6.19z"/><path fill="#34A853" d="M24 48c6.48 0 11.93-2.13 15.89-5.81l-7.73-6c-2.15 1.45-4.92 2.3-8.16 2.3-6.26 0-11.57-4.22-13.47-9.91l-7.98 6.19C6.51 42.62 14.62 48 24 48z"/></svg>
  <div>
    <div style="display:flex;align-items:center;gap:4px;">
      <span style="font-size:1.5rem;font-weight:700;color:#F5F5F5;">4.9</span>
      <svg width="100" height="20" viewBox="0 0 100 20"><polygon fill="#FBBC05" points="10,1 12.5,7 19,8 14,12 15.5,19 10,15.5 4.5,19 6,12 1,8 7.5,7"/><polygon fill="#FBBC05" points="30,1 32.5,7 39,8 34,12 35.5,19 30,15.5 24.5,19 26,12 21,8 27.5,7"/><polygon fill="#FBBC05" points="50,1 52.5,7 59,8 54,12 55.5,19 50,15.5 44.5,19 46,12 41,8 47.5,7"/><polygon fill="#FBBC05" points="70,1 72.5,7 79,8 74,12 75.5,19 70,15.5 64.5,19 66,12 61,8 67.5,7"/><polygon fill="#FBBC05" points="90,1 92.5,7 99,8 94,12 95.5,19 90,15.5 84.5,19 86,12 81,8 87.5,7"/></svg>
    </div>
    <span style="font-size:0.85rem;color:#A0A0A0;">Базирано на 127 отзива</span>
  </div>
</div>
```

**НЗОК Badge (inline SVG, NO external files):**
```html
<div style="display:inline-flex;align-items:center;gap:12px;padding:12px 20px;background:#1A1A1A;border:1px solid rgba(255,255,255,0.08);border-radius:10px;">
  <svg width="40" height="48" viewBox="0 0 50 55"><path d="M25 0 L50 10 L50 30 C50 42 38 50 25 55 C12 50 0 42 0 30 L0 10 Z" fill="#1565C0"/><path d="M18 16h4v8h6v-8h4v22h-4V28h-6v10h-4z" fill="white"/></svg>
  <div>
    <div style="font-weight:700;color:#90CAF9;font-size:1rem;">НЗОК</div>
    <div style="font-size:0.8rem;color:#A0A0A0;">Работим с Национална<br>здравноосигурителна каса</div>
  </div>
</div>
```

### 7. Gallery (bg-primary)
- Section header
- 3 images in grid, aspect-ratio 4/3
- Hover: scale(1.05), overlay with caption
- Images:
  1. `https://images.unsplash.com/photo-1606811841689-23dfddce3e95?w=600&q=80` — "Фасети — пълна трансформация"
  2. `https://images.unsplash.com/photo-1598256989800-fe5f95da9787?w=600&q=80` — "Избелване — 6 нюанса"  
  3. `https://images.unsplash.com/photo-1609840114035-3c981b782dfe?w=600&q=80` — "Имплантиране — горна челюст"

### 8. Testimonials (bg-secondary)
- 3 cards, each with:
  - 5 star icons (Lucide `star`, filled gold #FBBC05)
  - Quote text in italic
  - Author: avatar + name + "Пациент от X години"
  - Card bg: #242424, border: 1px solid rgba(255,255,255,0.06)
- Avatars:
  1. `https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=100&q=80` — Мария Петрова, 3 години
  2. `https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=100&q=80` — Георги Димитров, 5 години
  3. `https://images.unsplash.com/photo-1438761681033-6461ffad8d80?w=100&q=80` — Елена Тодорова, 2 години

**NOTE about stars:** Lucide's `star` icon is outline-only by default. For filled stars, use inline SVG:
```html
<svg width="16" height="16" viewBox="0 0 24 24" fill="#FBBC05" stroke="#FBBC05" stroke-width="1"><polygon points="12,2 15.09,8.26 22,9.27 17,14.14 18.18,21.02 12,17.77 5.82,21.02 7,14.14 2,9.27 8.91,8.26"/></svg>
```
Repeat 5 times per testimonial. Do NOT use Lucide for stars.

### 9. FAQ (bg-primary)
- 5 questions, accordion style
- Plus icon rotates 45deg on open (becomes X)
- Question text: Inter 600, white
- Answer text: Inter 400, muted
- Dividers: 1px solid rgba(255,255,255,0.08)

Questions:
1. "Колко струва първичният преглед?" — 60лв, безплатен при лечение до 30 дни
2. "Работите ли с НЗОК?" — Да, обтурации, екстракции, профилактика
3. "Колко време отнема имплант?" — 30-60 мин, 3-6 мес интеграция
4. "Болезнено ли е избелването?" — Не, лека чувствителност 24-48ч
5. "Предлагате ли разсрочване?" — Да, до 12 мес безлихвено, TBI Bank

### 10. Contact (bg-secondary)
- 2-column: info left, form right
- Contact items with Lucide icons in rose gold boxes (48×48, border-radius 8px)
- Form: dark inputs (bg #1A1A1A, border rgba(255,255,255,0.1)), focus → border rose gold
- Submit button: full-width, rose gold, "Изпрати запитване →"

### 11. Footer (bg #0A0A0A)
- 4-column grid: brand description, nav links, services, contacts
- Bottom bar: "© 2026 Д-р Иванова Дентал. Всички права запазени."
- Link hover: rose gold

## Critical Rules

1. **ALL content must be visible without JavaScript animations.** No opacity:0 on load. No reveal classes.
2. **Copyright year: 2026** — NOT 2025.
3. **Lucide icons** — load via CDN script, call `lucide.createIcons()` at end of body. Exception: star ratings use inline SVG (see above).
4. **Trust badges** use inline SVG as provided above — NO emoji, NO Font Awesome, NO external images.
5. **Mobile breakpoints:** 968px (tablet), 390px (phone). Hamburger menu below 968px.
6. **Bulgarian text** — все content is in Bulgarian. No lorem ipsum.
7. **No horizontal scroll** at any viewport width.
8. **Hover states on ALL interactive elements** — buttons darken + scale(1.02), cards get border glow, links get underline or color change. Transition: 0.2s-0.3s ease.
9. **Left-align body text.** Center-align ONLY: section labels, section titles, footer copyright.
10. **Single file** — everything in index.html (CSS in `<style>`, JS in `<script>`).

## Output

Overwrite `index.html` with the complete rebuilt template. Single file, production-ready.
