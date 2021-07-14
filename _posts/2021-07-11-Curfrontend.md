---
layout: post
read_time: true
show_date: true
title: Cursor-Recording some codes of frontend
date:   2021-07-12 21:32:20 -0600
description: Record some codes that I used
img: posts/20210711/Frontend.png
tags: [front-end,coding,HTML,programming,cursor]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
During a couple few months ago, I was building my own websites.I bought two domains last year, costing 6 yuan in total. By using Github,we can build a very well website, of course, if you want to connect to the database, you may need to rent a server. Or else, except the domain, all the material is free.

## What is frontend?

When it comes to make webpage, development of frontend mainly includes HTML, CSS and JS three different file types. If you want to make an app in cell phones, you may need to learn XML.

![image1](./assets/img/posts/20210711/1.jpg)
HTML is the short of HyperText Markup Language,which is the standard markup language for documents designed to be displayed in a web browser. It can be assisted by technologies such as Cascading Style Sheets (CSS) and scripting languages such as JavaScript.

The combination of HTML, CSS and JS forms diversity website pages.
## CSS cursor Property
CSS can generate a bunch of different mouse cursors:
```javascript
.alias {cursor: alias;}
.all-scroll {cursor: all-scroll;}
.auto {cursor: auto;}
.cell {cursor: cell;}
.context-menu {cursor: context-menu;}
.col-resize {cursor: col-resize;}
.copy {cursor: copy;}
.crosshair {cursor: crosshair;}
.default {cursor: default;}
.e-resize {cursor: e-resize;}
.ew-resize {cursor: ew-resize;}
.grab {cursor: grab;}
.grabbing {cursor: grabbing;}
.help {cursor: help;}
.move {cursor: move;}
.n-resize {cursor: n-resize;}
.ne-resize {cursor: ne-resize;}
.nesw-resize {cursor: nesw-resize;}
.ns-resize {cursor: ns-resize;}
.nw-resize {cursor: nw-resize;}
.nwse-resize {cursor: nwse-resize;}
.no-drop {cursor: no-drop;}
.none {cursor: none;}
.not-allowed {cursor: not-allowed;}
.pointer {cursor: pointer;}
.progress {cursor: progress;}
.row-resize {cursor: row-resize;}
.s-resize {cursor: s-resize;}
.se-resize {cursor: se-resize;}
.sw-resize {cursor: sw-resize;}
.text {cursor: text;}
.url {cursor: url(myBall.cur),auto;}
.w-resize {cursor: w-resize;}
.wait {cursor: wait;}
.zoom-in {cursor: zoom-in;}
.zoom-out {cursor: zoom-out;}
```
## Definition and Usage

|Default value:|	auto|
|--|--|
|Inherited:	|yes|
|Version:	|CSS2|

JavaScript syntax:
```
object.style.cursor="crosshair"
```
HTML syntax: 
```
<span style="cursor:*">text or other element</span>
```

 [* ]can be replaced by the following properties.
 
 |property|instruction|
 |--|--|
 |crosshair;|The cursor render as a crosshair|
|cursor: pointer; cursor: hand;|The cursor render as a pointer (a hand) that indicates a link. IE5 explorer only recognize hand|
|cursor: wait;|The cursor indicates that the program is busy (often a watch or an hourglass)|
|cursor: help;|The cursor indicates that help is available (often a question mark or a balloon)
|cursor: no-drop; cursor: text;|The cursor indicates text|
|cursor: move;|The cursor indicates something that should be moved|
|cursor: n-resize;|The cursor indicates that an edge of a box is to be moved up (north)|
|cursor: s-resize;|The cursor indicates that an edge of a box is to be moved down (south)|
|cursor: e-resize;|The cursor indicates that an edge of a box is to be moved right (east)|
|cursor: w-resize;|The cursor indicates that an edge of a box is to be moved left (west)|
|cursor: ne-resize;|The cursor indicates that an edge of a box is to be moved up and right (north/east)|
|cursor: nw-resize;|The cursor indicates that an edge of a box is to be moved up and left (north/west)|
|cursor: se-resize;|The cursor indicates that an edge of a box is to be moved down and right (south/east)|
|cursor: sw-resize;|The cursor indicates that an edge of a box is to be moved down and left (south/west)|
|cursor: auto;|The browser sets a cursor|
|cursor:not-allowed;|cursor:not-allowed;|
|cursor: progress; cursor: default;|The default cursor (often an arrow)|
|cursor: url(' # ');|The url of a custom cursor to be used. Note: Always define a generic cursor at the end of the list in case none of the url-defined cursors can be used|

## Example
Here is an example to set a custom icon. If one imports local files, the ‘.cur’ format is better.
 ```javascript
 <style>
		body {
			cursor: url(https://github.com/LydiaCShaw/LydiaShaw.github.io/blob/gh-pages/cur2.png?raw=true),auto;
		}
	</style>
```
script
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>cursor change</title>
<script>
function displayResult(){
    document.getElementById("p1").style.cursor="pointer";
}
</script>
</head>
<body>

<p id="p1">across this text</p>
<br>
<button type="button" onclick="displayResult()">change cursor property</button>

</body>
</html>

```





