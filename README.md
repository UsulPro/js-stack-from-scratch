# JavaScript Stack from Scratch

[![Yarn](/img/yarn.png)](https://yarnpkg.com/)
[![React](/img/react.png)](https://facebook.github.io/react/)
[![Gulp](/img/gulp.png)](http://gulpjs.com/)
[![Redux](/img/redux.png)](http://redux.js.org/)
[![ESLint](/img/eslint.png)](http://eslint.org/)
[![Webpack](/img/webpack.png)](https://webpack.github.io/)
[![Mocha](/img/mocha.png)](https://mochajs.org/)
[![Chai](/img/chai.png)](http://chaijs.com/)
[![Flow](/img/flow.png)](https://flowtype.org/)

[![Build Status](https://travis-ci.org/verekia/js-stack-from-scratch.svg?branch=master)](https://travis-ci.org/verekia/js-stack-from-scratch)

## Работа над переводом идет. Это не окончательная версия!

перевод терминов см. [Definitions.md](Definitions.md)

[вопросы, замечания, предложения](https://github.com/UsulPro/js-stack-from-scratch/issues)

Добро пожаловать в мое современное руководство по JavaScript стеку: **JavaScript стек с Нуля**.

Это минималистичное и "сразу-к-делу" руководство по сборке JavaScript стека. Оно требует некоторых общих знаний программирования и основ JavaScript. **Оно фокусируется на использовании инструментов вместе** и дает Вам **простейший возможный пример** для каждого инструмента. Вы можете рассматривать это руководство как *путь создания собственного шаблона с нуля*.

Конечно, Вам не обязательно использовать весь этот стек для создания простой web-страницы с несколькими JS взаимодействиями (комбинации Babel + jQuery достаточно!), но если Вы хотите построить масштабируемое веб-приложение, и Вам нужна помощь в настройке, это руководство отлично Вам подойдёт.

Поскольку целью данного руководства является сборка различных инструментов, я не буду вдаваться в подробности о том, как эти инструменты работают по-отдельности. Обратитесь к документации или найдите другие руководства, если хотите получить более углубленные знания о них.

Большая часть стека, описанного в данном руководстве, использует React. Если Вы только начинаете и просто хотите изучить React, [create-react-app](https://github.com/facebookincubator/create-react-app) поможет Вам очень быстро настроить окружение React с готовой конфигурацией. Я бы, например, рекомендовал бы этот подход тем, кто пришел в команду, использующую React, и вынужден догонять. В этом руководстве Вы не будете использовать готовую конфигурацию, потому что я хочу, чтобы Вы поняли все, что происходит под капотом.

Для каждой главы доступны примеры кода, и Вы можете запустить их все с помощью `yarn && yarn start` или `npm install && npm start`. Я рекомендую писать все с нуля самостоятельно, следуя **пошаговым инструкциям** в каждой главе.

**Каждая глава содержит код из предыдущих глав**, так что если Вы просто ищете шаблон проекта, содержащий сразу все, клонируйте последнюю главу и готово.

Примечание: Порядок глав не обязательно является наиболее познавательным. Например, тестирование / типизация могли бы быть перед введением в React. Премещать разделы довольно трудно, так как мне нужно вносить изменения в каждую следующую главу. Если все устаканится, я мог бы реорганизовать все это в лучшую сторону.

Код данного руководства работает на Linux, macOS и Windows.

## Содержание

[1 - Node, NPM, Yarn, и package.json](/tutorial/1-node-npm-yarn-package-json)

[2 - Установка и использование пакетов](/tutorial/2-packages)

[3 - Настройка ES6 с Babel и Gulp](/tutorial/3-es6-babel-gulp)

[4 - Использование синтактиса ES6 и классов](/tutorial/4-es6-syntax-class)

[5 - Синтаксис модулей ES6](/tutorial/5-es6-modules-syntax)

[6 - ESLint](/tutorial/6-eslint)

[7 - Клиентское приложение на основе Webpack](/tutorial/7-client-webpack)

[8 - React](/tutorial/8-react)

[9 - Redux](/tutorial/9-redux)

[10 - Иммутабельный JS и улучшения Redux](/tutorial/10-immutable-redux-improvements)

[11 - Тестировние с Mocha, Chai, и Sinon](/tutorial/11-testing-mocha-chai-sinon)

[12 - Типизация с Flow](/tutorial/12-flow)

## Скоро

Production / development окружения, Express, React Router, серверный рендеринг, стилизация, Enzyme, перехватчики Git.

## Переводы

- [Китайский](https://github.com/pd4d10/js-stack-from-scratch) by [@pd4d10](http://github.com/pd4d10)
- [Итальянский](https://github.com/fbertone/js-stack-from-scratch) by [Fabrizio Bertone](https://github.com/fbertone)

Если Вы хотите добавить Ваш перевод, пожалуйста, прочитайте [рекомендации к переводу](/how-to-translate.md) перед тем как начать!

## Сведения

Автор: [@verekia](https://twitter.com/verekia) – [verekia.com](http://verekia.com/).

Лицензия: MIT
