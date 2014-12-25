---
layout: post
title: Centering Vertically and Horizontally with Css
---

For any beginner in **Front End Development**, centering is a large deal. It's tough to find a solution you understand and can count on to work in the right situation. After pouring over the web myself, I present to you, the best way I have found for centering HTML elements.

I'll brake it up into seperate pieces first and then merge them together. Enjoy!

**Centering Horizontally**

Css has an awesome magical entity called *auto* which will set the right margin depending on other factors.

```Css
div {
  width:100px;
  height:100px;
  margin:0 auto;
}
```

This gives us a centered div of our desired width and height.
