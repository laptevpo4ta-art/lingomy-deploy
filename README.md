# lingomy-landing

Лендинг для [Lingomy](https://t.me/LingomyBot) — **Telegram Mini App** для изучения английского с русского. Дерево уроков, стрики, сердечки, недельные лиги, AI-чат на Premium.

Статический сайт без билда: чистый HTML + CSS в одном файле (~22 KB). Деплоится на GitHub Pages, домен `lingomy.com`.

## Позиционирование (короткой строкой)

Mini App в Telegram — как Duolingo, только проще: открывается прямо в чате, без отдельного приложения, объяснения на русском, оплата в Stars / картой / USDT.

## Структура

- `index.html` — единственная страница (hero + how-it-works + features + pricing + FAQ + final CTA + footer)
- `CNAME` — кастомный домен `lingomy.com` для GitHub Pages
- `terms.html` / `privacy.html` / `refund.html` — _TODO: правовые документы (выложить из docs/ репозитория бота)_

Все CTA ведут на `https://t.me/LingomyBot?startapp=landing` — deep-link с attribution-payload `landing`. Бот по этому payload помечает источник пользователя.

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
