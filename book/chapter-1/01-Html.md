#HTML 开发规范指南

HTML 开发规范指南

##1.文档目录结构

```
.
├── assets
│   ├── css
│   ├── fonts
│   ├── images
│   ├── js
│   └── pic
├── favicon.ico
├── index.html
```

##2.文档类型

统一使用HTML5的标准文档类型：<!DOCTYPE html>

```html
<!DOCTYPE html>
<html>
    <head>
    </head>
</html>
```

##3.语言属性

对不同语言文件使用正确的语言设定。

```html
<html lang="zh-cmn-Hans"><!-- 简体中文 -->
<html lang="zh-cmn-Hant"><!-- 繁体中文 -->
<html lang="en-us"><!-- 英文 -->
```

##4.移动端设置

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

##5.meta设定

了解各种meta的设定，针对具体项目取舍。

```html
<!DOCTYPE html>
<html lang="zh-cmn-Hans">

<head>
    <meta charset="utf-8"><!-- 字符编码 -->
    <title>value</title>
    <meta name="keywords" content="value" /><!-- 关键字 -->
    <meta name="description" content="value"><!-- 描述 -->
    <meta name="author" content="value"><!-- 作者 -->
    <meta http-equiv="Cache-Control" content="no-siteapp" /><!-- 禁止百度转义 -->
    <meta name="google" value="notranslate"><!-- 禁止google翻译 -->
    <link rel="stylesheet" type="text/css" media="value" href="uri" /><!-- 外链css -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"><!-- 移动端屏幕设置 -->
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" /><!-- 使用最新ie框架 -->
    <meta name="renderer" content="webkit"><!-- 默认使用webkit渲染 -->
</head>

</html>
```
##6.缩进

使用tab（4个空格宽度）来进行缩进，可以在IDE里进行设置

##7.语义化标签

* 根据HTML元素的本身用途去使用它们；
* 禁止使用被废弃的用于表现的标签，如 center, font 等；
* 部分在XHTML1中被废弃的标签，在HTML5中被重新赋予了新的语义，在选用时请先弄清其语义，如:b, i, u等。

不允许：

```
<p>标题</p>
```

应该：

```
<h1>标题</h1>
```

>虽然使用p标签，也可以通过CSS去定义它的外观和标题相同，但p标签本身的并不是表示标题，而是表示文本段落

##8.模块化

* 每个模块必须有一个模块名；
* 每个模块的基本组成部分应该一致；
* 模块的子节点类名需带上模块名（防止模块间嵌套时产生不必要的覆盖）；
* 孙辈节点无需再带模块名。

代码如：

    <section class="m-detail">
        <header class="m-detail-hd">
            <h1 class="title">模块标题</h1>
        </header>
        <div class="m-detail-bd">
            <p class="info">一些实际内容</p>
        </div>
        <footer class="m-detail-ft">
            <a href="#" class="more">更多</a>
        </footer>
    </section>

> 其中 `.m-detail-hd`, `.m-detail-bd`, `.m-detail-ft` 为可选，视具体模块情况决定是否需要抽象为这种 **头，中，尾** 的结构

##示例文件

[HTML示例文件](../../code/chapter-1/01-html.html)