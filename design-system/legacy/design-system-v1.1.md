---
title: "Design System LeadUp AI (v1.0, DEPRECATED)"
project: company
type: brand
status: deprecated
version: "1.0"
supersededBy: "/vault/company/brand/README.md + colors_and_type.css (Design System v3)"
deprecatedOn: "2026-04-24"
deprecatedBy: "Лена (AI Designer) — LEA-476"
owner: "Лена (AI Designer)"
created: "2026-04-08"
updated: "2026-04-24"
tags: [design, system, components, css, spacing, grid, deprecated, v1.0]
---

> ⚠️ **DEPRECATED · 2026-04-24.** Этот документ — v1.0 (Inter + blue `#2563EB` + slate). Заменён **Design System v3** (Geist + teal `#00E5C7` + green-tinted near-black). Используй [`../README.md`](../README.md) + [`../colors_and_type.css`](../colors_and_type.css) как canonical для новых работ.
>
> **Не использовать для новых лендингов/карточек.** Миграция существующих артефактов трекается в LEA-477.

---

# Design System LeadUp AI (v1.0, archived)

> Система дизайна для всех цифровых продуктов LeadUp AI: лендинги, соцсети, презентации.
> Основан на [Brand Book](../brand-book.md). Статус: **archived** — был approved Леной (AI Designer) 2026-04-08, superseded v3 2026-04-24.

---

## 1. Основы

### 1.1 Базовая единица

Базовая единица отступов: **4px (0.25rem)**.
Все отступы, размеры и сетки кратны 4.

### 1.2 Цветовые токены (CSS Variables)

```css
:root {
  /* Основные цвета */
  --color-primary: #2563EB;
  --color-primary-hover: #1D4ED8;
  --color-primary-light: #DBEAFE;

  --color-dark: #0F172A;
  --color-dark-secondary: #1E293B;

  --color-white: #FFFFFF;

  /* Акцентные */
  --color-cyan: #06B6D4;
  --color-cyan-hover: #0891B2;
  --color-violet: #7C3AED;
  --color-violet-hover: #6D28D9;
  --color-emerald: #10B981;
  --color-amber: #F59E0B;

  /* Нейтральные (Slate) */
  --color-slate-50: #F8FAFC;
  --color-slate-200: #E2E8F0;
  --color-slate-400: #94A3B8;
  --color-slate-600: #475569;
  --color-slate-800: #1E293B;

  /* Градиенты */
  --gradient-brand: linear-gradient(135deg, #2563EB 0%, #7C3AED 100%);
  --gradient-dark: linear-gradient(180deg, #0F172A 0%, #1E293B 100%);
  --gradient-accent: linear-gradient(90deg, #06B6D4 0%, #2563EB 100%);
}
```

---

## 2. Типографика

### 2.1 Подключение шрифтов

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

### 2.2 Токены типографики

```css
:root {
  /* Семейства */
  --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  --font-mono: 'JetBrains Mono', 'Fira Code', monospace;

  /* Размеры */
  --text-xs: 0.75rem;    /* 12px */
  --text-sm: 0.875rem;   /* 14px */
  --text-base: 1rem;     /* 16px */
  --text-lg: 1.125rem;   /* 18px */
  --text-xl: 1.25rem;    /* 20px */
  --text-2xl: 1.5rem;    /* 24px */
  --text-3xl: 2rem;      /* 32px */
  --text-4xl: 2.5rem;    /* 40px */
  --text-5xl: 3.5rem;    /* 56px */

  /* Веса */
  --font-regular: 400;
  --font-medium: 500;
  --font-semibold: 600;
  --font-bold: 700;
  --font-extrabold: 800;

  /* Line-heights */
  --leading-tight: 1.1;
  --leading-snug: 1.3;
  --leading-normal: 1.5;
  --leading-relaxed: 1.6;
}
```

### 2.3 Стили заголовков

