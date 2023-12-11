---
layout: default
title: "Killing a JavaScript function which runs infinite"
categories: [JavaScript]
author: "Stephen Quan"
tags: [JavaScript]
---

I posted on [https://stackoverflow.com/a/56829821/881441](https://stackoverflow.com/a/56829821/881441) a code snippet for breaking 'infinite' running Javascript functions:

```js
function execWithTimeout(gen, timeout = 100) {
    const limit = Date.now() + timeout
    for (let output of gen()) {
        console.log(output)
        if (Date.now() > limit) throw(new Error("Timeout reached"))
    }
}

function *runInfinite() {
    let i = 0
    while (1) {
        yield i++
    }
}

execWithTimeout(runInfinite)
```
