## the error "CLIENT_MISSING_INTENTS" means you forgot to pass intents while loging in!


This code below doesnt have any intents passed to the client
```js
const Discord = require("discord.js")
const bot = new Discord.Client()

bot.on('ready', ()=>{
    console.log("Bot loged in!")
})

bot.login("****")
```
As you can see we get this error: ![image](https://user-images.githubusercontent.com/71111395/151028535-4220dbed-d3ee-4554-bf5b-a22555150e8c.png)

So how do we fix this? Simple! Pass intents while making the client!
You can do so using this:
```js
const Discord = require("discord.js")
const bot = new Discord.Client({ intents: ["GUILDS", "GUILD_MEMBERS", "GUILD_MESSAGES"] })

bot.on('ready', ()=>{
    console.log("Bot loged in!")
})

bot.login("****")
```
There are a few ways to pass intents
```js
const Discord = require('discord.js');
const { intents } = require('discord.js');

const myIntents = new Discord.Intents();
myIntents.add(intents.FLAGS.GUILDS, intents.FLAGS.GUILD_MESSAGES, intents.FLAGS.GUILD_MESSAGE_REACTIONS);

const bot = new Discord.Client({ intents: myIntents });

bot.on('ready', ()=>{
    console.log("Bot loged in!")
})

bot.login("****")
```

You can see a full list of discord intents [here](https://discord.com/developers/docs/topics/gateway#list-of-intents)
