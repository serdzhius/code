# Чертоги Фрилансера v3

- [Ссылка на страницу с которой можно скачать gulp сборку фрилансер по жизни](https://zelenka.guru/threads/3214420/ "обновляется")
- [Чертоги Фрилансера v3 на GitHub](https://github.com/Maxim-Cherkasov/flsStartTemplate-v3/ "там же есть полезный файл readme")

- [Документация шаблона на оф сайте:](https://template.fls.guru/template-docs)
- [Для чего нужны Чертоги Фрилансера v3?](https://legosite.kz/ts/fls/ "Презентация шаблона и его возможностей")

# Документация: 


## Команды терминала

### Установка:
- npm i
или
npm i --legacy-peer-deps
(i) флаг --legacy-peer-deps позволит продолжить установку при возникновении 
конфликтов зависимостей (версий пакетов).

Запуск режима разработчика (c запуском сервера)
- npm run dev

Запуск сборки проекта (без запуска сервера, только финальная сборка)
- npm run build

Запуск сборки проекта и выгрузка результата на сервер по FTP. (без запуска локальконо сервера)
Конфигурация FTP находится в файле config/gulp-settings.js
- npm run deploy

Запуск сборки проекта и создание zip архива с именем проекта. (без запуска локальконо сервера)
- npm run zip

Запуск сборки проекта но без создания webp картинок. (без запуска сервера, только финальная сборка)
- npm run devbuild

Запуск создания SVG спрайта. Иконки нужно положить в папку src/svgicons,
готовый спрайт появится в папке src/img/icons/icons.svg
Изменения в папке src/svgicons не отслеживаются в dev режиме, при необходимости можно запустить повтоврую сборку спрайта
запускать создание спрайта стоит перед началом работ командой:
- npm run sprite


## Основные файлы для работы с шаблоном:
* js/app.js
* scss/style.scss

index.html - разводящая страница (содержание)
home.html - главная страница
файлы html/*.htm - подключаемые части


## Используются псевдонимы пути к папкам:
* @img = src/img
* @scss = src/scss
* @js = src/js


## Плагин для VS Code - Path Autocomplete
Настройки. Нажать в реждакторе F1, найти настройки Settings JSON, добавить код:  
 &nbsp "path-autocomplete.pathMappings": {  
    "@img": "${folder}/src/img", // псевдоним для папки img  
    "@scss": "${folder}/src/scss", // псевдоним для папки scss  
    "@js": "${folder}/src/js", //  псевдоним для папки js  
  }


## При возникновении ошибок убедитесь что:
1) У вас установлен Node.js последней версии
2) Терминал открыт с правами администратора
3) В названиях папок на всем пути к проекту нет символа # или !
4) Папки и файлы должны быть названы латиницей без пробелов
5) Тег img и его содержимое должны быть записаны в одну строку без переносов
6) В атрибуте src должен быть указан путь к существующей картинке


## Прочие проблемы и их решения:
//-----------------------------------
Ошибка "unable to resolve dependency tree"
Решение:
npm i --legacy-peer-deps
//-----------------------------------
Ошибка node-sass.
Решения:
npm rebuild node-sass
и/или
npm install sass gulp-sass --save-dev
//-----------------------------------
Ошибка Pyton
Решени:
npm install --global windows-build-tools
//------------------------------------------------------------------------------

### Для решения проблем с gulp-fonter-fix просто установите gulp-fonter-fix команднами
* npm install gulp-fonter-fix
* yarn add gulp-fonter-fix
//-----------------------------------
### Если в терминале возникает подобная ошибка
* SyntaxError: The requested module 'del' does not provide an export named 'default'

Ошибка "The requested module 'del' does not provide an export named 'default'" возникает, когда вы запускаете код, который не может импортировать экспорт по умолчанию из модуля 'del'.
Эта ошибка часто возникает, когда вы обновляете зависимости вашего проекта до более новой версии, и API этих зависимостей изменяется несовместимо с предыдущей версией.
Для исправления этой ошибки вы можете проверить документацию к используемой зависимости 'del', чтобы узнать о том, что такое экспорт по умолчанию и как он должен быть использован.
В этом конкретном примере, вам может потребоваться установить старую версию модуля 'del', которая работает с существующим кодом. Вы можете попробовать установить предыдущую версию кода, используя следующую команду:

* npm install del@2.2.2 --save-dev
