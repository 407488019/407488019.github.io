---
layout:       post
title:        "当网页内容小于屏幕高度时生成DIV将footer固定到底部"
author:       "喵大"
tags:
    - js
---

## 实现代码

> 如果一个网页的内容很少，就是`<body>` 的高度小于屏幕的高度，那么 `<footer>` 就不在屏幕最下方。
>
> 在 `<footer>` 上方添加一个 `<div id="push-to-bottom"></div>` 将 `<footer>` 挤到屏幕最下方

```
// jQuery footer height
pushtobottom();
$(window).scroll(pushtobottom).resize(pushtobottom);
function pushtobottom() {
    var docHeight = $(document.body).height() - $("#push-to-bottom").height();
    if (docHeight < $(window).height()) {
      var diff = $(window).height() - docHeight;
      if (!$("#push-to-bottom").length > 0) {
        $("#bottom").before('<div id="push-to-bottom"></div>');
      }
      $("#push-to-bottom").height(diff);
    }
}
```



