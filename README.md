# forStartApp

# Автоматичне форматування коду

Prettier — це упевнений форматувальник коду з підтримкою JavaScript, CSS та JSON. За допомогою Prettier ви можете автоматично форматувати код, який ви пишете, щоб забезпечити стиль коду у вашому проекті. Перегляньте сторінку Prettier's GitHub для отримання додаткової інформації та подивіться на цю сторінку, щоб побачити її в дії .

Щоб відформатувати наш код щоразу, коли ми робимо фіксацію в git, нам потрібно встановити такі залежності:

npm install --save husky lint-staged prettier
В якості альтернативи ви можете використовувати yarn:

yarn add husky lint-staged prettier
huskyполегшує використання githooks так, ніби вони є сценаріями npm.
lint-stagedдозволяє нам запускати сценарії для поетапних файлів у git. Перегляньте цю публікацію в блозі про lint-staged, щоб дізнатися більше про неї .
prettierце формататор JavaScript, який ми запускаємо перед коммітами.
Тепер ми можемо переконатися, що кожен файл відформатований правильно, додавши кілька рядків до package.jsonкореня проекту.

Додайте до scriptsрозділу такий рядок:

"scripts": {

- "precommit": "lint-staged",
  "start": "react-scripts start",
  "build": "react-scripts build",
  Далі ми додаємо поле 'lint-stage' до package.json, наприклад:

"dependencies": {
// ...
},

- "lint-staged": {
- "src/\*_/_.{js,jsx,json,css}": [
-     "prettier --single-quote --write",
-     "git add"
- ]
- },
  "scripts": {
  Тепер, коли ви робите фіксацію, Prettier автоматично форматує змінені файли. Ви також можете запустити ./node*modules/.bin/prettier --single-quote --write "src/\**/\_.{js,jsx,json,css}", щоб відформатувати весь проект вперше.

Далі ви можете інтегрувати Prettier у свій улюблений редактор. Прочитайте розділ про інтеграцію редактора на сторінці Prettier GitHub.

# link https://github.com/luxplanjay/fe-03-react#formatting-code-automatically !!!!
