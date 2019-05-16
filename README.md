# xmlparsing

> XML解析器，支持布尔属性、自结束标签元素、保持元素属性。

## 安装

```shell
npm i xmlparsing
```

## 使用

```js
import { parser, generator} from 'xmlparsing'

// parse
const xmlDocument = parser.parse('<hello class="red"></hello>');

// firstChild
const helloElement = xmlDocument.firstChild;

// tagName
console.info(helloElement.tagName); // hello

// getAttribute
console.info(helloElement.getAttribute('class')); // red;

helloElement.setAttribute('class', 'green');

// generate
generator.generate(xmlDocument); // <hello class="green"></hello>
```

## 元素类型

* Document
* Element
* Fragment
* Text
* Comment
* Cdata

## 属性

### nodeType

类型：string

节点类型：document、element、fragment、text、comment、cdata 类型


### nodeValue string | null

类型：string | null

节点值：Text节点、Comment节点、Cdata节点的文本内容，其他节点的nodeValue为null


### children [Node]

所有子节点数组


### parentNode

父节点

### previousSibling

前一个兄弟节点

### previousElementSibling

前一个兄弟元素节点

### nextSibling

后一个兄弟节点


### nextElementSibling

后一个兄弟元素节点


### firstChild

第一个子节点


### lastChild

最后一个子节点


### outerXML

节点字符串文本

### innerXML

所有子节点的字符串文本

## 方法

### getAttribute(attributName)
说明：获取属性值

参数：attributeName 属性名

```js
// <div class="hello" />
node.getAttribute('class'); // 'hello'
```

### setAttribute(attributeName, newValue)

说明： 设置属性值

参数： attributeName 属性名， newValue 属性值

```js
// <div class="hello" />
node.getAttribute('class', 'green');
node.getAttribute('id', 'abc'); // <div class="green" id="abc"></div>

```

### removeAttribute(attributeName)

说明： 删除节点属性

参数： attributeName

```js
// <div class="hello" />
node.removeAttribute('class');
node.getAttribute('id', 'abc'); // <div></div>
```

### hasAttribute

说明： 判断节点是否有纯在的属性

参数： attributeName

```js
// <div class="hello" />
node.removeAttribute('class');
node.getAttribute('id', 'abc'); // <div></div>
```

### appendChild

### insertBefore

### insertAfter

### before

### after

### removeChild

### replaceWith

### remove

### empty

### cloneNode

### toString

### getElementsByTagName

### createElement

### createComment

### createTextNode

### createFragment