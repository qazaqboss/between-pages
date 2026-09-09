# Between Pages

Сайт-визитка бренда дизайнерских закладок для книг (Актобе, Казахстан).

**Live:** https://qazaqboss.github.io/between-pages/

Одностраничник без сборки: `index.html` + иллюстрации в `assets/`. Открывается двойным кликом,
деплой — обычный статический хостинг или GitHub Pages.

## Структура страницы

| Секция | Что внутри |
|---|---|
| Hero | Логотип, слоган «Между страницами живёшь ты», веер из четырёх закладок |
| Коллекции | 5 коллекций; клик фильтрует каталог |
| Каталог | 8 закладок, карточки в форме закладки с вырезом |
| Наборы | 4 готовых набора + «Собери свой» |
| Афиша | Ближайшие встречи, маркеты и воркшопы |
| О бренде | Текст бренда и спецификация продукта |
| Как заказать | 3 шага, оплата Kaspi, доставка |
| Отзывы, контакты | WhatsApp / Telegram / Instagram, блок для опта |

## Что заменить на реальные данные

- Телефон и ники в секции «Контакты» (сейчас `+7 700 000 00 00`, `@betweenpages`).
- Цены в каталоге и наборах.
- **События в афише — примеры структуры.** Даты, адреса и число мест нужно заменить своими.

## Стиль

Кремовый пергамент `#FBF7EA`, шоколадный `#4A2C1A`, акценты по коллекциям
(красный `#D42A1F`, матча `#7A9A4B`, терракота `#D8623A`, золото `#C9A961`, розовый `#E77FA6`).
Шрифты: Cormorant Garamond, Manrope, Caveat, Bebas Neue (Google Fonts).

## Превью ссылки (Open Graph)

При пересылке ссылки в WhatsApp, Telegram и соцсети показывается баннер
`assets/og-cover.jpg` (1200 × 630, 128 КБ), заголовок и описание из `<meta>` в `index.html`.

Исходник баннера — `assets/og-cover-source.html`. Перерисовать после правок:

```sh
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --disable-gpu \
  --force-device-scale-factor=2 --window-size=1200,630 --virtual-time-budget=8000 \
  --screenshot=og2x.png assets/og-cover-source.html
sips -z 630 1200 og2x.png && sips -s format jpeg -s formatOptions 82 og2x.png --out assets/og-cover.jpg
```

Кэш превью: после замены картинки WhatsApp и Telegram какое-то время отдают старую.
Сбросить — Facebook Sharing Debugger, а в Telegram написать боту @WebpageBot.
