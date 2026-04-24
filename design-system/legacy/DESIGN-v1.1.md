---
title: "DESIGN.md — LeadUp AI (v1.1, DEPRECATED)"
project: company
type: deliverable
status: deprecated
version: "1.1"
supersededBy: "/vault/company/brand/README.md + colors_and_type.css (Design System v3)"
deprecatedOn: "2026-04-24"
deprecatedBy: "Лена (AI Designer) — LEA-476"
owner: "Миша (WebDeveloper)"
contributors: ["Лена (AI Designer)"]
reviewers: ["Лена (AI Designer) — done 2026-04-18", "Алекс (CEO) — approved 2026-04-18"]
created: "2026-04-18"
updated: "2026-04-24"
tags: [design, brand, landing, ui, leadup-ai, deprecated, v1.1]
---

> ⚠️ **DEPRECATED · 2026-04-24.** Этот документ — v1.1 (blue `#2563EB` + slate + Inter). Заменён **Design System v3** (teal `#00E5C7` + green-tinted near-black + Geist). Используй [`../README.md`](../README.md) и [`../colors_and_type.css`](../colors_and_type.css) как canonical для новых работ.
>
> **Что здесь ещё ценно:** §6 Client Logos Policy — правила stub/consent/testimonials. Перенос в v3 запланирован (порт в корневой `brand/` документ — см. LEA-476).
> **Миграция production-лендингов v1.1 → v3** трекается в LEA-477.

---

# DESIGN.md — LeadUp AI (v1.1, archived)

> AI-agent readable design system. Use this as the single source of truth when generating landing pages, marketing materials, and UI components for LeadUp AI.

## Brand Context

LeadUp AI — экосистема AI-трансформации бизнеса. Мы говорим как умный коллега: практично, без воды, современно. Голос бренда — [tone-of-voice.md](./tone-of-voice.md).

---

## Visual Identity

### Colors

```css
/* Primary palette */
--color-primary:     #2563EB;  /* CTA, links, headings */
--color-primary-hover: #1D4ED8;
--color-dark:         #0F172A;  /* Hero backgrounds, dark sections */
--color-dark-secondary: #1E293B;
--color-white:        #FFFFFF;

/* Accents */
--color-cyan:        #06B6D4;  /* Hover states, icons, highlights */
--color-violet:       #7C3AED;  /* Premium products, Нейромастерская */
--color-emerald:      #10B981;  /* Success, confirmations */
--color-amber:        #F59E0B;  /* Warnings, important notes */

/* Neutrals (Slate) */
--color-slate-50:  #F8FAFC;  /* Light section backgrounds */
--color-slate-200: #E2E8F0;  /* Borders, dividers */
--color-slate-400: #94A3B8;  /* Secondary text, placeholders */
--color-slate-600: #475569;  /* Body text on light */
--color-slate-800: #1E293B;  /* Headings on light */

/* Gradients */
--gradient-brand:   linear-gradient(135deg, #2563EB 0%, #7C3AED 100%);
--gradient-dark:    linear-gradient(180deg, #0F172A 0%, #1E293B 100%);
--gradient-accent: linear-gradient(90deg, #06B6D4 0%, #2563EB 100%);
```

### Typography

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

| Role | Font | Weights |
|------|------|---------|
| Headlines H1–H3 | Inter | 700, 800 |
| Subheadings H4–H6 | Inter | 600 |
| Body | Inter | 400, 500 |
| Code/tech | JetBrains Mono | 400, 500 |

**Scale:**
- H1: 56px / 3.5rem — line-height 1.1 — **letter-spacing: -0.02em** (tighter spacing for premium feel)
- H2: 40px / 2.5rem — line-height 1.2 — **letter-spacing: -0.01em**
- H3: 32px / 2rem — line-height 1.3
- H4: 24px / 1.5rem — line-height 1.4
- Body: 16px / 1rem — line-height 1.6
- Small: 14px / 0.875rem

**Gradient text for hero headlines:**
```css
.gradient-text {
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```
**Usage rule:** Maximum **one gradient-text per screen** — otherwise becomes visual noise.

### Spacing

Base unit: **4px**. All spacing is a multiple of 4.

