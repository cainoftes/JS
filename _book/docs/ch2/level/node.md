# Node

> 所有的节点类型都继承 Node 类型

## 类型

Node 有一个 nodeType 属性，表示该节点的类型，由12个常量表示

1. Node.element_node
2. Node.attribute_node
3. Node.text_node
4. Node.cdata_section_node
5. Node.entity_reference_node
6. Node.entity_node
7. Node.processing_instruction_node
8. Node.comment_node
9. Node.document_node
10. Node.document_type_node
11. Node.document_fragment_node
12. Node.notation_node

## 节点关系

一个文档中的任意两个节点之间都是有关系的（妙哇）

这些节点可以看作来自同一个家族，这个家族有一个族谱（DOM 树）

## 属性

### childNodes

这个属性是一个 NodeList 对象，NodeList 并不是 Array 的实例，但是可以使用中括号访问值，而且它 还有 length 属性。实际上，NodeList 是对 DOM 结构的动态查询，会实时变化，而不是一个快照。

```js
someNode.childNodes[1]
someNode.childNodes.items(1)
count = someNode.childNodes.length
someNode.firstChild // 指向子节点的第一个节点，如果没有则为 null
someNode.lastChild // 指向子节点的最后一个节点，如果没有则为 null
someNode.hasChildNodes() // 是否有一个子节点
```

### parentNode

指向父节点。同一个 NodeList 中的节点有一个 parentNode ， 实际上，可以在同一个 NodeList 中的元素之间跳转。

```js
someNode.previousSibling // 前一个节点，如果没有则为 null
someNode.nextSibling    // 后一个节点，如果没有则为 null
```

## 操纵节点

### appendChild()

在 childNodes 结尾添加一个节点，并且返回新添加的节点，同时更新 DOM。

如果传入的节点是一个已经存在于 DOM 树中的节点，则将该节点移动。

### insertBefore()

传入两个参数，要插入的节点和要插入的位置（插入节点的后一个位置，如果为null，则和appendChild的功能相同）

### replaceChild()

传入两个参数，要插入的节点和要删除的节点，会将要删除的节点替换为要插入的节点。

### removeChild()

传入一个参数，将该节点从 DOM 中删除

## 别的方法

### cloneNode()

传入一个布尔值表示是否进行深复制，返回复制的节点。这个返回的节点属于文档所有，但是是一个孤儿节点（没有指定父节点）

> 不会复制 JS，例如事件
