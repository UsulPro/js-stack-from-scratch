# 01 - Node, Yarn и `package.json`

Исходный код для этой главы доступен [здесь](https://github.com/verekia/js-stack-walkthrough/tree/master/01-node-yarn-package-json).

В этом разделе мы настроим Node, Yarn, базовый `package.json` файл и попробуем поработать с пакетами.

## Node

> 💡 **[Node.js](https://nodejs.org/)** — это среда выполнения JavaScript. Хотя Node.js в основном используется для Back-End разработки, он так же может быть использован для скриптинга (general scripting). В контексте Front-End разработки он может быть использован для выполнения целой кучи задач вроде подсветки (linting), тестирование и сборки файлов.

Мы будем использовать Node практически для всего в этом курсе, так что вам он понадобится. Перейдите на [страницу загрузки](https://nodejs.org/en/download/current/) для **macOS** или **Windows**,или на [страницу установки с помощью менеджера пакетов](https://nodejs.org/en/download/package-manager/) для Linux дистрибутивов.

Например, на **Ubuntu / Debian**, вам понадобится выполнить следующие команды, чтобы установить Node:

```sh
curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
sudo apt-get install -y nodejs
```

Вам понадобиться любая версия Node старше 6.5.0 (> 6.5.0).

## Инструменты управления версиями Node

Если вам нужна гибкость в использовании нескольких версий Node, посмотри на [NVM](https://github.com/creationix/nvm) или [tj/n](https://github.com/tj/n).

## NPM

NPM — это стандартный менеджер пакетов для Node. Он автоматически устанавливается вместе с Node. Менеджеры пакетов используются для установки и управления пакетами (модулями с кодом, написанными вами или кем-то другим). Мы будем использовать много пакетов в этом курсе, но мы будем пользоваться другим менеджером пакетов — Yarn.

## Yarn

> 💡 **[Yarn](https://yarnpkg.com/)** — это менеджер пакетов для Node.js, который намного быстрее чем NPM, может работать офлайн (offline support) и выбирает зависимости [более предсказуемо](https://yarnpkg.com/en/docs/yarn-lock).

Поскольку он [вышел](https://code.facebook.com/posts/1840075619545360) в октябре 2016, он очень быстро адоптировался и может скоро станет менеджером пакетов по выбору JavaScript сообщества (become the package manager of choice of the JavaScript community). Если вы придерживаетесь NPM, вы можете просто заменить все `yarn add` и `yarn add --dev` команды на `npm install --save` и `npm install --save-dev`.

Установите Yarn следуя [инструкциям](https://yarnpkg.com/en/docs/install) для вашей системы. Я рекомендую использовать **Installation Script** из вкладки *Alternatives* если вы используете MacOS или Unix, чтобы [избежать](https://github.com/yarnpkg/yarn/issues/1505) зависимости (relying) от других менеджеров пакетов:

```sh
curl -o- -L https://yarnpkg.com/install.sh | bash
```

## `package.json`

> 💡 **[package.json](https://yarnpkg.com/en/docs/package-json)** is the file used to describe and configure your JavaScript project. It contains general information (your project name, version, contributors, license, etc), configuration options for tools you use, and even a section to run *tasks*.

- Create a new folder to work in, and `cd` in it.
- Run `yarn init` and answer the questions (`yarn init -y` to skip all questions), to generate a `package.json` file automatically.

Here is the basic `package.json` I'll use in this tutorial:

```json
{
  "name": "your-project",
  "version": "1.0.0",
  "license": "MIT"
}
```

## Hello World

- Create an `index.js` file containing `console.log('Hello world')`

🏁 Run `node .` in this folder (`index.js` is the default file Node looks for in a folder). It should print "Hello world".

**Note**: See that 🏁 racing flag emoji? I will use it every time you reach a **checkpoint**. We are sometimes going to make a lot of changes in a row, and your code may not work until you reach the next checkpoint.

## `start` script

Running `node .` to execute our program is a bit too low-level. We are going to use an NPM/Yarn script to trigger the execution of that code instead. That will give us a nice abstraction to be able to always use `yarn start`, even when our program gets more complicated.

- In `package.json`, add a `scripts` object like so:

```json
{
  "name": "your-project",
  "version": "1.0.0",
  "license": "MIT",
  "scripts": {
    "start": "node ."
  }
}
```

`start` is the name we give to the *task* that will run our program. We are going to create a lot of different tasks in this `scripts` object throughout this tutorial. `start` is typically the name given to the default task of an application. Some other standard task names are `stop` and `test`.

`package.json` must be a valid JSON file, which means that you cannot have trailing commas. So be careful when editing manually your `package.json` file.

🏁 Run `yarn start`. It should print `Hello world`.

## Git and `.gitignore`

- Initialize a Git repository with `git init`

- Create a `.gitignore` file and add the following to it:

```gitignore
.DS_Store
/*.log
```

`.DS_Store` files are auto-generated macOS files that you should never have in your repository.

`npm-debug.log` and `yarn-error.log` are files that are created when your package manager encounters an error, we don't want them versioned in our repository.

## Installing and using a package

In this section we will install and use a package. A "package" is simply a piece of code that someone else wrote, and that you can use in your own code. It can be anything. Here, we're going to try a package that helps you manipulate colors for instance.

- Install the community-made package called `color` by running `yarn add color`

Open `package.json` to see how Yarn automatically added `color` in  `dependencies`.

A `node_modules` folder has been created to store the package.

- Add `node_modules/` to your `.gitignore`

You will also notice that a `yarn.lock` file got generated by Yarn. You should commit this file to your repository, as it will ensure that everyone in your team uses the same version of your packages. If you're sticking to NPM instead of Yarn, the equivalent of this file is the *shrinkwrap*.

- Write the following to your `index.js` file:

```js
const color = require('color')

const redHexa = color({ r: 255, g: 0, b: 0 }).hex()

console.log(redHexa)
```

🏁 Run `yarn start`. It should print `#FF0000`.

Congratulations, you installed and used a package!

`color` is just used in this section to teach you how to use a simple package. We won't need it anymore, so you can uninstall it:

- Run `yarn remove color`

## Two kinds of dependencies

There are two kinds of package dependencies, `"dependencies"` and `"devDependencies"`:

**Dependencies** are libraries you need for your application to function (React, Redux, Lodash, jQuery, etc). You install them with `yarn add [package]`.

**Dev Dependencies** are libraries used during development or to build your application (Webpack, SASS, linters, testing frameworks, etc). You install those with `yarn add --dev [package]`.

Next section: [02 - Babel, ES6, ESLint, Flow, Jest, Husky](02-babel-es6-eslint-flow-jest-husky.md#readme)

Back to the [table of contents](https://github.com/verekia/js-stack-from-scratch#table-of-contents).
