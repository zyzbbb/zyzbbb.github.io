---
title:"How to storage data on brower"
output:pdf_document
---

# Web Storage

## document.cookie

cookie 是最常用的存储数据的方式

```javascript
const cookie = document.cookie;
```

## window.sessionStorage

```javascript
sessionStorage.setItem("myCat", "Tom");
const myCat = sessionStorage.getItem("myCat");
```

sessionStorage 属性允许你访问一个，对应当前源的 session Storage 对象。它与 localStorage 相似，不同之处在于 localStorage 里面存储的数据没有过期时间设置，而存储在 sessionStorage 里面的数据在页面会话结束时会被清除。

- 页面会话在浏览器打开期间一直保持，并且重新加载或恢复页面仍会保持原来的页面会话。
- 在新标签或窗口打开一个页面时会复制顶级浏览会话的上下文作为新会话的上下文，这点和 session cookies 的运行方式不同。
- 打开多个相同的 URL 的 Tabs 页面，会创建各自的 sessionStorage。
- 关闭对应浏览器标签或窗口，会清除对应的 sessionStorage。

## window.localStorage

```javascript
sessionStorage.setItem("myCat", "Tom");
const myCat = sessionStorage.getItem("myCat");
```

应注意，无论数据存储在 localStorage 还是 sessionStorage ，它们都特定于页面的协议。

另外，localStorage 中的键值对总是以字符串的形式存储。 (需要注意，和 js 对象相比，键值对总是以字符串的形式存储意味着数值类型会自动转化为字符串类型).

## window.indexedDB

IndexedDB 是一种底层 API，用于在客户端存储大量的结构化数据（也包括文件/二进制大型对象（blobs））。该 API 使用索引实现对数据的高性能搜索。虽然 Web Storage 在存储较少量的数据很有用，但对于存储更大量的结构化数据来说力不从心。而 IndexedDB 提供了这种场景的解决方案。

```javascript
const dbVersion = 1;
const indexedDB = window.indexedDB.open("test", dbVersion);
```

## window.Cache

```javascript
const cache = new Cache();
```

## window.sessionStorage & window.localStorage 容量限制

| Browser        | localStorage | sessionStorage |
| -------------- | ------------ | -------------- |
| Mac Chrome     | 约 5M        | 约 5M          |
| Win Chrome     | -            | -              |
| IOS WeChat     | 约 2.5M      | 大于 10M       |
| Android WeChat | -            | -              |
| Mac Safria     | 约 2.5M      | 大于 10M       |
