# Dom Scripting

****

## Context

- CSS 简介
- CSS Selector
- DOM 操作
- 事件编程
- 作业相关

****

# CSS
> abbr. Cascading Style Sheets

****

```html
<!-- html -->
<head>
	<link href="style.css" type="text/css" />
</head>
<body>
	<span class="text">hello world!</span>
</body>
```

```css
/* style.css */
span.text {
	color: #f00;	
}					

```

```
CSS 语法：

<css-selector> {
	<property>: <value>
}
```

***

## 内联样式

```html
<body style="color:#f00">
	<div style="padding:10px; border:1px solid #000">
	</div>
</body>
```

****

## CSS Selector

用来匹配元素

- 在 DOM 编程中，CSS Selector 可用于选择特定的元素
- 决定 CSS 样式的定义是否会被应用到元素上

[reference](http://www.w3.org/TR/CSS2/selector.html) 

***

## CSS Selector 基本元素

Pattern | 含义
------- | ---------------------
\#abc   | id="abc"
.abc    | class="abc"
abc     | &lt;abc>&lt;/abc>
[abc]   | 是否包含名为 abc 的属性 &lt;div abc>&lt;/div>
[abc=d] | 是否包含名为 abc 的属性，并且值为 `'d'`

***

## CSS Selector 的组合

组合方式 | 含义
------- | ---------------------
无空格   | 表明该元素自身需要同时满足这几个条件
空格     | 表明嵌套关系
\>       | 标明直接的嵌套关系(儿子辈，不能是孙子辈)

***

## Example

```html
<!-- 对于这样一段 html -->
<div class="a b">
	<div class="b c">
		<div class="c"></div>
	</div>
</div>
```

```css
/* 如下 CSS Selector 分别可以匹配到什么元素 */
.c
div.c
div.b.c
.a .c
.a > .c
```

***

## Selector 优先级

id(100) > class(10) > tag(1)

***

## Practices

使用 [jQuery](http://jquery.com) 后，在当前的运行环境中会增加一个名为 `$` 的全局变量

```js
$(selector)
```


****

## CSS 与 DOM

![webkit](../doc/src/webkit-renderer.png)

****

# Scripting

**** 

## 什么是 DOM ？

****

## JS 是如何能够操作 DOM 的？

***

JavaScript 语言规范中，是不包含任何 DOM 相关的内容的

之所以 JavaScript 能够操作 DOM，是因为 DOM 引擎为 JavaScript 运行环境暴露了 API

****

## DOM 方法

- [获取 DOM](http://api.jquery.com/category/selectors/): `$`
- [操作 DOM](http://api.jquery.com/category/manipulation/)
- [遍历 DOM](http://api.jquery.com/category/traversing/)
- [DOM 样式](http://api.jquery.com/category/css/)

***

## Practices

![box](../doc/src/box.png)

我们尝试将 [jQuery](http://jquery.com) 首页的该元素移除 

***

```js
// 已知有如下方法
$(selector); // 获取 DOM

.remove() // 能够将当前 DOM 移除
```

大家尝试在 chrome 的 console 窗口中试用 JS 实现这个效果。

****

## DOM 事件编程

```js
.on(type, handler);
.on({
	<type>: handler
});
```
***

## 事件类型

鼠标事件    | 键盘事件    | 窗口事件
---------- | --------- | ---------
click      | keypress  | scroll
dbclick    | keydown   | resize
mouseover  | keyup     |
mousemove  |           |
mouseout   |           |













