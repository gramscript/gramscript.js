<!-- <p align='center'>
  <img alt="GitHub Sparkline" src="https://github.com/gramscript/gramscript">
</p> -->
<br>
<p align="center"> 
  <img alt="GitHub code size in bytes" src="https://img.shields.io/github/languages/code-size/gramscript/gramscript?logo=files&logoColor=f72585&style=social">
  <a href="https://www.codefactor.io/repository/github/gramscript/gramscript/overview/main"><img src="https://www.codefactor.io/repository/github/kalanakt/all-url-uploader/badge/main" alt="CodeFactor" /></a>
  <img alt="GitHub issues" src="https://img.shields.io/github/issues-raw/gramscript/gramscript?color=8eecf5&logo=anaconda&logoColor=06d6a0&style=social">
  <img alt="GitHub" src="https://img.shields.io/github/license/gramscript/gramscript?logo=adguard&logoColor=390099&style=social">
  <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/gramscript/gramscript?color=90e0ef&logoColor=ff4d6d&style=social">
  <img alt="GitHub last commit" src="https://img.shields.io/github/last-commit/gramscript/gramscript?logo=electron&logoColor=89fc00&style=social">
</p>
<br>

## Installation 

```consol
npm install gramscript
```
```consol
npm i gramscript
```
```consol
yarn add gramscript
```

## Usage
Creating custom bot Object

```js
const TeleBot = require('gramscript');
const bot = new TeleBot('TELEGRAM_BOT_TOKEN');

// bot's script here

bot.start();
```

## Quick Examples

### Forwad Same Message Text

```js
const TeleBot = require('gramscript');
const bot = new TeleBot('123yuio456pasd678fghWqaz');

// bot command
bot.on('/hello', (msg) => {
  return bot.sendMessage(msg.from.id, `Hello, ${ msg.from.first_name }!`);
});

// if user send message text , bot will forward same content
bot.on('text', (msg) => msg.reply.text(msg.text));

// if user send sticker, bot will forwad same sticker
bot.on('sticker', (msg) => {
    return msg.reply.sticker('http://i.imgur.com/VRYdhuD.png', { asReply: true });
});

// also work with multiple events
bot.on(['/start', 'audio', 'sticker'], msg => {
  return bot.sendMessage(msg.from.id, 'Bam!');
});

bot.start();
```
