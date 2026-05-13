# CLAUDE.md — лендинг lingomy.com

Это **публичный статический сайт** для GitHub Pages → lingomy.com.
Single-page, без сборки, без зависимостей.

## Стек
- Чистый HTML/CSS/JS (можно Tailwind через CDN).
- GitHub Pages из ветки `main`, домен — через `CNAME` (уже настроен на `lingomy.com`).
- `index.html` — главная (и единственная) страница.

## Что продаём
**Lingomy** — Duolingo-подобное приложение для изучения английского, живёт как
Telegram Mini App. Фичи:
- Дерево уроков (vocab / translate / listen / multiple choice / match).
- XP, стрики, сердечки.
- Недельные лиги — соревнование с 29 другими в твоей лиге.
- Друзья — приглашение через Telegram, общий лидерборд.
- Freemium: free тариф с лимитами, Premium = unlimited.

## Правила
- **Один файл** `index.html` — никаких bundler-ов, npm-ов. Меньше зависимостей =
  меньше боли с деплоем на Pages.
- Tailwind — только через CDN (`https://cdn.tailwindcss.com`).
- Анимации — vanilla CSS + минимум JS (vanilla, без React).
- Все CTA ведут на `https://t.me/<bot_username>?startapp=landing` (deep-link
  с attribution).
- Минимум JS-аналитики (можно Plausible через тег, без cookie-баннера тогда).
- Responsive с mobile-first (большинство юзеров кликнут с мобилы).
- Тон копирайтинга — русский, простой, без рекламной пены. Прямо что даём и кому.
- `CNAME` НЕ удалять — иначе слетит кастомный домен.

## Структура контента (предложение)
1. Hero — название, оффер в одну строку, скриншот мини-аппа, CTA.
2. Как работает — 3 шага (открой бот → пройди тест уровня → учись каждый день).
3. Фичи — лиги / стрики / SRS / AI-объяснения / TTS.
4. Тарифы — Free / Premium (месяц / год / lifetime), цены из основного `english-bot`.
5. FAQ — 5–7 пунктов (зачем Telegram, чем отличается от Duolingo, можно ли с десктопа, и т.п.).
6. Футер — связь, политика, копирайт.

## Деплой
- `git push origin main` → GitHub Pages автоматом пересобирает.
- Если что-то сломалось — `gh-pages` action логи.

## Команды
```bash
# Локальный preview
python3 -m http.server 8000
# или VS Code Live Server (открой index.html, ПКМ → Open with Live Server)
```
