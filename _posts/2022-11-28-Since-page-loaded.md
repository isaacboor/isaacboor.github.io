---
layout: post
title: Since this page was loaded...
description: How often things happen
summary: How often things happen
tags: project
---
A page displaying counters that count up, showing how often things happen.

## [Take a look](https://www.isaacboor.me/sincethispageloaded)

### How did I make it?

You can view the full code [here](https://github.com/isaacboor/sincethispageloaded)

Heres a quick explanation.

1. First I have a function that formats numbers with commas

```js
function numberWithCommas(x) {
    return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
}
```

2. Then I set all the counters to 0

```js
var emails = 0;
var babies = 0;
var googles = 0;
var deaths = 0;
. . . // Some counters emmited from code.
```

3. Then I have some functions that add certain amounts to each.

```js
function email() {
    emails += 500000;
    document.getElementById("mails").innerText = numberWithCommas(emails);
}
function born() {
    babies += 1;
    document.getElementById("born").innerText = numberWithCommas(babies);
}
function google() {
    googles += 400;
    document.getElementById("google").innerText = numberWithCommas(googles);
}
function die() {
    deaths += 1;
    document.getElementById("die").innerText = numberWithCommas(deaths);
}
. . .
```

4. Then I have some interval functions

```js
window.setInterval(email, 100)
window.setInterval(born, 500)
window.setInterval(google, 10)
window.setInterval(die, 600)
. . .
```