# LongReset

### 简介：

version：0.0.2

目前还不是很完整，我自己在用。

除了让各个浏览器表现一致外(部分代码参考与：Normalize.css

)，还注重了一些中文的排版(部分代码参考与：typo.css)。

所以分为**重置、排版、H5、常用特殊样式**四个方面。

### 起步：

```html
<!- 在所有样式前引用 ->
<link rel="stylesheet" type="text/css" href="longreset">
```

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

**内外边距**

```css
/* 清除内外边距 */
body, h1, h2, h3, h4, h5, h6, hr, p, blockquote, /* structural elements 结构元素 */
dl, dt, dd, ul, ol, li, /* list elements 列表元素 */
pre, /* text formatting elements 文本格式元素 */
fieldset, lengend, button, input, textarea, /* form elements 表单元素 */
th, td { /* table elements 表格元素 */
    margin: 0;
    padding: 0;
}
```

**重置列表元素**

```css
/* 重置列表元素 */
ul, ol { list-style: none; }
```

**重置链接文本格式**

```css
/* 链接展示的时候不应该有下划线 */
a { text-decoration: none; }

/* 链接hover的时候出现下划线 */
a:hover { text-decoration: underline; }
```

**表格**

```css
/* 去掉各Table cell 的边距并让其边重合 */
table {
  border-collapse: collapse;
  border-spacing: 0;
}
```

**去除默认边框**

```css
/* 去除默认边框 */
fieldset,
img {
  border: 0;
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
body,
button, input, select, textarea {
  font: 300 1em/1.8 PingFang SC, Lantinghei SC, Microsoft Yahei, Hiragino Sans GB, Microsoft Sans Serif, WenQuanYi Micro Hei, sans;
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