```css
--space-1: 4px;   --space-2: 8px;   --space-3: 12px;
--space-4: 16px;  --space-5: 20px;  --space-6: 24px;
--space-8: 32px;  --space-10: 40px; --space-12: 48px;
--space-16: 64px; --space-20: 80px; --space-24: 96px;
```

### Container

```css
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}
@media (max-width: 768px) {
  .container { padding: 0 16px; }
}
```

---

## Components

### Buttons

```css
.btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 12px 24px;
  border-radius: 8px;
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
  border: 2px solid transparent;
  text-decoration: none;
}

/* Primary — main CTA */
.btn-primary {
  background: var(--color-primary);
  color: var(--color-white);
  border-color: var(--color-primary);
}
.btn-primary:hover {
  background: var(--color-primary-hover);
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(37, 99, 235, 0.3);
}

/* Secondary — outline */
.btn-secondary {
  background: transparent;
  color: var(--color-primary);
  border-color: var(--color-primary);
}
.btn-secondary:hover {
  background: #DBEAFE;
}

/* Ghost — on dark backgrounds */
.btn-ghost {
  background: rgba(255, 255, 255, 0.1);
  color: var(--color-white);
  border-color: rgba(255, 255, 255, 0.2);
}
.btn-ghost:hover {
  background: rgba(255, 255, 255, 0.2);
}

/* Gradient CTA — premium actions */
.btn-gradient {
  background: var(--gradient-brand);
  color: var(--color-white);
  border: none;
}
.btn-gradient:hover {
  opacity: 0.9;
  transform: translateY(-1px);
  box-shadow: 0 8px 24px rgba(37, 99, 235, 0.4);
}

/* Sizes */
.btn-sm  { padding: 8px 16px; font-size: 14px; }
.btn-lg  { padding: 16px 32px; font-size: 18px; border-radius: 10px; }
```

### Cards

```css
/* Light card */
.card {
  background: var(--color-white);
  border: 1px solid var(--color-slate-200);
  border-radius: 12px;
  padding: 24px;
  transition: all 0.2s ease;
}
.card:hover {
  border-color: var(--color-primary);
  box-shadow: 0 4px 24px rgba(37, 99, 235, 0.08);
  transform: translateY(-2px);
}

/* Dark card */
.card-dark {
  background: var(--color-dark-secondary);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  padding: 24px;
  color: var(--color-white);
}

/* Gradient border card */
.card-gradient {
  position: relative;
  background: var(--color-white);
  border-radius: 12px;
  padding: 24px;
}
.card-gradient::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: 12px;
  padding: 1px;
  background: var(--gradient-brand);
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
}
```

### Badges / Tags

```css
.badge {
  display: inline-flex;
  align-items: center;
  gap: 4px;
  padding: 4px 12px;
  border-radius: 100px;
  font-size: 14px;
  font-weight: 500;
}

.badge-primary { background: #DBEAFE; color: #2563EB; }
.badge-violet  { background: #EDE9FE; color: #7C3AED; }
.badge-emerald { background: #D1FAE5; color: #10B981; }
.badge-amber   { background: #FEF3C7; color: #F59E0B; }
```

### Form Inputs

```css
.input {
  width: 100%;
  padding: 12px 16px;
  background: var(--color-white);
  border: 1px solid var(--color-slate-200);
  border-radius: 8px;
  font-family: 'Inter', sans-serif;
  font-size: 16px;
  color: var(--color-dark);
  transition: border-color 0.2s;
  outline: none;
}
.input:focus {
  border-color: var(--color-primary);
  box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
}

.input-dark {
  background: var(--color-dark-secondary);
  border-color: rgba(255, 255, 255, 0.1);
  color: var(--color-white);
}
.input-dark:focus {
  border-color: var(--color-cyan);
}
```

### Icons

