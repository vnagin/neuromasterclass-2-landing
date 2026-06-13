# leadup-ads — Мультилендинговая структура

Репо обслуживает домен **ads.leadup.guru** через GitHub Pages.

## Структура

```
/                          → ads.leadup.guru/           (хаб-страница)
/neuromasterclass/         → ads.leadup.guru/neuromasterclass/
/[slug]/                   → ads.leadup.guru/[slug]/
/_template/                → шаблон нового лендинга (не публикуется пользователям)
```

## Как добавить новый лендинг

### 1. Создать папку для лендинга

```bash
cp -r _template/ название-slug/
```

Пример:
```bash
cp -r _template/ ai-copywriting/
```

### 2. Отредактировать `название-slug/index.html`

- Обновите `<title>` в `<head>`
- Замените заголовки, подзаголовки и тексты
- Добавьте нужные секции и стили

### 3. Добавить карточку на хаб-страницу

Откройте корневой `index.html`, найдите блок `<!-- Добавьте новый лендинг здесь -->` и добавьте карточку:

```html
<a href="/название-slug/" class="card">
  <div class="card-label">Тип продукта</div>
  <div class="card-title">Название продукта</div>
  <div class="card-desc">Краткое описание — 1–2 предложения.</div>
</a>
```

### 4. Закоммитить и запушить

```bash
git add .
git commit -m "Add landing: название-slug"
git push
```

GitHub Pages публикует автоматически через ~1 минуту.

## UTM-стандарт (обязательно для всех ad-лендингов)

Все формы на `ads.leadup.guru/*` обязаны пробрасывать **полный UTM-5tuple** из `window.location.search` в тело webhook-POST к n8n. Атрибуция и retention-кампании ломаются, если в `lead_magnet_downloads` / HubSpot прилетает только `utm_source`.

### Принятые параметры (snake_case, lower-case значения)

| Ключ | Обязательность | Назначение | Пример |
|------|----------------|------------|--------|
| `utm_source` | обязателен | Площадка/канал | `vk_ads`, `tg_neurosborka`, `email` |
| `utm_medium` | обязателен | Тип канала | `cpc`, `social`, `email`, `referral` |
| `utm_campaign` | обязателен | Кампания | `nmc2-launch-q3`, `lead-magnet-8-cases` |
| `utm_term` | опционально | Ключ/аудитория | `ceo-b2b`, `topic-llm` |
| `utm_content` | опционально | Креатив/вариант | `hero-cta`, `banner-vip-v2` |

Все колонки в `public.lead_magnet_downloads` — `text NULL`, схему менять не нужно (LEA-3117, Илья).

### Правила в коде лендинга

1. Имена ключей в URL и в payload — **строго snake_case**, точно как в таблице выше.
2. Отсутствующие параметры **не отправляем** (не шлите `''` или `null`) — пусть n8n кладёт NULL.
3. Каждый webhook-POST лендинга должен иметь рядом хелпер `getUtm()` и `Object.assign(payload, getUtm())`. Канонический пример:

```js
// UTM-5tuple passthrough → n8n (LEA-3117).
function getUtm() {
  var p = new URLSearchParams(window.location.search);
  var out = {};
  ['utm_source','utm_medium','utm_campaign','utm_term','utm_content'].forEach(function(k){
    var v = p.get(k); if (v) out[k] = v;
  });
  return out;
}

// в обработчике submit:
var payload = Object.assign({ email: email, source: 'mini-course' /* и т.п. */ }, getUtm());
```

4. **НЕ хардкодим** `utm_source` или `utm_campaign` в JS — все пять читаются ТОЛЬКО из URL.
5. Тестовая проверка перед мёрджем: открыть лендинг с `?utm_source=test&utm_medium=cpc&utm_campaign=qa-3117&utm_term=k1&utm_content=banner-a`, отправить форму → в Network → POST на n8n тело содержит все пять ключей.

### Соглашения по значениям

- `utm_source` — slug площадки в нижнем регистре (`vk_ads`, `yandex_direct`, `tg_aibusinesshub`).
- `utm_medium` — стандартный набор: `cpc` / `social` / `email` / `referral` / `organic` / `display`.
- `utm_campaign` — обычно `<продукт>-<повод>-<год-квартал>`, например `nmc2-launch-q3`.

## Домен и GitHub Pages

- Кастомный домен прописан в файле `CNAME` (`ads.leadup.guru`).
- В настройках репо: **Settings → Pages → Source: Deploy from branch → main / (root)**.
- HTTPS включается автоматически после DNS-проверки.

## Активные лендинги

| URL | Описание |
|-----|----------|
| [ads.leadup.guru](https://ads.leadup.guru/) | Хаб-страница |
| [ads.leadup.guru/neuromasterclass/](https://ads.leadup.guru/neuromasterclass/) | Нейромастерская 2.0 |