```css
h1 {
  font-family: var(--font-sans);
  font-size: var(--text-5xl);
  font-weight: var(--font-extrabold);
  line-height: var(--leading-tight);
  color: var(--color-dark);
}

h2 {
  font-size: var(--text-4xl);
  font-weight: var(--font-bold);
  line-height: 1.2;
}

h3 {
  font-size: var(--text-3xl);
  font-weight: var(--font-bold);
  line-height: var(--leading-snug);
}

h4 {
  font-size: var(--text-2xl);
  font-weight: var(--font-semibold);
  line-height: 1.4;
}

/* Градиентный текст (для hero-заголовков) */
.gradient-text {
  background: var(--gradient-brand);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```

---

## 3. Сетка и отступы

### 3.1 Spacing Scale

```css
:root {
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;
  --space-20: 80px;
  --space-24: 96px;
  --space-32: 128px;
}
```

### 3.2 Контейнер

```css
.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-6);
}

@media (max-width: 768px) {
  .container {
    padding: 0 var(--space-4);
  }
}
```

### 3.3 Сетка (Grid)

```css
/* 12-колоночная сетка */
.grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--space-6);
}

/* Типовые колонки */
.col-4 { grid-column: span 4; }  /* треть */
.col-6 { grid-column: span 6; }  /* половина */
.col-8 { grid-column: span 8; }  /* 2/3 */
.col-12 { grid-column: span 12; } /* полная ширина */

@media (max-width: 768px) {
  .col-4, .col-6, .col-8 {
    grid-column: span 12;
  }
}
```

---

## 4. Компоненты

### 4.1 Кнопки

```css
/* Базовые стили кнопки */
.btn {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2);
  padding: var(--space-3) var(--space-6);
  border-radius: 8px;
  font-family: var(--font-sans);
  font-size: var(--text-base);
  font-weight: var(--font-semibold);
  cursor: pointer;
  transition: all 0.2s ease;
  border: 2px solid transparent;
  text-decoration: none;
}

/* Primary */
.btn-primary {
  background: var(--color-primary);
  color: var(--color-white);
  border-color: var(--color-primary);
}
.btn-primary:hover {
  background: var(--color-primary-hover);
  border-color: var(--color-primary-hover);
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(37, 99, 235, 0.3);
}

/* Secondary (Outline) */
.btn-secondary {
  background: transparent;
  color: var(--color-primary);
  border-color: var(--color-primary);
}
.btn-secondary:hover {
  background: var(--color-primary-light);
}

/* Ghost (тёмный фон) */
.btn-ghost {
  background: rgba(255, 255, 255, 0.1);
  color: var(--color-white);
  border-color: rgba(255, 255, 255, 0.2);
}
.btn-ghost:hover {
  background: rgba(255, 255, 255, 0.2);
}

/* Gradient CTA */
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

/* Размеры */
.btn-sm { padding: var(--space-2) var(--space-4); font-size: var(--text-sm); }
.btn-lg { padding: var(--space-4) var(--space-8); font-size: var(--text-lg); border-radius: 10px; }
```

### 4.2 Карточки

```css
/* Базовая карточка */
.card {
  background: var(--color-white);
  border: 1px solid var(--color-slate-200);
  border-radius: 12px;
  padding: var(--space-6);
  transition: all 0.2s ease;
}
.card:hover {
  border-color: var(--color-primary);
  box-shadow: 0 4px 24px rgba(37, 99, 235, 0.08);
  transform: translateY(-2px);
}

/* Тёмная карточка */
.card-dark {
  background: var(--color-dark-secondary);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 12px;
  padding: var(--space-6);
  color: var(--color-white);
}

/* Карточка с градиентной рамкой */
.card-gradient {
  position: relative;
  background: var(--color-white);
  border-radius: 12px;
  padding: var(--space-6);
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

### 4.3 Бейджи / Теги

```css
.badge {
  display: inline-flex;
  align-items: center;
  gap: var(--space-1);
  padding: var(--space-1) var(--space-3);
  border-radius: 100px;
  font-size: var(--text-sm);
  font-weight: var(--font-medium);
}

.badge-primary {
  background: var(--color-primary-light);
  color: var(--color-primary);
}

.badge-violet {
  background: #EDE9FE;
  color: var(--color-violet);
}

.badge-emerald {
  background: #D1FAE5;
  color: var(--color-emerald);
}

.badge-amber {
  background: #FEF3C7;
  color: var(--color-amber);
}
```

### 4.4 Секции страницы

```css
/* Базовая секция */
.section {
  padding: var(--space-24) 0;
}

