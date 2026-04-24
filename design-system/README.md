# LeadUp AI — Design System v3

Единый источник правды по визуальной идентичности, бренду и UI-компонентам **LeadUp AI**. Используется и людьми, и AI-агентами при создании лендингов, соц-карточек, презентаций и внутренних интерфейсов.

> Полные исходные документы (brand book, DESIGN.md, tone of voice, references) лежат в `sources/` — это импорт из `vnagin/leadup-ai-design-system@main`.

---

## О компании

**LeadUp AI** — экосистема AI-трансформации бизнеса в русскоязычном пространстве.

**Миссия.** Помогать бизнесам становиться AI-first через практические инструменты автоматизации, образование и сообщество практиков.

**Бренд-архетип.** *Наставник + Новатор* — умный коллега, который уже прошёл путь и помогает другим пройти его быстрее.

### Продукты и каналы

| Продукт | Что это | Где живёт |
|---|---|---|
| **Нейромастерская 2.0** | Корпоративная образовательная программа по AI-трансформации | Лендинг: `ads.leadup.guru/<slug>/` |
| **Нейросборка** | Telegram-сообщество практиков AI-автоматизации | Telegram-канал `@neurosborka` + 1080×1080 карточки |
| **AI-автоматизация** | n8n-решения для B2B-клиентов | Сайты/презентации продаж |

### Аудитория

- **B2B:** компании 50–500 человек, внедряющие AI в процессы.
- **B2C:** специалисты и предприниматели, осваивающие AI-инструменты.

---

## Index — что лежит в корне

| Путь | Назначение |
|---|---|
| `README.md` | Этот файл — точка входа, foundations, правила. |
| `SKILL.md` | Entry-point для AI-агента (Claude Skills совместимо). |
| `colors_and_type.css` | CSS-токены v3 (Geist, teal, dark surfaces, spacing, radii, shadows, motion) + базовые стили. |
| `sources/` | Исходные MD-документы бренда: `DESIGN.md`, `brand-book.md`, `design-system.md`, `tone-of-voice.md`. |
| `assets/` | Логотип (`logo-leadup-raw.png`) и иконки. |
| `preview/` | HTML-карточки для Design System tab. |
| `ui_kits/` | Полностраничные UI-киты: `landing/`, `b2b-booking/`. |

---

## CONTENT FUNDAMENTALS — как мы пишем

Голос LeadUp AI — *умный коллега, который уже прошёл этот путь.* Не гуру, не блогер, не академик.

### Основные правила

- **Практично, без воды.** Если абзац можно заменить одной фразой — заменяем.
- **На «ты»** в B2C (Нейросборка, рассылки, соцсети). **На «вы»** в корпоративных B2B-презентациях и холодных продажах.
- **Уважительно, без снисхождения.** Клиент — умный, просто занят.
- **Современно, без жаргона ради жаргона.** Английские термины оставляем только если у них нет русского эквивалента («воркфлоу», «промпт» — да; «вельюпроп», «синергия» — нет).
- **Объясняем через примеры и цифры**, не через теорию.
- **Признаём ограничения AI.** Не обещаем волшебных результатов.

### Запрещённые слова

- «революционный», «прорывной», «уникальный» — если нет доказательств.
- «просто», «легко» — обесценивает усилия клиента.
- «AI заменит» — страх не конвертит, смысл конвертит.
- Buzzwords без объяснения («ML-driven», «disruption», «AI-powered» как самоцель).

### Примеры «до / после»

| ❌ Не так | ✅ Так |
|---|---|
| «Революционная AI-платформа, которая просто изменит ваш бизнес.» | «n8n-воркфлоу, который экономит 18 часов в неделю на отчётах. Работает с 2025-го у 12 команд.» |
| «AI заменит копирайтеров уже в этом году.» | «Копирайтер + GPT делает в 3 раза больше текстов. Замена не случится; перераспределение — уже идёт.» |
| «Получите уникальные инсайты!» | «Разбор 7 кейсов: где AI дал +15% к выручке, а где слил бюджет.» |

### Вайб и casing

- **Casing:** Sentence case в предложениях, **Title Case для англ. продуктовых имён** (`LeadUp AI`, `Нейромастерская 2.0`).
- **Никогда:** `leadup`, `LEADUP`, `Lead Up AI` (через пробел).
- **Emoji:** ✅ OK в Telegram/Нейросборке, ❌ **запрещено** на лендингах и в B2B-материалах.
- **Числа и метрики:** конкретно (`+18%`, `12 команд`, `47 минут`), не «значительно» и «существенно».
- **Тире — длинные** (—), кавычки — «ёлочки», цифры и меры неразрывно (`18 часов` с `&nbsp;`).

### Тон по каналам

| Канал | Тон |
|---|---|
| Telegram «Нейросборка» | Дружелюбный, живой, чуть неформальный. Emoji допустимы. |
| YouTube / Reels | Энергичный, структурированный, с «хуком» в первой фразе. |
| LinkedIn | Экспертный, деловой, с данными и ROI. |
| Email-рассылка | Личный, прямой, **один CTA** на письмо. |
| B2B-презентация | Профессиональный, на «вы», ориентированный на ROI и метрики. |
| Лендинг | Конвертирующий, на «ты», с социальным доказательством. |

