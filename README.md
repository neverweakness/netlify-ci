# Assembly automation (netlify-ci)

Шаблон сборки статического фронтенда на Gulp: минификация HTML и CSS, автопрефиксы, склейка стилей в один файл, копирование изображений и живая перезагрузка в браузере.

## Что делает сборка

| Задача | Что происходит |
| --- | --- |
| `html` | Минификация HTML (`html-minifier`), вывод в `dist/` |
| `css` | Склейка всех `src/**/*.css` в `bundle.css`, PostCSS: `autoprefixer`, `postcss-combine-media-query`, `cssnano` |
| `images` | Копирование изображений (jpg, png, svg, gif, ico, webp, avif) |
| `clean` | Очистка `dist/` |
| `build` | Полная сборка: `clean` → `html` + `css` + `images` |
| `watchapp` (по умолчанию) | Сборка, слежение за файлами и BrowserSync |

Дополнительно настроены Stylelint и Prettier.

## Использование

```bash
git clone https://github.com/neverweakness/netlify-ci.git
cd netlify-ci
npm install
npx gulp build       # разовая сборка в dist/
npx gulp             # режим разработки: сервер и автоперезагрузка
```

Исходники кладутся в `src/` (`src/index.html`, `src/**/*.css`, `src/images/`).

## Стек

Gulp, PostCSS, autoprefixer, cssnano, html-minifier, BrowserSync, Stylelint, Prettier.

## Заметки

Сделано в декабре 2023 как основа для учебных вёрсток: сборка на базе `dist/` подходит для публикации на Netlify или GitHub Pages.
