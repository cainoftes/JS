# location

+ window.location 和 document.location 指向同一个对象
+ 保存当前加载文档的信息
+ 保存着把 URL 解析为离散片段后能够通过属性访问的信息

## 属性

```js
location.hash
location.host
location.hostname
location.href
location.pathname
locaiton.port
locaiton.protocol
location.search
location.username
location.password
location.origin
```

## 修改地址

+ 直接导航到另一个 URL

  ```javascript
  location.assign(URL)
  window.location = URL
  location.href = URL
  ```

+ 通过修改 location 属性微调 URL

  ```
  location.hostname = "www.bilibili.com"
  ```

+ 通过 location.replace(URL) 修改，区别是该方法导航到新URL之后后退按钮不可用
+ 通过 location.reload()修改，这个方法会以最有效的方法重新加载页面，例如从缓存中读取，如果想要强制从服务器读取，应该使用 location.reload(true)
