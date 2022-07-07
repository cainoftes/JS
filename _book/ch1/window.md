# window

+ 所有浏览器都支持
+ 表示浏览器的窗口（和 Windows 操作系统没有任何关系）
+ JS 全局对象、函数、变量自动成为该对象的成员
+ HTML DOM 的 document 也是 window 对象的属性之一

### 窗口位置

以下单位都是 CSS 像素

```js
window.screenLeft // 相对于屏幕左侧的位置
window.screenTop // 相对于屏幕顶部的位置
window.moveTo(x,y) // 左上角移动到 (x, y)坐标
window.moveBy(cx, cy) // 左上角移动到(x + cx, y + cy) 坐标
```

### 窗口大小

```javascript
window.innerHeight
window.outerHeight
window.innerWidth
window.outerWidth
window.resizeTo(w, h) // 设置到 w,h
window.resizeBy(cw, ch) // 设置为 w + cw, h + ch
```

## 视口位置

```
window.scollX = window.pageXoffset
window.scollY = window.pageYoffset
window.scollBy(100, 200)
window.scollTo(0, 0)
```

## 导航与打开新窗口

### window.open()

+ 带有四个参数

+ 可以获取返回值，然后使用 返回对象.close()关闭打开的窗口

+ 第一个参数：要加载的URL

+ 第二个参数：目标窗口

  + 也就是想在那个窗口中打开 URL，如果不存在会新建然后命名
  + 可以是一个特殊的名字，例如 _self _parent _top _blank

+ 第三个参数：特性字符串，用于指定新窗口的配置；

  + 如果没有传入第三个参数，则所有特性都是默认的
  + 如果没有打开新窗口，则忽略第三个参数
  + 特性字符串用逗号分割


  | 设置       | 值         | 说明                     |
  | ---------- | ---------- | ------------------------ |
  | fullscreen | "yes" "no" | 是否最大化窗口，仅IE支持 |
  | height     | 数值       | 不能小于100              |
  | width      | 数值       | 不能小于100              |
  | left       | 数值       | x 坐标，非负             |
  | top        | 数值       | y 坐标，非负             |
  | location   | "yes" "no" | 是否显示地址栏           |
  | Menubar    | "yes" "no" | 是否显示菜单栏，默认 no  |
  | resizeable | "yes" "no" |            -              |
  | scrollbars | "yes" "no" |             -             |
  | status     | "yes" "no" |              -            |
  | toolbar    | "yes" "no" |               -           |
  

## 系统对话框

1. alert() ：接受一个字符串，只有一个 OK 按钮
2. confirm()：
3. prompt()
