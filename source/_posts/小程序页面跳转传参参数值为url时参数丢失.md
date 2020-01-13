---
title: 小程序页面跳转传参参数值为url时参数丢失
date: 2020-01-13 22:31:22
tags: 小程序
---
![nasa](小程序页面跳转传参参数值为url时参数丢失/IMG_0586.jpg)

*当参数为 url 时，接受参数页面的 options 中的 url 值 ？ 之后的字符串被截取*

*此时，可以在传递参数页面使用 encodeURIComponent() 将字符串作为 URL 组件进行编码*
```javascript
    let url = encodeURIComponent('http://www.itubang.com/?r=news&id=9527');

    // 小程序跳转
    wx.navigateTo({
        url: `detail?url=${url}`
    })
```

*接收页面使用 decodeURIComponent() 解析*
```javascript

    // 小程序获取参数
    onload(options){
        let url = decodeURIComponent(options.url);
    }
```