---

## VISUAL FOUNDATIONS v3

### Direction

**D2 · Cold Technical.** Референсы — **Linear, Vercel Geist, Raycast**. Near-black поверхности, grid-pattern, монохром + один teal-accent. Жёстко, точно, плотные данные. Не HubSpot, не Anthropic, не Notion.

### Цветовая палитра

**Signature accent:** `#00E5C7` Electric Teal — CTA, links, accent, metric numbers.

| Token | Value | Использование |
|---|---|---|
| `--teal` | `#00E5C7` | CTA, links, accent |
| `--teal-hover` | `#14F5D7` | hover-state |
| `--teal-pressed` | `#00CBB0` | active/press |
| `--teal-tint` | `rgba(0,229,199,0.12)` | badge bg, icon-box |
| `--teal-glow` | `0 0 24px rgba(0,229,199,0.45)` | CTA hover glow |

**Dark surfaces (green-tinted, фирменная подпись):**

| Token | Value | Использование |
|---|---|---|
| `--bg-0` | `#050807` | deepest — body outer |
| `--bg-1` | `#0A0F0D` | default page |
| `--bg-2` | `#0F1512` | section, nav |
| `--bg-3` | `#141B18` | card surface |
| `--bg-4` | `#1B2420` | input, raised |
| `--bg-5` | `#253029` | hover, divider-fill |

**Foreground (on dark):**

| Token | Value | Использование |
|---|---|---|
| `--fg-1` | `#EDEFEE` | h1, h2, key data |
| `--fg-2` | `rgba(237,239,238,0.72)` | body text |
| `--fg-3` | `rgba(237,239,238,0.52)` | captions, meta |
| `--fg-4` | `rgba(237,239,238,0.36)` | disabled |

**Light surfaces:** `--bg-light-1` `#FAFBFA` / `--bg-light-2` `#F2F4F3` / `--bg-light-3` `#E6EAE8`.

**Borders:** `--border-1` (0.06 opacity, subtle) / `--border-2` (0.10, default) / `--border-3` (0.18, hover/focus).

**Semantic:** `--success` `#3EE089` / `--warning` `#F5B544` / `--danger` `#FF5D5D` / `--info` `#6EB8FF` — каждый с `-tint` вариантом.

**Правила:**
- Teal **никогда** как залитая поверхность — только текст, 1px border, glow.
- Максимум 1 teal-accent area above the fold.
- Градиенты — только `--grad-glow` (radial teal haze сверху) и `--grad-teal-line` (горизонтальная линия). Не как фоны секций.
- Gradient-text (`.text-teal-grad`) — максимум 1 на экран.

### Типографика (TS1 · Geist)

| Уровень | Size / lh / tracking | Weight |
|---|---|---|
| display-2 | 120px / 0.98 / -0.045em | 700 |
| display-1 | 84px / 0.98 / -0.045em | 700 |
| H1 | 60px / 1.04 / -0.035em | 700 |
| H2 | 44px / 1.04 / -0.035em | 700 |
| H3 | 32px / 1.2 / -0.02em | 600 |
| H4 | 24px / 1.2 / -0.02em | 600 |
| H5 | 20px / 1.3 / -0.02em | 600 |
| H6 | 17px / 1.35 / -0.01em | 600 |
| lead | 17px / 1.55 / -0.01em | 400 |
| body | 15px / 1.5 | 400 |
| small | 13px / 1.5 | 400–500 |
| caption/eyebrow | 11px / 1.2 / 0.08em uppercase | 500, Geist Mono |

**Шрифты:**
- `--font-sans`: `'Geist', -apple-system, BlinkMacSystemFont, 'Inter', 'Segoe UI', sans-serif`
- `--font-mono`: `'Geist Mono', 'JetBrains Mono', ui-monospace, monospace`
- Загрузка: Google Fonts CDN, `font-feature-settings: 'ss01', 'cv11'`.

**Правила:**
- Агрессивно-отрицательный tracking у display/H1/H2 — подпись tech-брендов.
- Eyebrow всегда mono, uppercase, 11px, tracking 0.08em.
- Числовые данные — `font-variant-numeric: tabular-nums`.
- Mono используется для: eyebrow, kbd, code, table data, meta, timestamps.

### Фоны

- **Grid-pattern** — фирменная подпись: `48px` линии `rgba(255,255,255,0.035)`, маскируется через radial-gradient для hero.
- **Teal glow** — `radial-gradient` с `rgba(0,229,199,0.16)` сверху hero. Только 1 на страницу.
- **Teal line** — горизонтальный `linear-gradient(90deg, transparent, teal 0.4, transparent)` как акцентный разделитель.
- **Полно-bleed фотографий — нет.** Фоны геометричные, grid-based.

### Анимация

| Что | Duration | Easing |
|---|---|---|
| Hover, micro | `120ms` | `cubic-bezier(0.2, 0, 0, 1)` |
| Default (tab, button) | `200ms` | `cubic-bezier(0.2, 0, 0, 1)` |
| Reveal, scroll-in | `320ms` | `cubic-bezier(0.2, 0, 0, 1)` |
| Complex (modal, page) | `500ms` | `cubic-bezier(0.16, 1, 0.3, 1)` |