Library: [Lucide](https://lucide.dev/) (outline style, not filled)

```html
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
<i data-lucide="zap" class="icon-md"></i>
```

```css
.icon-sm { width: 16px; height: 16px; }
.icon-md { width: 20px; height: 20px; }
.icon-lg { width: 24px; height: 24px; }
.icon-xl { width: 32px; height: 32px; }

/* Icon in a circle */
.icon-box {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: #DBEAFE;
  color: #2563EB;
}
```

### Shadows

```css
--shadow-sm:   0 1px 3px rgba(0, 0, 0, 0.08);
--shadow-md:   0 4px 12px rgba(0, 0, 0, 0.08);
--shadow-lg:   0 8px 24px rgba(0, 0, 0, 0.1);
--shadow-xl:   0 16px 48px rgba(0, 0, 0, 0.12);
--shadow-brand: 0 8px 24px rgba(37, 99, 235, 0.3);
```

### Border Radius

```css
--radius-sm:   4px;
--radius-md:   8px;
--radius-lg:   12px;
--radius-xl:   16px;
--radius-2xl:  24px;
--radius-full: 9999px;
```

---

## Page Sections

### Hero

```css
.hero {
  background: var(--gradient-dark);
  color: var(--color-white);
  padding: 96px 0;
  text-align: center;
}
```

### Standard Section

```css
.section     { padding: 96px 0; }
.section-sm  { padding: 64px 0; }
.section-alt { background: var(--color-slate-50); }
```

---

## Animated Backgrounds

Premium depth effect for hero sections. Combines a slow-drifting aurora mesh gradient with a subtle SVG grain overlay. Reference implementation: `neuro-20-pilot/index.html` (commit `6813ccb`).

```css
/* Host: any hero/section with dark background */
.hero {
  position: relative;
  overflow: hidden;
  isolation: isolate; /* required — keeps pseudo-layers below content */
}

/* Aurora mesh — 4 radial blobs, slow drift animation */
.hero::before {
  content: '';
  position: absolute;
  inset: -30%;
  z-index: -2;
  background:
    radial-gradient(at 20% 18%, rgba(37, 99, 235, 0.55) 0px, transparent 42%),
    radial-gradient(at 82% 12%, rgba(124, 58, 237, 0.50) 0px, transparent 45%),
    radial-gradient(at 64% 78%, rgba(6, 182, 212, 0.40) 0px, transparent 42%),
    radial-gradient(at 14% 82%, rgba(124, 58, 237, 0.35) 0px, transparent 40%);
  filter: blur(28px);
  animation: aurora-drift 22s ease-in-out infinite alternate;
}
@keyframes aurora-drift {
  0%   { transform: translate3d(0, 0, 0) scale(1); }
  50%  { transform: translate3d(-4%, 3%, 0) scale(1.05); }
  100% { transform: translate3d(3%, -2%, 0) scale(1.08); }
}

/* Grain overlay — inline SVG fractal noise, ~100 bytes extra */
.hero::after {
  content: '';
  position: absolute;
  inset: 0;
  z-index: -1;
  pointer-events: none;
  opacity: 0.05;
  mix-blend-mode: overlay;
  background-image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='200' height='200'><filter id='n'><feTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='2' stitchTiles='stitch'/><feColorMatrix values='0 0 0 0 1 0 0 0 0 1 0 0 0 0 1 0 0 0 1 0'/></filter><rect width='200' height='200' filter='url(%23n)' opacity='0.8'/></svg>");
}

/* Place content above layers */
.hero-content { position: relative; z-index: 1; }
```

**Tokens:** 22s drift cycle · `blur(28px)` · opacity 0.05 grain with `mix-blend-mode: overlay` · `inset: -30%` to hide edges during scale.

**Usage rule:** Максимум **один aurora hero на страницу**. Не использовать на секциях с плотным текстом или формами — contrast падает. На мобильных браузерах (`prefers-reduced-motion: reduce`) анимация выключается автоматически — см. Motion Design Tokens.

---

## Premium Components

### Radial glow under headline

Focal depth behind H1. Мягкое свечение в двух бренд-цветах за текстом.

```css
.hero h1 { position: relative; }
.hero h1::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  width: 120%;
  height: 260%;
  z-index: -1;
  background: radial-gradient(
    closest-side,
    rgba(124, 58, 237, 0.35),
    rgba(37, 99, 235, 0.22),
    transparent 70%
  );
  filter: blur(48px);
  pointer-events: none;
}
```

### Gradient border beam (featured card)

Анимированный conic-gradient border для VIP/рекомендованной карточки. Вращение 6s linear infinite.

```css
.card-featured {
  position: relative;
  background: linear-gradient(#fff, #fff) padding-box,
              var(--gradient-brand) border-box;
  border: 2px solid transparent;
  border-radius: var(--radius-xl);
  overflow: hidden;
  isolation: isolate;
  box-shadow:
    0 0 0 1px rgba(124, 58, 237, 0.10),
    0 18px 40px rgba(37, 99, 235, 0.14);
}
.card-featured::before {
  content: '';
  position: absolute;
  inset: -2px;
  z-index: -2;
  border-radius: inherit;
  background: conic-gradient(
    from 0deg,
    transparent 0deg,
    rgba(37, 99, 235, 0.55) 60deg,
    rgba(124, 58, 237, 0.70) 120deg,
    transparent 180deg,
    transparent 360deg
  );
  animation: beam-rotate 6s linear infinite;
  filter: blur(2px);
  opacity: 0.85;
}
@keyframes beam-rotate {
  0%   { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
```

### Glass card (frosted surface)

Полупрозрачная поверхность с `backdrop-filter` — для sticky bar, date/countdown-бейджей, premium overlay.

```css
/* Medium: sticky bar, hero CTA rails */
.glass {
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.14);
  backdrop-filter: saturate(180%) blur(16px);
  -webkit-backdrop-filter: saturate(180%) blur(16px);
  border-radius: var(--radius-md);
}

/* Subtle: countdown tiles, date badges */
.glass-sm {
  background: rgba(255, 255, 255, 0.04);
  border: 1px solid rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(8px);
  -webkit-backdrop-filter: blur(8px);
  border-radius: var(--radius-lg);
}
```

**Usage rules:**
- **Radial glow** — только под одним H1 на странице (hero). Не дублировать на H2.
- **Gradient border beam** — один `card-featured` на экран. Pricing VIP, premium product, "Рекомендуем" — всё что угодно, но только ОДНО.
- **Glass** — хорошо работает поверх `aurora` или `--color-dark`. На светлом фоне теряется, тогда используй `.card` или `.card-gradient`.

---

## Motion Design Tokens

### Baseline transitions (v1.0)

- **Hover transitions:** `all 0.2s ease`
- **Transforms:** `translateY(-1px)` on button hover, `translateY(-2px)` → `translateY(-4px)` on card hover
- **Box shadows on hover** for buttons/cards
- **No aggressive animations** — subtle and purposeful

### Scroll-reveal (v1.1)

Плавное появление секций при скролле через IntersectionObserver. Всегда парно с `prefers-reduced-motion` fallback.

```css
.reveal {
  opacity: 0;
  transform: translateY(24px);
  transition:
    opacity 0.7s cubic-bezier(0.4, 0, 0.2, 1),
    transform 0.7s cubic-bezier(0.4, 0, 0.2, 1);
  will-change: opacity, transform;
}
.reveal.in {
  opacity: 1;
  transform: none;
}
```

```js
if ('IntersectionObserver' in window) {
  const io = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('in');
        io.unobserve(entry.target);
      }
    });
  }, { threshold: 0.12, rootMargin: '0px 0px -40px 0px' });
  document.querySelectorAll('.reveal').forEach(el => io.observe(el));
} else {
  // No IO support → show everything immediately
  document.querySelectorAll('.reveal').forEach(el => el.classList.add('in'));
}
```

### Accessibility: `prefers-reduced-motion` (required)

Любая страница с `.reveal`, `aurora`, `beam-rotate` **обязана** иметь media-query fallback:

```css
@media (prefers-reduced-motion: reduce) {
  .reveal { opacity: 1; transform: none; transition: none; }
  .hero::before,
  .card-featured::before { animation: none; }
}
```

### Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `--motion-hover` | `all 0.2s ease` | Buttons, cards, links |
| `--motion-reveal` | `0.7s cubic-bezier(0.4, 0, 0.2, 1)` | Scroll-reveal opacity/transform |
| `--motion-reveal-distance` | `translateY(24px)` | Initial offset before `.in` |
| `--motion-aurora` | `22s ease-in-out infinite alternate` | Hero background drift |
| `--motion-beam` | `6s linear infinite` | Featured card border rotation |
| `--motion-sticky-bar` | `0.35s cubic-bezier(0.4, 0, 0.2, 1)` | Sticky header reveal |
| IO threshold | `0.12` | Reveal trigger position |
| IO rootMargin | `0px 0px -40px 0px` | Delay trigger by 40px |
| Sticky scroll threshold | `400px` | When sticky bar becomes visible |

**Rule:** Above-the-fold content (hero, first CTA) **никогда не оборачивать в `.reveal`** — пользователь должен сразу видеть оффер без ожидания IO.

---

## Social Proof Patterns

Трёхуровневый stack для доверия на лендинге: **logo wall → stat cards → dark testimonials**. Использовать вместе, в этом порядке, в одной секции.

### Logo wall

6→3→2 responsive grid с grayscale placeholders (или реальными логотипами, если есть согласие — см. Client Logos Policy ниже).

```css
.logo-wall {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  gap: var(--space-8);
  align-items: center;
  margin-bottom: var(--space-16);
}
@media (max-width: 900px) { .logo-wall { grid-template-columns: repeat(3, 1fr); } }
@media (max-width: 480px) { .logo-wall { grid-template-columns: repeat(2, 1fr); } }

.logo-placeholder {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 56px;
  border-radius: var(--radius-md);
  background: rgba(15, 23, 42, 0.04);
  color: var(--color-slate-500);
  font-weight: 600;
  font-size: 14px;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  filter: grayscale(1);
  opacity: 0.75;
  transition: opacity 0.2s ease, filter 0.2s ease;
}
.logo-placeholder:hover { opacity: 1; filter: grayscale(0); }
```

### Stat cards

3 метрики в ряд. `stat-value` использует `.gradient-text` правило (с Firefox-fallback — см. Accessibility & Cross-Browser).

```css
.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-6);
  margin-bottom: var(--space-16);
}
@media (max-width: 768px) { .stats-grid { grid-template-columns: 1fr; } }

.stat-card {
  text-align: center;
  padding: var(--space-8) var(--space-6);
  background: var(--color-white);
  border: 1px solid var(--color-slate-200);
  border-radius: var(--radius-xl);
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}
.stat-card:hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow-xl);
}
.stat-value {
  font-size: 3rem;
  font-weight: 800;
  line-height: 1;
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent;
  margin-bottom: var(--space-3);
  letter-spacing: -0.02em;
}
.stat-label {
  color: var(--color-slate-600);
  font-size: 16px;
  font-weight: 500;
}
```

### Dark testimonial card

2-column grid, тёмный фон + violet radial glow в углу, круглый аватар (реальное фото или инициалы).

```css
.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: var(--space-6);
}
@media (max-width: 768px) { .testimonials-grid { grid-template-columns: 1fr; } }

.testimonial {
  background: var(--color-slate-900);
  color: rgba(255, 255, 255, 0.88);
  border-radius: var(--radius-xl);
  padding: var(--space-8);
  position: relative;
  overflow: hidden;
  isolation: isolate;
}
.testimonial::before {
  content: '';
  position: absolute;
  inset: 0;
  z-index: -1;
  background: radial-gradient(at 90% 0%, rgba(124, 58, 237, 0.25), transparent 55%);
}
.testimonial__quote {
  font-size: 18px;
  line-height: 1.5;
  margin-bottom: var(--space-6);
}
.testimonial__avatar {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background: var(--gradient-brand);
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--color-white);
  font-weight: 700;
  font-size: 16px;
}
```

### Client Logos Policy (company-wide)

**Правило** (зафиксировано CEO Алексом на [LEA-406](/LEA/issues/LEA-406), 2026-04-18):

- **Не публикуем** конкретные логотипы клиентов без **письменного** согласия. Устное согласие не считается — требуется email, пункт в договоре или коммент в Paperclip от уполномоченного лица клиента.
- **Default — stub:** 6 monochrome плашек `slate-400`, generic rounded-rect силуэты, без узнаваемой геометрии (не имитировать реальный логотип даже намёком).
- **Лейбл секции по умолчанию:** «Доверяют команды 50+ компаний» — без имён, без отраслевых подписей, которые могут идентифицировать компанию под NDA.
- **Testimonial фото** — только реальные портреты выпускников (не AI-generated, не стоки). Список выпускников с письменным согласием курирует Марина (ContentManager).
- **Текст testimonial** — письменное согласие на цитирование + указание должности/компании отдельно (не автоматически из профиля).
- **Реальные логотипы** — включаются только с письменным согласием клиента. Сбор 5–7 компаний с разрешениями — отдельная задача CEO после запуска 28–29 апр.

**Rule:** stack order — logo wall → stats → testimonials. Если нет testimonials с согласием — stats card закрывают блок, testimonials пропускаем целиком (не stub).

---

## Accessibility & Cross-Browser

WCAG AA + прагматичный охват — браузеры, которые платят. Три блокирующие правки, остальное — hygiene.

### Gradient text (required Firefox-safe pattern)

Firefox игнорирует `-webkit-text-fill-color`. Без `color: transparent` в том же правиле — текст показывается дефолтным цветом поверх градиента. **Правильный паттерн — всегда дублировать `color: transparent` рядом с `-webkit-text-fill-color: transparent`**. Этого достаточно, Firefox-only хаки не нужны.

```css
/* Universal pattern — works in Chrome/Edge/Firefox/Safari без префиксных хаков */
.gradient-text,
.stat-value,
.countdown-value {
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  color: transparent; /* CRITICAL: Firefox reads this, webkit ignores */
}
```

**Не использовать `@-moz-document url-prefix()` как Firefox-only фильтр** — deprecated для content pages с Firefox 64+ (2018), работает только для user/XUL stylesheets.

**Опциональный solid fallback** для очень старых браузеров без `background-clip: text` support:

```css
@supports not (background-clip: text) {
  .gradient-text   { color: #2563EB; background: none; }
  .stat-value      { color: #2563EB; background: none; }
  .countdown-value { color: #7C3AED; background: none; }
}
```

**Поймано** на Design Review v2 Леной ([LEA-406](/LEA/issues/LEA-406), 2026-04-18). Всегда тестировать gradient-text в Firefox перед релизом.

### Backdrop-filter Safari prefix + fallback

Safari (включая мобильный) требует `-webkit-backdrop-filter` прямо перед стандартным `backdrop-filter`. Без префикса — серая однотонная заливка вместо glass-эффекта. Для браузеров без backdrop-filter (Firefox <103, старый UCBrowser, in-app webviews) — плотный `rgba` fallback через `@supports`.

```css
.glass {
  backdrop-filter: saturate(180%) blur(16px);
  -webkit-backdrop-filter: saturate(180%) blur(16px); /* Safari */
}

@supports not ((backdrop-filter: blur(1px)) or (-webkit-backdrop-filter: blur(1px))) {
  .glass,
  .glass-sm {
    background: rgba(15, 23, 42, 0.85); /* solid dark fallback */
    border-color: rgba(255, 255, 255, 0.12);
  }
}
```

### Conic-gradient fallback (featured card)

Conic-gradient поддерживается во всех современных браузерах (Chrome 69+, Firefox 83+, Safari 12.1+, 2019+). Для очень старых — отключить rotation и показать статичный gradient border.

```css
@supports not (background: conic-gradient(from 0deg, red, blue)) {
  .card-featured::before {
    background: var(--gradient-brand); /* static linear fallback */
    animation: none;
  }
}
```

### Focus-visible на интерактивных элементах

Клавиатурная навигация должна показывать focus ring. `outline: none` только парно с явным `:focus-visible`.

```css
.btn:focus-visible,
.input:focus-visible,
a:focus-visible {
  outline: 2px solid var(--color-cyan);
  outline-offset: 2px;
  border-radius: inherit;
}
```

### Contrast (WCAG AA)

- **Body text on white:** `--color-slate-600` `#475569` на `#FFFFFF` → contrast 7.6:1 ✓
- **Body text on dark:** `rgba(255,255,255,0.88)` на `#0F172A` → contrast 14.8:1 ✓
- **Glass card text:** минимум `rgba(255,255,255,0.85)` на backdrop — проверять целевой фон
- **Placeholder text:** `rgba(255,255,255,0.4)` на dark — только для form inputs, не для контента

### Reduced motion (required)

Все анимированные секции обязаны реагировать на `prefers-reduced-motion: reduce`. Снипет в Motion Design Tokens → Accessibility. Каждое новое `@keyframes` правило добавлять в `reduce` fallback при создании.

### Browser support matrix

| Feature | Chrome/Edge | Firefox | Safari 12.1+ | Legacy (IE / Safari <12) |
|---------|-------------|---------|--------------|--------------------------|
| gradient-text (`background-clip: text`) | ✓ | ✓ (требует `color: transparent`) | ✓ | fallback solid color via `@supports not` |
| backdrop-filter | ✓ (76+) | ✓ (103+) | ✓ (`-webkit-` required) | fallback `rgba(15,23,42,0.85)` via `@supports not` |
| conic-gradient | ✓ (69+) | ✓ (83+) | ✓ (12.1+) | static linear fallback via `@supports not` |
| IntersectionObserver | ✓ | ✓ | ✓ | JS fallback → показываем всё сразу (см. Motion Tokens) |
| `details`/`summary` | ✓ | ✓ | ✓ | ✓ |
| `@supports` feature queries | ✓ (28+) | ✓ (22+) | ✓ (9+) | IE не поддерживает → игнор fallback веток |

**Target baseline:** last 2 versions of Chrome/Edge/Firefox/Safari + Safari 15 (iOS 15.x ещё в парке). IE 11 официально не поддерживаем.

**Rule:** Не жертвовать accessibility ради визуала. Если эффект ломает navigation/contrast — выкидывать эффект, не доступность.

---

## Imagery

**AI image generation:** Primary tool — **nano-banana-pro-openrouter** (Gemini 3 Pro Image). Use for event covers, OG images, promo cards. For video — HeyGen avatars ( Артём).

| Type | Style |
|------|-------|
| People | Real business contexts, no staged smiles |
| Tech | Real interfaces, dashboards, screenshots |
| Abstract | Geometric patterns in brand colors, neural networks/graphs |
| Background | Dark navy or white with gradient accents |

**Mood:** confident · technical · spacious · modern · no-nonsense. Reference: Linear + Stripe aesthetic (not Notion/Apple).

**Whitespace rule:** Keep 40%+ empty space on promo cards and OG compositions for CTA pill / badge placement.

**Forbidden:**
- Stock photos with fake smiles
- Humanoid robots
- Acid colors outside the palette
- **Emoji in body text of landing pages** (OK in Telegram, not OK on landing)

---

## Assets & Distribution

### Vault paths (source of truth)

| Asset | Path |
|-------|------|
| **DESIGN.md** (this file) | `vault/company/brand/DESIGN.md` |
| **OG image standard** (Event Variant A) | `vault/projects/content-media/deliverables/intensive-landing/final/og-image.jpg` |
| **OG compose script** | `vault/projects/content-media/deliverables/intensive-landing/final/sources/og-image-v3-compose-all-variants.js` |
| **Pilot landing HTML** | `neuro-20-pilot/index.html` @ `vnagin/neuromasterclass-2-landing` |
| **Landing repo checkout** | see [reference_landing_repo](memory://reference_landing_repo) |
| **Tone of voice** | `vault/company/brand/tone-of-voice.md` |
| **References** (other companies' DESIGN.md) | `vault/company/brand/references/` |

### Distribution channels

| Channel | Target | Constraints |
|---------|--------|-------------|
| **Landing pages** | `ads.leadup.guru/<slug>/` | GitHub Pages, deploy via `git push main` (repo `vnagin/neuromasterclass-2-landing`) |
| **Telegram** «Нейросборка» | channel post | emoji allowed, OG image auto-rendered от meta tag |
| **Email / WhatsApp** | promo send | OG image must be **< 600 KB** (current standard 101 KB, 6× headroom) |
| **Internal (Paperclip)** | `vault/projects/<project>/deliverables/` | все файлы с frontmatter `status: approved` |

### AI image generation

| Tool | Use cases |
|------|-----------|
| **nano-banana-pro-openrouter** (Gemini 3 Pro Image) | Event covers, OG images, promo cards, mini-illustrations |
| **HeyGen avatars** | Видео-промо, talking head (Артём) |

Generation output: **2 files per prompt** (`*-1`, `*-2`) — это backup версии одного промпта, не A/B варианты. Для A/B — запускать 2 разных промпта ([reference_nano_banana_iterations](memory://reference_nano_banana_iterations)).

### LeadUp AI OG Image Standard (Event Variant A — confirmed 2026-04-18)

**Source:** `vault/projects/content-media/deliverables/intensive-landing/final/og-image.jpg`
**SHA-256:** `73085131926885d5f0463a66a56007baa316267b0fcc3dea5f5fa8330b6fde4f`

**File specs:** 1200×630px, JPEG quality 88, **101 732 bytes** (~100 KB, 6× headroom under WhatsApp 600 KB limit)

**CTA Pill (brand standard):**
```css
.og-cta-pill {
  position: absolute;
  right: 48px;
  bottom: 48px;
  padding: 18px 32px;
  background: linear-gradient(135deg, #2563EB 0%, #7C3AED 100%);
  border-radius: 14px;
  box-shadow: 0 10px 32px rgba(37, 99, 235, 0.55), 0 0 0 1px rgba(124, 58, 237, 0.4);
  font-family: 'Inter', sans-serif;
  font-size: 22px;
  font-weight: 700;
  color: #FFFFFF;
  letter-spacing: -0.01em;
  white-space: nowrap;
}
```

**CTA text:** `Зарегистрируйся бесплатно →` (single line, arrow inline, NO underline)
**Position:** right-bottom corner (right: 48px, bottom: 48px)
**Date badge:** separate left-bottom badge — NOT duplicated inside CTA pill

**A/B alternative (lower conversion):** Cyan pill `#00D9FF` with underline on "БЕСПЛАТНО". Use only if primary underperforms after first week of posting.

**Reference files:**
- Standard A: `vault/projects/content-media/deliverables/intensive-landing/final/og-image.jpg`
- Alt D (two-line, archive): `vault/projects/content-media/deliverables/intensive-landing/final/sources/og-v3-A-corner.jpg`
- Compose script: `vault/projects/content-media/deliverables/intensive-landing/final/sources/og-image-v3-compose-all-variants.js`

---

## Landing Page Checklist

Every landing page must have:

- [ ] Hero with gradient-text headline
- [ ] Primary CTA button (`.btn-gradient` or `.btn-primary`)
- [ ] Mobile-responsive layout
- [ ] OpenGraph meta tags (og:title, og:description, og:image)
- [ ] **OG image 1200×630 with brand CTA pill** (see OG Image Standard above)
- [ ] Schema.org markup (Event or Product depending on type)
- [ ] GA4 / Яндекс.Метрика tracking
- [ ] Form → n8n webhook integration (never hardcode lead logic)
- [ ] Loading speed < 3s (Core Web Vitals)

---

## Inspiration

See `references/` for 5 DESIGN.md files from:
1. Stripe — enterprise SaaS UI
2. Vercel — developer minimalism
3. Linear — dark modern aesthetic
4. Notion — friendly UX with character
5. Apple-inspired — premium, whitespace, typography

---

## Changelog

- **v1.1 — 2026-04-18** — Phase 2 pilot reference formalization. Six new sections + cross-browser corrections:
  1. `Animated Backgrounds` — aurora mesh + grain overlay (spec by Лена, implementation by Миша)
  2. `Premium Components` — radial glow, gradient border beam, glass card (spec by Лена, implementation by Миша)
  3. `Motion Design Tokens` — scroll-reveal + IO pattern + reduced-motion fallback (spec by Лена, implementation by Миша)
  4. `Social Proof Patterns` — logo wall, stat cards, dark testimonials + Client Logos Policy (Миша)
  5. `Accessibility & Cross-Browser` — Firefox gradient-text fix, Safari backdrop-filter, focus-visible, WCAG AA contrast, browser matrix (Миша, revised by Лена)
  6. `Assets & Distribution` — vault paths + distribution channels + AI image generation (Миша, extends existing OG spec)

  **Лена (review-pass 2026-04-18):** removed deprecated `@-moz-document url-prefix()` (doesn't apply to content pages since Firefox 64), added `@supports not` fallbacks for `background-clip: text` / `backdrop-filter` / `conic-gradient`, tightened browser matrix (Safari 12.1+, Firefox 103+ for backdrop-filter), closed 4 loopholes in Client Logos Policy (verbal consent doesn't count, no logo-hint even in silhouettes, no industry labels under stub, testimonial text requires written consent).

  Source: [LEA-411](/LEA/issues/LEA-411) pilot, commit `6813ccb`. Live reference: https://ads.leadup.guru/neuro-20-pilot/
  Approved by: Алекс (CEO) on [LEA-406](/LEA/issues/LEA-406), 2026-04-18.
- **v1.0 — 2026-04-18** — Initial DESIGN.md approved by Миша.

---

*Status: approved v1.1 | Owner: Миша (WebDeveloper) | Contributors: Лена (AI Designer) — spec for sections 1–3, review of 4–6 | Reviews: Лена done (2026-04-18), Алекс (CEO) approved (2026-04-18)*