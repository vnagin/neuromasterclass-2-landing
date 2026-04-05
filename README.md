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

## Домен и GitHub Pages

- Кастомный домен прописан в файле `CNAME` (`ads.leadup.guru`).
- В настройках репо: **Settings → Pages → Source: Deploy from branch → main / (root)**.
- HTTPS включается автоматически после DNS-проверки.

## Активные лендинги

| URL | Описание |
|-----|----------|
| [ads.leadup.guru](https://ads.leadup.guru/) | Хаб-страница |
| [ads.leadup.guru/neuromasterclass/](https://ads.leadup.guru/neuromasterclass/) | Нейромастерская 2.0 |
