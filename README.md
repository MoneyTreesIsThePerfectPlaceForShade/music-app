# Music App Doc

В этом документе я описываю _весь_ процесс разработки музыкального приложения.

# Шаг 1

## Инициализация и начальная настройка

С помощью команды _npm init vue@latest_ начинаю конфигурацию и создание приложения на Vue. Я выбрал следующие настройки: Vue Router, Pinia, Vitest, Cypress, ESLint, Prettier.
Далее перешел в директорию проекта и установил зависимости _npm install_.

Зайдя в настройки VS Code, открываем их как JSON файл. Для того, чтобы ESLint работал при сохранении проекта, нужно прописать следующее:

```js
"editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
```

Далее установил tailwind, используя команду `npm install -D tailwindcss postcss autoprefixer`. После ввёл команду `npx tailwindcss init -p`. Эта команда сгенерировала файлы конфигурации для tailwind и postcss. Открыв файл конфигурации tailwind, я ввёл в контент то, что рекомендовалось на сайте: `"./index.html", "./src/**/*.{js,ts,jsx,tsx}",`.

Чтобы ESLint не ругался на module.exports, нужно в файле конфигурации ESLint добавить объект env с такими свойствами:

```js
env: {
    node: true,
  },
```

В src/assets/base.css удаляем весь код и пишем это:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Чтобы VS Code не ругался на `@tailwind` заходим в JSON версию настроек и прописываем это:

```js
"files.associations": {
        "*.css": "tailwindcss"
    }
```

Удалил из `src/assets/` файл `main.css`. Это потребовалось только потому, что на курсе был заготовлен отдельный `main.css`.
В `main.js` изменяем импорт css с `main.css` на `base.css`.
В `main.js` добавляем импорт css с `main.css`.