**Правила:**
- **Никаких bounce, elastic, spring, overshoot.**
- Buttons hover: `translateY(-1px)` + `--teal-glow`.
- Cards hover: `border-color` transition, **no translateY**.
- Scroll-reveal: `opacity 0→1 + translateY(12px→0)`, stagger 40ms.
- `prefers-reduced-motion: reduce` — отключает всё.

### Hover / Active состояния

| Элемент | Hover | Active |
|---|---|---|
| `.btn-primary` | `--teal-hover` + glow + `translateY(-1px)` | `--teal-pressed` + `translateY(0)` + no glow |
| `.btn-default` | `bg-5` + `border-3` | `bg-4` + `scale(0.98)` |
| `.btn-ghost` | `bg-4` + `fg-1` | `bg-5` |
| `.btn-danger` | darker danger-tint | `scale(0.98)` |
| `.card` | `border-3` + `bg-4` | — |

### Borders

- `1px solid var(--border-2)` — default для карточек, инпутов.
- `1px solid var(--teal)` — selected / featured card.
- Top-glow line (`--grad-teal-line`) — на hero-ui панели, featured cards.

### Shadows

| Token | Value | Использование |
|---|---|---|
| `--shadow-1` | inset highlight + 2px drop | inputs, kbd |
| `--shadow-2` | 8px drop + 1px ring | card rest |
| `--shadow-3` | 32px drop + 1px ring | hover, popover |
| `--shadow-4` | 64px drop + 1px ring | modals |
| `--shadow-teal` | 1px teal ring + 24px teal glow | CTA hover, selected |

### Corner radii

| Token | Value | Использование |
|---|---|---|
| `--r-sm` | 4px | kbd, code inline |
| `--r-md` | 6px | small buttons, badges |
| `--r-lg` | 8px | **buttons, inputs — default** |
| `--r-xl` | 10px | cards |
| `--r-2xl` | 14px | hero blocks, feature cards |
| `--r-3xl` | 20px | panels, large surfaces |
| `--r-full` | 9999px | pills, avatars |

### Layout

- **Container:** `max-width: 1240px`, `padding: 0 24px`.
- **Narrow container:** `max-width: 980px`.
- **Grid gap:** `24px`.
- **Section padding:** `96px 0` desktop, `64px 0` mobile.
- **Breakpoints:** 480 / 768 / 1024 / 1280.

---

## ICONOGRAPHY

### Lucide Icons — основная библиотека

Outline stroke, **не filled**. Размеры: 16/20/24/32, кратны 4. Цвет — `currentColor`. Акцентные — `--teal`.

### Icon-in-a-box

`36×36`, `border-radius: --r-md`, `background: --teal-tint`, `border: 1px solid rgba(0,229,199,0.2)`, иконка `--teal`.

### Logo

- Единственный файл: `assets/logo-leadup-raw.png` (белый на прозрачном).
- На тёмном фоне: `filter: brightness(10)` для белого.
- На светлом фоне: `filter: brightness(0)` для чёрного.
- На teal-фоне: `filter: brightness(0)` для чёрного.
- Формы написания: `LeadUp AI` (основное), `LeadUp` (короткое).
- **Никогда:** `leadup`, `LEADUP`, `Lead Up AI`.
- Минимальный отступ: `16px`.

### Emoji / Unicode

- **Emoji** — ✅ в Telegram, ❌ на лендингах и в B2B.
- **Unicode** — стрелки (`→`, `↗`) в кнопках, точки (`·`, `•`) как разделители.

---

## UI Kits

| Kit | Путь | Описание |
|---|---|---|
| **Landing** | `ui_kits/landing/` | Нейромастерская 2.0 — hero, features, program timeline, pricing, testimonial, CTA, footer. |
| **B2B Booking** | `ui_kits/b2b-booking/` | Lead capture: program card, calendar, form, sidebar. |

---

## Quick reference (CSS variables — hot path)

```css
--teal:            #00E5C7;    /* CTA, links, accent */
--teal-hover:      #14F5D7;
--teal-tint:       rgba(0,229,199,0.12);

--bg-1:            #0A0F0D;    /* default page */
--bg-2:            #0F1512;    /* section */
--bg-3:            #141B18;    /* card */
--bg-4:            #1B2420;    /* input */

--fg-1:            #EDEFEE;    /* primary text */
--fg-2:            rgba(237,239,238,0.72);  /* body */
--fg-3:            rgba(237,239,238,0.52);  /* muted */

--border-2:        rgba(255,255,255,0.10);  /* default border */

--font-sans:       'Geist', sans-serif;
--font-mono:       'Geist Mono', monospace;

--r-lg:            8px;     /* default button/input */
--r-xl:            10px;    /* cards */

--ease:            cubic-bezier(0.2, 0, 0, 1);
--dur-2:           200ms;   /* default transition */
```

---

*LeadUp AI © 2026. Design System v3 · D2 Cold Technical · C3 Electric Teal · TS1 Geist.*
