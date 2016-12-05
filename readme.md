# Ready.css

## 简介：

版本：0.0.3

为了前端开发做准备，通过ReadyCSS让各个浏览器表现一致外，包括不同浏览器的字体大小、渲染、边距、边框等问题，还注重了一些中文的排版。

部分代码参考与：

- Normalize.css
- typo.css

所以分为**重置、排版、H5、常用特殊样式**四个方面。

### 注意！！

目前还处于开发阶段，使用的时候请慎重！！

## 测试平台

- IE 11
- Edge 38.+
- Chrome 54
- Firefox
- 360安全浏览器
- 360极速浏览器



## 开始使用

暂时不提供CDN加速。

```html
<!- 在所有样式前引用 ->
<link rel="stylesheet" type="text/css" href="longreset">
```

## 代码哲学

### RESET:

**字体颜色、网页背景和字体渲染效果保持一致**

```css
html {
  
  /* 让字体颜色更有质感 */
  color: #333;
  
  /* 防止用户自定义背景颜色对网页的影响 */
  background: #fff;
  
  /* 当样式表里font-size<12px时，中文版部分浏览器里字体显示仍为12px */
  -webkit-text-size-adjust: 100%;
  -ms-text-size-adjust: 100%;
  
  /* 侧重文本的可读性（清晰度），而不是渲染速度和几何精度。 */
  text-rendering: optimizelegibility;
}
```

**去除浏览器默认的内外边距**

```css
/* 清除浏览器默认的内外边距 */
body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, /* structural elements 结构元素 */
dl, dt, dd, ul, ol, li, /* list elements 列表元素 */
pre, /* text formatting elements 文本格式元素 */
fieldset, lengend, button, input, textarea, /* form elements 表单元素 */
th, td { /* table elements 表格元素 */
    margin: 0;
    padding: 0;
}
```

**去除浏览器默认的边框**

```css
/* 去除默认边框 */
fieldset,
img {
  border: 0;
}
```

**重置列表元素**

```css
/* 去除ul、ol默认的list-style样式 */
ul, ol { list-style: none; }
```

**重置链接文本格式**

```css
/* 链接展示和hover的时候不应该有下划线 */
a,a:hover { text-decoration: none; }
```

**表格**

```css
/* 去掉各Table cell 的边距并让其边重合 */
table {
  border-collapse: collapse;
  border-spacing: 0;
}
```

**重置hr**

```css
hr {
    margin: 0;
    border: 0;
    height: 1px;
    background: #333;
}
```

### 排版


**一份好看的默认字体**

```css
/* 要注意表单元素并不继承父级 font 的问题 */
/* 字体粗细300更加好看 */
/* 默认字体大小设置为1em便于适应不同的浏览器 */
/* 让所有的字体的行高为自己本身的大小，否则chrome浏览器渲染字体后所占高度会大于设定字体的大小 */
/* 这份字体表参考于typo.css 如果不喜欢可以替换成你喜欢的样式 */
body,
button, input, select, textarea {
  font: 300 1em/1.0 PingFang SC, Lantinghei SC, Microsoft Yahei, Hiragino Sans GB, Microsoft Sans Serif, WenQuanYi Micro Hei, sans;
}
```

### H5

**重置H5标签**

```css
/* 重设 HTML5 标签, IE 需要在 js 中 createElement(TAG) */
article, aside, details, figcaption, figure, footer, header, menu, nav, section,
audio, canvas, video {
  display: block;
}
```



### 特殊样式

**启用border-box**

```css
/* 如果你的项目仅支持 IE9+ | Chrome | Firefox 等，推荐在 <html> 中添加 .borderbox 这个 class */
html.borderbox *, html.borderbox *:before, html.borderbox *:after {
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
```

**清除浮动**

```css
.clearfix:after {
    display: table;
    clear: both;

    content: '';
}
```