.section-sm {
  padding: var(--space-16) 0;
}

/* Hero-секция */
.hero {
  background: var(--gradient-dark);
  color: var(--color-white);
  padding: var(--space-32) 0;
  text-align: center;
}

/* Альтернативный фон секции */
.section-alt {
  background: var(--color-slate-50);
}
```

### 4.5 Инпуты и формы

```css
.input {
  width: 100%;
  padding: var(--space-3) var(--space-4);
  background: var(--color-white);
  border: 1px solid var(--color-slate-200);
  border-radius: 8px;
  font-family: var(--font-sans);
  font-size: var(--text-base);
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

---

## 5. Иконки и иллюстрации

### 5.1 Lucide Icons

```html
<!-- Подключение -->
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>

<!-- Использование -->
<i data-lucide="zap" class="icon-sm"></i>
<i data-lucide="brain" class="icon-md"></i>
<i data-lucide="trending-up" class="icon-lg"></i>
```

```css
.icon-sm { width: 16px; height: 16px; }
.icon-md { width: 20px; height: 20px; }
.icon-lg { width: 24px; height: 24px; }
.icon-xl { width: 32px; height: 32px; }

/* Иконка в круге (feature-card) */
.icon-box {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 48px;
  height: 48px;
  border-radius: 12px;
  background: var(--color-primary-light);
  color: var(--color-primary);
}
```

---

## 6. Тени

```css
:root {
  --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.08);
  --shadow-md: 0 4px 12px rgba(0, 0, 0, 0.08);
  --shadow-lg: 0 8px 24px rgba(0, 0, 0, 0.1);
  --shadow-xl: 0 16px 48px rgba(0, 0, 0, 0.12);
  --shadow-brand: 0 8px 24px rgba(37, 99, 235, 0.3);
}
```

---

## 7. Border Radius

```css
:root {
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-2xl: 24px;
  --radius-full: 9999px;
}
```

---

## 8. Breakpoints

```css
/* Mobile first */
/* xs: < 480px */
/* sm: 480px */
@media (min-width: 480px) { ... }
/* md: 768px */
@media (min-width: 768px) { ... }
/* lg: 1024px */
@media (min-width: 1024px) { ... }
/* xl: 1280px */
@media (min-width: 1280px) { ... }
/* 2xl: 1536px */
@media (min-width: 1536px) { ... }
```

---

## 9. Telegram-карточки (1080×1080)

### 9.1 Общая структура

```
┌─────────────────────────┐
│  [Logo / Badge]  16px   │  ← padding 48px со всех сторон
│                         │
│  ЗАГОЛОВОК              │  ← Inter 700, 56–64px
│  (2–3 строки макс)      │
│                         │
│  Текст/цифра/факт       │  ← Inter 400, 28–32px
│                         │
│  ─────────────────      │  ← разделитель
│  @neurosborka           │  ← caption, 24px
└─────────────────────────┘

Фоны:
- Тёмный: #0F172A → #1E293B
- Акцент: gradient-brand
- Нейтральный: #F8FAFC (для цитат)

Акцентный элемент: цветной блок/полоса сверху или слева (8px)
```

### 9.2 Вариант A — Тёмный (основной)

**Назначение:** Инсайты, факты, советы по AI-автоматизации

**Параметры:**
- Фон: `linear-gradient(180deg, #0F172A 0%, #1E293B 100%)`
- Акцентная полоса сверху: 8px, цвет `#2563EB`
- Заголовок: Inter 700, 56px, цвет `#FFFFFF`
- Подтекст: Inter 400, 28px, цвет `#94A3B8`
- Caption: Inter 500, 24px, цвет `#475569`
- Бейдж-тег: `.badge-primary` (синий), позиция — левый верх после отступа

**Midjourney prompt:**
```
dark navy background 1080x1080 telegram card, gradient from #0F172A to #1E293B, minimalist UI design, blue accent stripe 8px at top #2563EB, large white Inter bold headline text placeholder, small muted subtitle text, @neurosborka caption bottom, clean modern tech aesthetic, LeadUp AI brand --ar 1:1 --style raw --v 6
```

**DALL-E 3 prompt:**
```
A minimalist 1080x1080 social media card with dark navy gradient background (#0F172A to #1E293B), a thin 8px blue accent line (#2563EB) at the top, bold white headline text area in the center, small grey subtitle below, and a subtle @neurosborka caption at the bottom. Clean, modern, tech brand aesthetic. No people, no decorative elements except a small geometric glow near headline.
```

---

### 9.3 Вариант B — Акцентный (градиент бренда)

**Назначение:** Анонсы, важные новости, запуск продуктов

**Параметры:**
- Фон: `linear-gradient(135deg, #2563EB 0%, #7C3AED 100%)`
- Заголовок: Inter 800, 60px, цвет `#FFFFFF`
- Подтекст: Inter 500, 28px, цвет `rgba(255,255,255,0.85)`
- Caption: Inter 500, 24px, цвет `rgba(255,255,255,0.6)`
- Декор: крупный прозрачный геометрический элемент (окружность/сетка) в правом нижнем углу, opacity 0.1

**Midjourney prompt:**
```
vibrant blue to purple gradient 1080x1080 telegram card #2563EB to #7C3AED, minimalist announcement design, white extrabold headline, subtle geometric circle wireframe decoration bottom-right corner opacity 10%, clean sans-serif typography, modern tech brand aesthetic, LeadUp AI --ar 1:1 --style raw --v 6
```

**DALL-E 3 prompt:**
```
A bold 1080x1080 social media card with a vibrant diagonal gradient from electric blue (#2563EB) to violet (#7C3AED), large white extra-bold announcement headline in the center-left, smaller white subtitle text below, subtle transparent geometric circle pattern in the bottom-right corner (10% opacity), @neurosborka caption bottom-left. No people or photos. Premium, modern tech aesthetic.
```

---

### 9.4 Вариант C — Нейтральный (светлый, для цитат)

**Назначение:** Цитаты, отзывы, обучающие факты

**Параметры:**
- Фон: `#F8FAFC`
- Левая акцентная полоса: 6px, цвет `#2563EB`
- Заголовок: Inter 700, 48px, цвет `#0F172A`
- Цитата/текст: Inter 400 italic, 28px, цвет `#475569`
- Caption: Inter 500, 22px, цвет `#94A3B8`
- Рамка: 1px `#E2E8F0`

**Midjourney prompt:**
```
light grey background #F8FAFC 1080x1080 telegram card, blue left accent border stripe 6px #2563EB, dark navy bold headline text, italic grey quote text, minimal clean layout, white card with subtle border, modern editorial style, @neurosborka caption --ar 1:1 --style raw --v 6
```

**DALL-E 3 prompt:**
```
A clean minimal 1080x1080 social media card with light grey background (#F8FAFC), a thin blue vertical accent stripe (6px, #2563EB) on the left edge, dark navy large bold headline text, italic medium-grey quote or body text below, subtle 1px light border around the card, @neurosborka caption bottom-right in muted grey. Elegant, editorial, minimalist design.
```

---

## 10. Статус и версионирование

| Версия | Дата | Изменения |
|--------|------|-----------|
| 0.1 | 2026-04-08 | Первичный драфт на основе brand book |
| 1.0 | 2026-04-08 | Проверка и утверждение: цвета, типографика, компоненты. Добавлены 3 типовых варианта Telegram-карточек с промптами. Статус → approved |

**Выполнено Леной (AI Designer) 2026-04-08:**
- [x] Проверить и уточнить цветовую палитру — соответствует Brand Book ✓
- [x] Проверить типографику — соответствует Brand Book ✓
- [x] Убедиться в корректности компонентов (кнопки, карточки, бейджи) — ✓
- [x] Разработать типовой набор Telegram-карточек — 3 варианта с Midjourney и DALL-E 3 промптами ✓
- [x] Утвердить и изменить статус на `approved` ✓

---

## Связанные документы

- [Brand Book](./brand-book.md) — идентичность и голос бренда
- [Голос и тон](./tone-of-voice.md) — правила коммуникации

---

*Последнее обновление: 2026-04-08 | Версия: 1.0 | Владелец: Лена (AI Designer) | Статус: approved*
