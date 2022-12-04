---
layout: post
title: Message Tricks
description: Change your text
summary: Change your text
tags: project
---
A simple page that lets make your text look weird.

[Take a look](https://www.isaacboor.me/messagetricks)

### Examples:

- ⍺ℓ†℮Իռ⍺†ɪṼ℮ 𐐽հ⍺Ի⍺𐐽†℮Ի$
- ʇxǝʇ nʍod ǝdᴉsdn
- G̷̖̬͍͈͇͉̍̾͐́́̈̉̕͝͝ḻ̵̬̲̝̌͗̿̅̐̅̈́͑̾̎̿̋͊̇͝ȋ̷̧̻̭̙̣̠͍̲̻̆̏͝t̸̨̖̩͊̍̈́ç̷̹̜̙̣̬̘̱̞͕̝͎̤̯̀h̷̡̯͚̮̬̭͕̙̜̻͎̟͎̎ͅe̸̥̭̬͍̪̺͕͇̋͛̀̐͗̉̌̕d̸̹̥͚̭͂̌̏͂̀͗̍̽̂̚͝ ̵͙͙̩͖͖̐͐̆̑́͌͛̔̾̿̊̓Ḷ̸̼̯̹̪̬͙͎͓̫̼̭̭̌̾̍̉͂͜e̷̛̱̤̠̪̥̺̥̭̾͂̀̾̾́̃̀̉͂͝t̴̢̰̘̤̟̯͍̰̘̭̳͇͉̓̍͐̕͜͜t̴̞͇̼̝̪̻̬̔͋̂́̿͘ḛ̶̯̤͓̪̞̯̪̪̤̙̘͐̍̉͌͗̏̓̾͑̽̀̓͘͜͝r̵̨̧̛̛͕͖̘̟̮̩̬̞̦̼̆̾̏̆̒̈͝͝s̶͉̝̗̾̽̆̆̋͠

<br>

### How did I make it?

You can view the full code [here](https://github.com/isaacboor/messagetricks)

But if want a quick tldr rundown of the main concepts, here you go.

1. First, I create a replaceAll function.

```js
String.prototype.replaceAll = function (search, replacement) {
    var target = this;
    return target.replace(new RegExp(search, 'g'), replacement);
};
```


2. Then I create a function for the 'alternative characters'. (similar one for the upside down)

```js
// Not the cleanest code, I know
function applyAltChars(input) {
    input = input.toLowerCase();
    input = input.replaceAll('a', '&#9082;')
    input = input.replaceAll('b', '&#5234;')
    input = input.replaceAll('c', '&#66621;')
    input = input.replaceAll('d', '&#5095;')
    input = input.replaceAll('e', '&#8494;')
    input = input.replaceAll('f', '&#383;')
    input = input.replaceAll('g', '&#397;')
    . . .
    document.getElementById('altcharsoutput').innerHTML = input;
}
```

3. I use a reverser function for the flipped and upside down.

```js
function reverseString(str) {
    var splitString = str.split("");
    var reverseArray = splitString.reverse();
    var joinArray = reverseArray.join("");
    return joinArray;
}
```

4. And for bubbles, wonky and glithed I used a library called [lunicode.js](https://github.com/combatwombat/Lunicode.js).

```js
function applyGlitched(input) {
    input = luni.tools.creepify.encode(input);
    document.getElementById('glitchedoutput').innerHTML = input;
}
```