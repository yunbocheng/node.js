# Node.js
##  1. Node.js 概念

### 1.1 Node.js是什么

-  Node.js不是一门语言。
- Node.js不是一个库、不是框架。
- Node.js是一个JavaScript运行时环境。
- 简单点来讲就是 Node.js 可以解析和执行JavaScript代码。
- 以前只有浏览器可以解析和执行JavaScript代码。
- 也就是说：现在的JavaScript完全脱离浏览器来运行，一切都归公于Node.js

### 1.2 浏览器中的JavaScript

- EcmaScript（基础语法、if、var、function、Object、Array）
- DOM
- BOM

### 1.3 Node.js中的JavaScript

- 没有DOM、BOM对象，因为在服务端 不处理业务。
- 存在 EcmaScript。
- 在Node这个JavaScript执行环境中为 JavaScript提供了一些服务器级别的操作 API
  - 文件读写。
  - 网络服务的构建
  - 网络通信
  - http服务器

### 1.4 Node.js中Script与浏览器中的Script的区别

- 在Node.js中不存在DOM、BOM对象，只是存在EcmaScript基础语法。所以不存在getElemetById等方法。Node.js中使用的基本语法和JavaScript中的语法是一样的。只是在原有语法的基础之上增加了一些服务器级别的操作API。

### 1.5 Node.js的特性

- event-driven : 事件驱动
- non-blocking I/O model ：非阻塞IO模型(异步)
- lightweight and efficient : 轻量和高效

**JavaScript引擎是一个专门处理JavaScript脚本的虚拟机，一般会附带在网页浏览器之中。**

