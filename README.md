# Домашнее задание к лекции «Платформы: браузер vs Node.js»

## Библиотека для браузера и Node.js (продолжение..)

### Шаг 7. Использование библиотеки

Нас будет интересовать два варианта использования (поскольку через шаблон Webpack всё будет работать как обычно):
* в Node.js
* в браузере через тег script

### Для Node.js:

1. Создайте новый проект (GitHub репозиторий, clone, перейдите в каталог склонированного репо), выполните в нём команду: `npm init`
2. Установите ваш пакет: `npm install @netology-code/ajs@1.0.0` (естественно, вам нужно писать не netology-code, а имя своего репо)
3. Создайте файл `src/index.js` следующего содержания:

```js
// у вас будет не netology-code, а ваш username
const ajs = require('@netology-code/ajs');

console.log(ajs.info());
```

Пропишите скрипт запуска (в package.json):
```
"scripts": {
   "start": "node src/index.js"
}
```

Проверьте, что запускается (`npm start`):

![](pic/node.png)

### Для браузера:

Здесь нам придётся немного посложнее, поскольку для npmjs.com есть специальный [CDN](https://unpkg.com/), который вам позволяет через URL подключать конкретные файлы.

Для GitHub Packages такого пока нет, поэтому придётся сделать чуть по-другому.

Удалите каталог dist из .gitignore и запушьте его на GitHub (удостоверьтесь, что он там появился):

![](pic/dist.png)

Перейдите к файлу index.js (который в каталоге dist) и нажмите на кнопку Raw:

![](pic/raw.png)

Скопируйте URL из строки браузера (в примере он вот такой: https://raw.githubusercontent.com/netology-code/ajs/master/dist/index.js).
 
Теперь перейдите на сервис [Statically](https://statically.io/convert/), подставьте получившийся URL в верхнее поле (1), а с нижнего скопируйте итоговый URL (2):

![](pic/cdn.png)

Остался последний штрих: воспользуйтесь сервисом [JSBin](https://jsbin.com) для того, чтобы быстро проверить работоспособность вашего кода:

![](pic/jsbin.png)

После чего выберите File -> Save Snapshot:

![](pic/snapshot.png)

После этого станет активна кнопка Share (вам нужно скопировать URL):

![](pic/share.png)

### Итог: [ссылка на JSBin](https://jsbin.com/juvadanalo/edit?html,console)
