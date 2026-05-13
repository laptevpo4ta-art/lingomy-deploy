# lingomy-landing

Лендинг для [Lingomy](https://t.me/lingomy_bot) — Telegram-бот для изучения английского.

Статический сайт без билда: чистый HTML + CSS в одном файле. Деплоится на GitHub Pages.

## Структура

- `index.html` — единственная страница (hero + features + steps + pricing + FAQ + footer)
- `CNAME` — кастомный домен `lingomy.com` для GitHub Pages
- `terms.html` / `privacy.html` / `refund.html` — _TODO: правовые документы (выложить из docs/ репозитория бота)_

## Локально посмотреть

Достаточно открыть `index.html` в браузере. Или поднять http-сервер:

```bash
python3 -m http.server 8000
# открой http://localhost:8000/
```

## Деплой (одноразово)

1. Создать репозиторий на GitHub: `laptevpo4ta-art/lingomy-landing` (или другой).
2. Запушить:
   ```bash
   git remote add origin git@github.com:laptevpo4ta-art/lingomy-landing.git
   git push -u origin main
   ```
3. В **Settings → Pages**:
   - Source: `Deploy from a branch`
   - Branch: `main`, folder: `/ (root)`
   - Save
4. Когда сайт развернётся (через 1-2 мин), в той же странице GitHub Pages укажет: «Custom domain: lingomy.com». Включить «Enforce HTTPS» — обычно подтягивается через ~10 минут после привязки.
5. У регистратора домена прописать DNS:
   - `A` записи на корень `lingomy.com`:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - `CNAME` `www.lingomy.com → laptevpo4ta-art.github.io`
6. Через 5-30 минут (зависит от TTL) — `https://lingomy.com/` должен открыть сайт.

## Дальнейшее

- Open Graph картинку (`og-image.png`, 1200×630) — добавить и прописать в `<meta property="og:image">`
- Robots.txt + sitemap.xml — для индексации в поисковиках
- Аналитика — Plausible / Umami / GA4 (по желанию)
- Reuse правовых документов из `docs/` бота — выгрузить как `terms.html`/`privacy.html`/`refund.html`
