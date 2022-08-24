---
theme: juejin
highlight: tomorrow
---

大家好我是牛哥，一枚前端程序员。虽然从事前端开发，但我个人觉得想要长期端稳程序员这碗饭，光会前端是不够的(业内大佬除外)，编程行业的生命周期可以总结为：程序员（前端/后端）->工程师（全栈）->研发架构师（IT+DT）->解决方案架构师（IT+DT+商业）->CTO->创业者，用年龄划分：30岁之前死磕技术，技术为王。30岁之后想要摆脱中年危机比较好的办法就是转变思维由技术到管理/自主创业。

由此可看出，想要在互联网行业有所成就且长存不倒，要学的东西太多太多了其中包含：前端、后端、大数据、产品、运营、架构....，可能有些小伙伴看到是不是有点劝退了，就单纯把其中一个点单独拎出来都够喝一壶了。我个人理解只要把自己从事的这个行业学精，再去学习其他技术就不会那么难了，有很多东西是触类旁通的，编程语言这东西在创立之初多少都会互相借鉴，只是不同的语言他的适用场景不同罢了。

可能有人会疑惑了，我一个干前端的学习什么后端，一个搞后端的学什么前端。从事前端的小伙伴学习了后端不一定要从事后端，后端学习了前端不一定要从事后端。但是想要晋升管理是要求综合技能过关，这样才能即管的了后端又管的了前端。那可能又有小伙伴疑问为什么要学习产品运营，可以这么说，不懂产品的程序员不是一个好的程序员，产品在我们日常开发中时时刻刻都在。前端后端都会了+产品运营这样就可以晋升产品+研发+运营的高级管理。下来我们回归到技术，技术就像习武之人的基本功，只有基本功扎实，才有能力去练降龙十八掌、罗汉拳这些武功。让我们一起努力练功升级把！💪💪💪

实时同步更新可以到我[github](https://github.com/xiaoniuge36/ng-learning-for-1024-days)（这里shaw）
# Day1【2022年7月23日】
**学习重点**：回顾前端基础知识，复习JavaScript基础之回顾JS组成（ECMAScript、DOM、BOM）。
## 1.前端技术回顾


在前端有我们熟悉的三架马车HTML+CSS+JavaScript

HTML
> 超**文本标记语言**或**HTML是设计用于在**[Web 浏览器](https://en.wikipedia.org/wiki/Web_browser "Web browser")中显示的文档的标准[标记语言](https://en.wikipedia.org/wiki/Markup_language "标记语言")。它可以通过[级联样式表](https://en.wikipedia.org/wiki/Cascading_Style_Sheets "Cascading Style Sheets")(CSS) 等技术和 JavaScript 等脚本[语言](https://en.wikipedia.org/wiki/JavaScript "JavaScript")[来](https://en.wikipedia.org/wiki/Scripting_language "Scripting language")辅助。[](https://en.wikipedia.org/wiki/Web_browser "网页浏览器")[](https://en.wikipedia.org/wiki/Cascading_Style_Sheets "层叠样式表")[](https://en.wikipedia.org/wiki/Scripting_language "脚本语言")[](https://en.wikipedia.org/wiki/JavaScript "JavaScript")
>  [Web 浏览器从](https://en.wikipedia.org/wiki/Web_browser "网页浏览器")[Web 服务器](https://en.wikipedia.org/wiki/Web_server "网络服务器")或本地存储接收 HTML 文档，并将文档[呈现](https://en.wikipedia.org/wiki/Browser_engine "浏览器引擎")为多媒体网页。[HTML 从语义](https://en.wikipedia.org/wiki/Semantic_Web "Semantic Web")上描述了[网页](https://en.wikipedia.org/wiki/Web_page "网页") 的结构，并且最初包含了文档外观的提示。

CSS
> CSS**层叠样式表**（英语：**C**ascading **S**tyle **S**heets，缩写：**CSS**；又称**串样式列表**、**级联样式表**、**串接样式表**、**阶层式样式表**）是一种用来为结构化文档（如[HTML](https://zh.wikipedia.org/wiki/HTML "HTML")文档或[XML](https://zh.wikipedia.org/wiki/XML "XML")应用）添加样式（字体、间距和颜色等）的[计算机语言](https://zh.wikipedia.org/wiki/%E8%AE%A1%E7%AE%97%E6%9C%BA%E8%AF%AD%E8%A8%80 "计算机语言")，由[W3C](https://zh.wikipedia.org/wiki/W3C "W3C")定义和维护。[CSS3](https://zh.wikipedia.org/wiki/%E5%B1%82%E5%8F%A0%E6%A0%B7%E5%BC%8F%E8%A1%A8#CSS3)现在已被大部分现代[浏览器](https://zh.wikipedia.org/wiki/%E7%80%8F%E8%A6%BD%E5%99%A8 "浏览器")支持，而下一版的[CSS4](https://zh.wikipedia.org/wiki/%E5%B1%82%E5%8F%A0%E6%A0%B7%E5%BC%8F%E8%A1%A8#CSS4)仍在开发中。

JavaScript

> **JavaScript**（通常缩写为**JS**）是一种[高级](https://zh.m.wikipedia.org/wiki/%E9%AB%98%E7%BA%A7%E8%AF%AD%E8%A8%80 "高级语言")的、[解释型](https://zh.m.wikipedia.org/wiki/%E7%9B%B4%E8%AD%AF%E8%AA%9E%E8%A8%80 "直譯語言")的[编程语言](https://zh.m.wikipedia.org/wiki/%E7%BC%96%E7%A8%8B%E8%AF%AD%E8%A8%80 "编程语言")[[8]](https://zh.m.wikipedia.org/zh/JavaScript#cite_note-:0-8)。JavaScript是一门[基于原型](https://zh.m.wikipedia.org/wiki/%E5%9F%BA%E4%BA%8E%E5%8E%9F%E5%9E%8B%E7%BC%96%E7%A8%8B "基于原型编程")、[头等函数](https://zh.m.wikipedia.org/wiki/%E5%A4%B4%E7%AD%89%E5%87%BD%E6%95%B0 "头等函数")的语言[[9]](https://zh.m.wikipedia.org/zh/JavaScript#cite_note-:1-9)，是一门多范式的语言，它支持[面向对象](https://zh.m.wikipedia.org/wiki/%E9%9D%A2%E5%90%91%E5%AF%B9%E8%B1%A1%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1 "面向对象程序设计")程式設計，[指令式编程](https://zh.m.wikipedia.org/wiki/%E6%8C%87%E4%BB%A4%E5%BC%8F%E7%BC%96%E7%A8%8B%E8%AF%AD%E8%A8%80 "指令式编程语言")，以及[函数式编程](https://zh.m.wikipedia.org/wiki/%E5%87%BD%E6%95%B0%E5%BC%8F%E7%BC%96%E7%A8%8B%E8%AF%AD%E8%A8%80 "函数式编程语言")。它提供语法来操控文本、[数组](https://zh.m.wikipedia.org/wiki/%E6%95%B0%E7%BB%84 "数组")、日期以及[正则表达式](https://zh.m.wikipedia.org/wiki/%E6%AD%A3%E5%88%99%E8%A1%A8%E8%BE%BE%E5%BC%8F "正则表达式")等，不支持[I/O](https://zh.m.wikipedia.org/wiki/I/O "I/O")，比如网络、存储和图形等，但这些都可以由它的宿主环境提供支持。它已经由[ECMA（欧洲电脑制造商协会）](https://zh.m.wikipedia.org/wiki/Ecma%E5%9B%BD%E9%99%85 "Ecma国际")通过[ECMAScript](https://zh.m.wikipedia.org/wiki/ECMAScript "ECMAScript")实现语言的标准化[[8]](https://zh.m.wikipedia.org/zh/JavaScript#cite_note-:0-8)。它被世界上的绝大多数网站所使用，也被世界主流[浏览器](https://zh.m.wikipedia.org/wiki/%E6%B5%8F%E8%A7%88%E5%99%A8 "浏览器")（[Chrome](https://zh.m.wikipedia.org/wiki/Google_Chrome "Google Chrome")、[IE](https://zh.m.wikipedia.org/wiki/Internet_Explorer "Internet Explorer")、[Firefox](https://zh.m.wikipedia.org/wiki/Firefox "Firefox")、[Safari](https://zh.m.wikipedia.org/wiki/Safari "Safari")、[Opera](https://zh.m.wikipedia.org/wiki/Opera%E9%9B%BB%E8%85%A6%E7%80%8F%E8%A6%BD%E5%99%A8 "Opera電腦瀏覽器")）支持。

如果把这三个与我们人做比较的话HTML可以比喻为骨骼，CSS可以比喻成我们所穿的衣服，JS则可以指挥人进行运动。前两者都不属于编程语言其中HTML 是一种用于定义内容结构的*标记语言*，CSS是一种样式语言一般用他为HTML添加样式。JS才算得上是编程语言，引用MDN对JS的解释————**JavaScript**（**JS**）是一种具有函数优先特性的轻量级、解释型或者说即时编译型的编程语言。JS可以说对前端非常重要，这门语言上手很快，但是要达到精通要花上很长事件，前端框架都是基于他进行开发的，像我们熟知的vue、react都是基于JS进行开发的。当然前两者也很重要，优先级的话是JS为主。而CSS而言想要学到工作中运用的水平并不难，但是要达到精通还是要花费一定的精力的，像CSS我们前端业内有比较牛的大佬-张鑫旭，著名的css三部曲就是由大佬出品，附上大佬的个人网站https://www.zhangxinxu.com/ 感兴趣的小伙伴可以看看。

## 2.JS组成部分
完整的JavaScript由ECMAScript（核心）、文档对象模型（DOM）、浏览器对象模型（BOM）三者组成，三者是并列关系。
### 2.1ECMAScript

> **ECMAScript**是一种由[Ecma国际](https://zh.wikipedia.org/wiki/Ecma%E5%9B%BD%E9%99%85 "Ecma国际")（前身为[欧洲计算机制造商协会](https://zh.wikipedia.org/wiki/%E6%AC%A7%E6%B4%B2%E8%AE%A1%E7%AE%97%E6%9C%BA%E5%88%B6%E9%80%A0%E5%95%86%E5%8D%8F%E4%BC%9A "欧洲计算机制造商协会")）在标准ECMA-262中定义的[脚本语言](https://zh.wikipedia.org/wiki/%E8%84%9A%E6%9C%AC%E8%AF%AD%E8%A8%80 "脚本语言")规范。这种语言在[万维网](https://zh.wikipedia.org/wiki/%E4%B8%87%E7%BB%B4%E7%BD%91 "万维网")上应用广泛，它往往被称为[JavaScript](https://zh.wikipedia.org/wiki/JavaScript "JavaScript")或[JScript](https://zh.wikipedia.org/wiki/JScript "JScript")，但实际上后两者是ECMA-262标准的实现和扩展。

ECMAScript每年都会更新JavaScript基于ECMAScript，而且每年都会更新标准。
最新标准于今年六月更新引用了Top-level Await,Object.hasOwn(),at(),error.case,正则表达式匹配人索引，类等新特性。

![微信图片_20220722160701.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/3410d584e99549d3b50f169fec08153a~tplv-k3u1fbpfcp-watermark.image?)
——官网https://www.ecma-international.org/


### 2.2DOM文档对象模型

> 文档对象模型 (DOM) 是 HTML 和 XML 文档的编程接口。它提供了对文档的结构化的表述，并定义了一种方式可以使从程序中对该结构进行访问，从而改变文档的结构，样式和内容。DOM 将文档解析为一个由节点和对象（包含属性和方法的对象）组成的结构集合。简言之，它会将 web 页面和脚本或程序语言连接起来。
> 
> 一个 web 页面是一个文档。这个文档可以在浏览器窗口或作为 HTML 源码显示出来。但上述两个情况中都是同一份文档。文档对象模型（DOM）提供了对同一份文档的另一种表现，存储和操作的方式。 DOM 是 web 页面的完全的面向对象表述，它能够使用如 JavaScript 等脚本语言进行修改。文档对象模型 (DOM) 将 web 页面与到脚本或编程语言连接起来。---MDN

DOM,是一种树形结构，DOM 通过创建表示文档的树，可以随心所欲地控制网页的内容和结构。使用 DOM API，可以轻松地删除、添加、替换、修改节点。

![微信图片_20220722163007.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/46ae99171e3d4f87899dfa416d00bf34~tplv-k3u1fbpfcp-watermark.image?)

#### 2.2.1document(文档)和element(元素)的关系
Document
> **`Document`** 接口表示任何在浏览器中载入的网页，并作为网页内容的入口，也就是[DOM 树](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Using_the_W3C_DOM_Level_1_Core)。DOM 树包含了像 [`<body>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/body) 、[`<table>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/table) 这样的元素，以及[大量其他元素](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element)。它向网页文档本身提供了全局操作功能，能解决如何获取页面的 URL ，如何在文档中创建一个新的元素这样的问题。---MDN。

在浏览器中，文档对象 document 是HTMLDocument 的实例（HTMLDocument 继承 Document），表示整个 HTML 页面。document 是 window对象的属性，因此是一个全局对象。一般来说，appendChild()、removeChild()和 replaceChild()方法不会用在 document 对象上。这是因为文档类型（如果存在）是只读的，而且只能有一个 Element 类型的子节点（即<html>，已经存在了）


Element

> **Element** 是一个通用性非常强的基类，所有 [Document](https://developer.mozilla.org/zh-CN/docs/Web/API/Document) 对象下的对象都继承自它。这个接口描述了所有相同种类的元素所普遍具有的方法和属性。`element` 对象实现了 DOM `Element` 接口以及更基本的 `Node` 接口
 
Element 类型就是Web开发中最常用的类型了。Element 表示XML或HTML元素，对外暴露出访问元素标签名、子节点和属性的能力。 
Document和Element*都继承自它的祖先接口 [Node](https://developer.mozilla.org/zh-CN/docs/Web/API/Node)*

```js
var element = document.createElement(tagName[, options]);
```

####  2.2.2总结常用的一些dom操作
```js
//返回一个匹配特定的元素
document.getElementById(id);
//返回一个包括所有给定标签名称的元素的 HTML 集合HTMLCollection 整个文件结构都会被搜索，包括根节点。返回的 HTML 集合是动态的，之后不用再调用会同步跟新
document.getElementsByTagName(name);
//方法用于创建一个由标签名称 `tagName` 指定的 HTML 元素。如果用户代理无法识别 `tagName`，则会生成一个未知 HTML 元素 HTMLUnknownElement。
document.createElement(name);
//返回文档中与指定选择器或选择器组匹配的第一个 Element对象。 如果找不到匹配项，则返回`null`。该方法按照深度优先遍历parentNode.appendChild(node)//方法将一个节点附加到指定父节点的子节点列表的末尾处。如果将被插入的节点已经存在于当前文档的文档树中，那么只会将它从原先的位置移动到新的位置（不需要事先移除要移动的节点）。
document.querySelector();
//设置一个html 可能会产生安全问题
element.innerHTML();
//返回与指定的选择器组匹配的文档中的元素列表 (使用深度优先的先序遍历文档的节点)。返回的是一个类数组对象的集合
Document.querySelectorAll();
//设置指定元素的属性值。如果属性已经存在，则更新值；否则将添加具有指定名称和值的新属性。
element.setAttribute();
//要获取属性的当前值
element.getAttribute();
```

**`Element.innerHTML`** 属性设置或获取 HTML 语法表示的元素的后代。
如果要向一个元素中插入一段 HTML，而不是替换它的内容，那么请使用 [`insertAdjacentHTML()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/insertAdjacentHTML "insertAdjacentHTML()") 方法。[`DOMString`](https://developer.mozilla.org/zh-CN/docs/conflicting/Web/JavaScript/Reference/Global_Objects/String_6fa58bba0570d663099f0ae7ae8883ab) 包含元素后代的 HTML 序列。设置元素的 `innerHTML` 将会删除所有该元素的后代并以上面给出的 htmlString 替代。
    
简单来说document是对文档/元素进行获取，只能获取不能修改，而element则对获取的元素/标签标签进行修改。

#### 2.2.3getElementById和querySelector区别
1.querySelector是按css规范来实现的，它传入的字符串中第一个字符不能是数字。
2.query选择符选出来的元素及元素数组是静态的，而getElement这种方法选出的元素是动态的。静态的就是说选出的所有元素的数组，不会随着文档操作而改变。在使用的时候getElement这种方法性能比较好，query选择符则比较方便。

#### 2.2.4 Document.querySelectorAll
```
elementList = parentNode.querySelectorAll(selectors);
```
> 返回与指定的选择器组匹配的文档中的元素列表 (使用深度优先的先序遍历文档的节点)。返回的对象是 [`NodeList`](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList) 。
>
> `NodeList` 对象是节点的集合，通常是由属性，如[`Node.childNodes`](https://developer.mozilla.org/zh-CN/docs/Web/API/Node/childNodes) 和 方法，如[`document.querySelectorAll`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll) 返回的。
> `NodeList` **不是一个数组**，是一个类似数组的对象 (*Like Array Object*)。虽然 `NodeList` 不是一个数组，但是可以使用 `forEach()` 来迭代。你还可以使用 [`Array.from()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/from) 将其转换为数组。 
> 不过，有些浏览器较为过时，没有实现 `NodeList.forEach()` 和 `Array.from()`。你可以用 [`Array.prototype.forEach()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) 来规避这一问题。请查看[该例](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList#example)。
在一些情况下，`NodeList` 是一个实时集合，也就是说，如果文档中的节点树发生变化，`NodeList` 也会随之变化。 详情请看[mdn](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll)
### 2.3BOM即浏览器对象模型

BOM即浏览器对象模型，它提供了独立于内容而与浏览器窗口进行交互的对象，其核心对象是 window。总体来说，BOM 主要针对浏览器窗口和子窗口（frame），不过一般会把任何特定于浏览器的操作都归在 BOM 的范畴内。虽然 ECMAScript 把浏览器对象模型（BOM）描述为 JavaScript 的核心，但实际上 BOM 是使用 JavaScript 开发 Web 应用程序的核心。

####  2.3.1window 对象一些操作

```js
//打开一个新窗口
window.open(); 
//关闭一个新窗口
window.close()；
// 把窗口移动到左上角
window.moveTo(0,0);
// 把窗口向下移动 100 像素
window.moveBy(0, 100); 
// 把窗口移动到坐标位置(200, 300)
window.moveTo(200, 300);
// 把窗口向左移动 50 像素
window.moveBy(-50, 0);
//警告框
window.alert();
//确认框
window.confirm()
```
#### 2.3.2定时器
我们常使用的定时器setTimeout()和setInterval()挂在在window下，它们主要的区别如下：setTimeout()用于指定在一定时间后执行某些代码，而 setInterval()用于指定
每隔一段时间执行某些代码。用法：
```js
// 在 1 秒后显示警告框
let timeoutIdTi = setTimeout(() => alert("Hello world!"), 10000);
//取消定时器
clearTimeout(timeoutIdTi);
// 在间隔 1 秒后显示警告框
let timeoutIdIn = setInterval(() => alert("Hello world!"), 1000);
//取消定时器
clearInterval(timeoutIdIn);
```
####  2.3.3location对象
> location 是最有用的 BOM 对象之一，提供了当前窗口中加载文档的信息，以及通常的导航功能。
> 这个对象独特的地方在于，它既是 window 的属性，也是 document 的属性。也就是说，
> window.location 和 document.location 指向同一个对象。location 对象不仅保存着当前加载文
> 档的信息，也保存着把 URL 解析为离散片段后能够通过属性访问的信息。
> 

**常用API：**

```js
//包含块标识符的DOMString，开头有一个#。"#contents"
window.location.hash;
//服务器名及端口号："www.wrox.com:80"
window.location.host;
//服务器名:"www.wrox.com"
window.location.hostname;
//当前加载页面的完整 URL。location 的 toString()方法也返回这个值："http://www.wrox.com:80/WileyCDA/?q=javascript#contents"
window.location.href;
//URL 中的路径和（或）文件名:"/WileyCDA/"
window.location.pathname;
//请求的端口。如果 URL中没有端口，则返回空字符串:"80"
window.location.port;
//页面使用的协议。通常是"http:"或"https:":"http:"
window.location.protocol;
//URL 的查询字符串。这个字符串以问号开头:"?q=javascript"
window.location.search;
//域名前指定的用户名:"foouser"
window.location.username;
//域名前指定的密码:"barpassword"
window.location.password;
//URL 的源地址。只读:"http://www.wrox.com"
window.location.origin;

```
**路由实现方式：**
主要通过location.hash设置hash Url，也就是url的符号#后面的值。当哈希值发生变化时，不会向服务器请求发送数据，可以通过hashchange事件来监听hash的变化，实现相应的功能。

**hash模式需要注意的几个点**
-   散列值不会随请求发送到服务器
-   散列值会反映在浏览器url上
-   只修改浏览器的哈希部分，按下回车，浏览器不会发送任何请求给服务器，只会触发hashchange事件并且修改location.hash的值
-   html a标签，设置id锚点，点击触发时，浏览器会自动设置location.hash值，同时触发hashchange事件，url上也会反映这一变化
-   hash模式下，手动刷新页面不会向浏览器发送请求，不会触发hashchange事件，但是会触发load事件
####  2.3.4history 对象
> DOM [`window`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window) 对象通过 [`history`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/history "history") 对象提供了对浏览器的会话历史的访问 。它暴露了很多有用的方法和属性，允许你在用户浏览历史中向前和向后跳转，同时——从 HTML5 开始——提供了对 history 栈中内容的操作。它表示当前窗口首次使用以来用户的导航历史记录。因为 history 是 window 的属性，所以每个 window 都有自己的 history 对象。出于安全考虑，这个对象不会暴露用户访问过的 URL，但可以通过它在不知道实际 URL 的情况下前进和后退。

**常用API**：
```js
//返回历史记录中的网页数量
window.history.length;
//前进
window.history.forward();
//后退
window.history.back();
//前往相对于自身的第num个(前后取决于正负)页面
window.history.go(num);
//history堆栈最上层的状态值
window.history.state;
//向当前历史记录插入一个状态值对象stateObj,并在网址后面添加url,title无实际意义
window.history.pushState(stateObj,title,url);
//实现
//const state = { 'page_id': 1, 'user_id': 5 }
//const url = 'hello-world.html'
//history.pushState(state, '', url)
//修改history对象的当前记录
window.history.replaceState(stateObj,title,url);
//原生用法
window.onpopstate = function(event) {
  alert(`location: ${document.location}, state: ${JSON.stringify(event.state)}`)
}

history.pushState({page: 1}, "title 1", "?page=1")
history.pushState({page: 2}, "title 2", "?page=2")
history.replaceState({page: 3}, "title 3", "?page=3")
history.back() // alerts "location: http://example.com/example.html?page=1, state: {"page":1}"
history.back() // alerts "location: http://example.com/example.html, state: null"
history.go(2)  // alerts "location: http://example.com/example.html?page=3, state: {"page":3}"

```

**history实现路由**

主要通过history.pushState/replceState向当前历史记录中插入状态对象state,在浏览器前进、回退、跳转等动作发生时触发popState事件，此时可以通过解析popState事件回调函数的event参数中的state对象，或者解析当前页面url来实现路由。\
**建议解析url方式实现路由。如果没有在页面首次加载的时候设置pushState/replaceState，那么首页一般是没有state对象的，在执行浏览器动作时，如果回退到首页，那么当前history对象的state属性不存在，导致解析state报错**


补充：
**popstate 事件**
每当活动的历史发生变化时，`popstate`事件条目被提交给窗口对象。记录当前活动的历史记录项是被`pushState`创建的，或者如果是由`replaceState`改变的，那么`popstate`事件的状态属性`state`会包含一个当前历史记录状态对象的拷贝



#### 2.3.5两种路由方式的差异以及需要注意的点

**方式的异同**

-   页面手动刷新，hash模式不会向服务器发送请求，history模式会， 后者会导致404问题，需要后端配置，或者开启NGINX配置
-   hash模式下url中的哈希值不会发送到服务器，history模式url全部会发送至服务器
-   设置location.hash和pushState都不会导致浏览器刷新
-   设置location.hash的时候会触发hashchange事件和popstate事件
-   仅当pushState函数设置url参数的值为hash格式时,浏览器动作发生会触发hashchange事件，尽管location.hash值为空
-   a标签锚点跳转可以设置hash，触发hashchange事件

**pushState设置跨域请求**

如果pushState的url为跨域网址，那么会报错.这样设计的目的是防止恶意代码让用户以为他们是在另一个网站上。

前端路由的本质为url改变页面不刷新、达到视图数据改变的结果。
以上就是前端路由的两种模式，至于在vue,react 框架中的路由封装基本原理都是基于这两个模式、但是它们在路由中又封装了动画等一系列的东西、显得比较复杂。

**其他的一些window对象**

navigator 对象，提供关于浏览器的详尽信息；  

location 对象，提供浏览器加载页面的详尽信息；

screen 对象，提供关于用户屏幕分辨率的详尽信息；

performance 对象，提供浏览器内存占用、导航行为和时间统计的详尽信息。
##  3.今日精进
学习解决方案架构师13讲。

原则定义-架构原则-原则质量-原则名称-理由依据-数据原则。
原则是说话或行事所依据的法则或标准，原则是客观、高度抽象、缓慢变化的。
知识压缩是一个人内核能力的体现，知识提炼是一种自我升华的过程。
企业原则是标准，架构原则决定产品走向，个人原则影响个人发展。

引用：提升自我认知，用自己的确定性对冲世界的不确定性。-马志峰



# Day2【2022年7月24日】
**学习重点**：复习HTML中的JS,js基础语法及关键字，基本数据类型

## 1.基础使用语法及关键字
### 1.1基本语法
JS语法创立之初借鉴了C语言/Java在语法上面会有相似性，JS语法在书写时候会区分大小写，Num和num是两个不同的变量。
JS中的一些运算总结

![2e3b10727661be3924998ccecd65dd8.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e7f9f8da04e641af8feb2b2a6195adae~tplv-k3u1fbpfcp-watermark.image?)
### 1.2.i++ 和 ++i 区别

i++和++i的意思是一样的，就是i = i + 1。当做运算符来说，就是a = i++ 和 a = ++i这样的形式，情况就不一样了。

a = i++的意思是，先把i的值赋给a，即a = i，再执行i = i + 1;a = ++i是先执行 i = i+1，再把i的值赋给a;如果一开始i=1。那么执行a=i++这条语句之后，a=1，i=2；那么执行a=++i这条语句之后，i=1，a=1；同理，i–和--i的用法也是一样的。
实例：
```js
//i++
i=1;
a = i++;
console.log(a);
console.log(i);
//1
// 2
//++i
i=1;
a = ++i;
console.log(a);
console.log(i);
//2
//2
```

**在循环体中的一些区别：**

for循环中,for(int i = 0;i < 3;i++)和for(int i = 0;i < 3;++i)效果一样

while(i++)是先用i的初始化值做循环变量再i+1

而while(++i)是先用i的初始值+1,再循环。
### 1.3=== 、 ==和Object.is()的区别
使用双等号（==）进行相等判断时，如果两边的类型不一致，则会进行强制类型转化后再进行比较。

使用三等号（===）进行相等判断时，如果两边的类型不一致时，不会做强制类型准换，直接返回 false。

使用 Object.is 来进行相等判断时，一般情况下和三等号的判断相同，它处理了一些特殊的情况，比如 -0 和 +0 判断为相等(===判断为相同)，两个 NaN 是相等的。

### 1.4常见的分支语句和循环遍历运算符
#### 1.4.1分支语句

![c5a6ec08b040f1f6ccce8b003477a31.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/f87ef43867724b058f4760afa8511f2f~tplv-k3u1fbpfcp-watermark.image?)

##### 1.4.1.1分支语句if分支结构有三种：

单分支结构

if..

多分支结构

if..else..

if..else if..else..
 
##### 1.4.1.2三元运算符：
 
 用法
 ```js
 //如果结果为真，则返回 value1，否则返回 value2。
var result = condition ? value1 : value2;

```
 
 ##### 1.4.1.3逻辑运算符
 
![6c331bc8d6f8e99db2de5f521870d95.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/efaf068b75bc40b685b60416b8153b60~tplv-k3u1fbpfcp-watermark.image?)

 ##### 1.4.1.4||运算符本质： 
 
![aa3b2112bb602a5572a34d54613dfc4.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/a27456bb64e34b0bb81607826800781f~tplv-k3u1fbpfcp-watermark.image?)
 
 
从左到右依次计算操作数。

处理每一个操作数时，都将其转化为布尔值（Boolean）；

如果结果是 true，就停止计算，返回这个操作数的初始值。

如果所有的操作数都被计算过（也就是，转换结果都是 false），则返回最后一个操作数。

**总结：一个或运算 || 的链，将返回第一个真值，如果不存在真值，就返回该链的最后一个值。**

**补充：** 
**如果||运算符与非布尔值一起使用，它将返回一个非布尔值。（忽略，不理解，有歧义）**
```js
console.log(true || null); // true
console.log(true || undefined); // true
console.log(true || 1); // true
console.log(true || ''); // true
console.log(false || ''); // ''
console.log(false || 'hello'); // 'hello'
console.log('hello' || false); // 'hello'
console.log('' || false); // false
console.log(true || "hello"); // true
console.log("hello" || true); // true
console.log(true || false); // true
console.log(true || true); // true
console.log('test' || 'hello'); // 'test'
console.log(null || 'hello'); // 'hello'
console.log(undefined || 'hello'); // 'hello'
console.log(1 || 'hello'); // 1
console.log('' || 'hello'); // 'hello'
console.log(false || 'hello'); // 'hello'
console.log([] ||false ); // []
console.log({} || false); // {}
```
##### 1.4.1.5&&运算符本质：

![1e7d83bc5493c0c5b75805797fb8d1a.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/da1735e477ba4526bbe4745c1b92dc72~tplv-k3u1fbpfcp-watermark.image?)

<img src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/add2f7d267724f479761058b43560719~tplv-k3u1fbpfcp-watermark.image?" alt="1659599075900.png" width="50%" />
从左到右依次计算操作数。

在处理每一个操作数时，都将其转化为布尔值（Boolean）；

如果结果是 false，就停止计算，并返回这个操作数的初始值（一般不需要获取到初始值）；

如果所有的操作数都被计算过（例如都是真值），则返回最后一个操作数。

**总结：与运算返回第一个假值，如果没有假值就返回最后一个值。**

**补充：** 
可以转换为 false 的表达式示例如下：

false;

null;

NaN;

0;

空字符串（""或''或``）；

undefined.

**举例：**
```js
console.log(true && null); // null
console.log(true && undefined); // undefined
console.log(true && 1); // 1
console.log(true && ''); // ''
console.log(false && ''); // false
console.log(false && 'hello'); // false
console.log('hello' && false); // false
console.log('' && false); // ''
console.log(true && "hello"); // "hello"
console.log("hello" && true); // true
console.log(true && false); // false
console.log(true && true); // true 
console.log('test' && 'hello'); // hello
console.log(null && 'hello'); // null
console.log(undefined && 'hello'); // undefined
console.log(1 && 'hello'); // hello
console.log('' && 'hello'); // ''
console.log(false && 'hello'); // false 
```
**优先级：**
数字越大优先级越高，说明&&的优先级大于||
<img src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7380c8413fcd4a409f70e7c0b6d060b2~tplv-k3u1fbpfcp-watermark.image?" alt="1659597163861.png" width="70%" />
```js
// &&优先级高于|| 
//&& 返回第一个假值 都为真返回最后一个值
//|| 返回第一个为真的值 如果都为假则返回最后一个值
let a = 1;
let b = 2;
let c = a && b; // 2
let y = a || b; // 1
console.log(c); // 2
let d = a || b;
console.log(d); // 1
let e = a && b || c;
console.log(e); // 2
let f = a || b && c;
console.log(f); // 1
let g = a || b || c;
console.log(g); // 1
let h = a && b && c;
console.log(h); // 2
let i = a && b && c || d;
console.log(i); // 2
```
在实际开发中最好两边都是逻辑判断空数组和字符串默认为true。
##### 1.4.1.6switch语句 
 
它是通过判断表达式的结果（或者变量）是否等于case语句的常量，来执行相应的分支体的；与if语句不同的是，switch语句只能做值的相等判断（使用全等运算符 ===），而if语句可以做值的范围判断。

**一些注意事项**
case穿透问题：
一条case语句结束后，会自动执行下一个case的语句；
这种现象被称之为case穿透；
break关键字
通过在每个case的代码块后添加break关键字来解决这个问题；
注意事项：这里的相等是严格相等,被比较的值必须是相同的类型才能进行匹配。

```js
 // 语法
    // switch (表达式/变量) {
    //   case 常量1:
    //     // 语句
    // }
 ```
 #### 1.4.2循环和遍历遍历运算符
 
 ##### 1.4.2.1while
 while 语句是一种先测试循环语句(先判断再执行)，即先检测退出条件，再执行循环体内的代码。语法如下：
 ```js
 //while循环
let i = 0;
while(i<10){
    console.log(i);
    i++;
}
//变量 i 从 0 开始，每次循环递增 1。只要 i 小于 10，循环就会继续。
 ```
##### 1.4.2.2do while
do...while语句创建一个执行指定语句的循环，直到`condition`值为 false。在执行`statement` 后检测`condition`，所以指定的`statement`至少执行一次。
```js
//模板
do
   statement
while (condition);
//用法
let b = 0;
do{
    console.log(i);
    i++;
}
```
##### 1.4.2.3 for
这也是一种先测试循环语句(先判断再执行)，比较常用,它有三个表达式组成，分别是声明循环变量、判断循环条件、更新循环变量。这三个表达式用分号分隔，都可以省略。但是中间的分号不能省略。其用法如下：
```js
//for循环
for(let i=0;i<10;i++){
    console.log(i);
}
```
for循环可以用来遍历数组，字符串，类数组，DOM节点等,不能用来遍历对象，对象无length的概念。

**结束循环的方式：**
```js
var arr = ['q','w','e','r','t'];
for(var i=0, len = arr.length ; i< len ; i++){
console.log(arr[i]);
}
//continue 跳出当前循环直接到下一个
// q , w , e , r , t

for(var i=0, len = arr.length ; i< len ; i++){
if(i == 2){
continue;
}
console.log(arr[i]);
}
// q , w , r , t

//breake结束判断后的循环
for(var i=0, len = arr.length ; i< len ; i++){
if(i == 2){
break;
}
console.log(arr[i]);
}
// q w
```
##### 1.4.2.4 for in 
> 以任意顺序迭代一个对象的除[Symbol](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)以外的[可枚举](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Enumerability_and_ownership_of_properties)属性，包括继承的可枚举属性。-mdn

官方的解释比较抽象一些我们可以这样理解：

可枚举可以理解为是否可以被遍历被列举出来，可枚举性决定了这个属性能否被for…in查找遍历到。
js中的基本包装类型的原型属性是不可枚举如：number,string,boolean。
在 JavaScript 中，基本类型是没有属性和方法的，但是为了便于操作基本类型的值，在调用基本类型的属性或方法时 JavaScript 会在后台隐式地将基本类型的值转换为对象。
包装类类型是针对number,string,boolean三种基本类型来说的三种基本类型,原则上只有值,没有对应的方法,或属性,但为了方便,咋们往往会直接调用一些,方法或属性,例如str.replace(),true.toString()等方法.这就是包装类带来的好处。
用法：

```js
//遍历数组
let arr = [1,2,3,4,5];
for(let item in arr){
    console.log(item);
}
// 0
// 1
// 2
// 3
// 4

//遍历对象
let obj = {
    name:'张三',
    age:18
}
for(let key in obj){
    console.log(key);
}
// name
// age
```
如果 for-in 循环要迭代的变量是 null 或 undefined，则不执行循环体。
for in 不仅会遍历当前的对象所有的可枚举属性，还会遍历其原型链上的可枚举属性。
其遍历数组返回的是每个元素对应的索引值，遍历对象返回的是键。
**结束循环的方式：**
```js
let arr = [1,2,3,4,5];
for(let item in arr){
    if(item>=2){
        continue;
    }
    console.log(item);
}
//0 1
let arr = [1,2,3,4,5];
for(let item in arr){
    if(item>=2){
        break;
    }
    console.log(item);
}
//0 1 
```
由此可以看出 for 和for in结束循环的方式相同


##### 1.4.2.5 for of 

for...of 语句创建一个循环来迭代可迭代的对象。在 ES6 中引入的 for...of 循环，以替代 for...in 和 forEach() ，并支持新的迭代协议。for...of 允许遍历 Arrays（数组）, Strings（字符串）, Maps（映射）, Sets（集合）等可迭代的数据结构等。

用法
```js
let arr = ['a', 'b', 'c', 'd'];

for (let a in arr) {
  console.log(a); // 0 1 2 3
}

for (let a of arr) {
  console.log(a); // a b c d
}
```
**注意：**

-   for…of适用遍历 **数组/ 类数组/字符串/map/set** 等拥有迭代器对象的集合
-   它可以正确响应break、continue和return语句。
-   for-of循环不支持遍历普通对象，因为没有迭代器对象。如果想要遍历一个对象的属性，可以用`for-in`循环
-   该方法只会遍历当前对象的属性，不会遍历其原型链上的属性。
-   for…of是作为ES6新增的遍历方式，允许遍历一个含有iterator接口的数据结构（数组、对象等）并且返回各项的值，普通的对象用for..of遍历是会报错的。

如果需要遍历的对象是类数组对象，用Array.from转成数组即可。
```js
let obj = {
    0:'one',
    1:'two',
    length: 2
};
obj = Array.from(obj);
for(var k of obj){
    console.log(k)
    //one
    // two
}
```
如果不是类数组对象，就给对象添加一个[Symbol.iterator]属性，并指向一个迭代器即可。
```js
//方法一：
var obj = {
    a:1,
    b:2,
    c:3
};

obj[Symbol.iterator] = function(){
    var keys = Object.keys(this);
    var count = 0;
    return {
        next(){
            if(count<keys.length){
                return {value: obj[keys[count++]],done:false};
            }else{
                return {value:undefined,done:true};
            }
        }
    }
};

for(var k of obj){
    console.log(k);
}


// 方法二
var obj = {
    a:1,
    b:2,
    c:3
};
obj[Symbol.iterator] = function*(){
    var keys = Object.keys(obj);
    for(var k of keys){
        yield [k,obj[k]]
    }
};

for(var [k,v] of obj){
    console.log(k,v);
}
```
跳出循环：
```js
var arr = ['a', 'b', 'c', 'd'];
for (let a of arr) {
  console.log(a); // a b c d
  if ( a === 'a') {
        break;  //跳出循环
   }
}
// a
var arr = ['a', 'b', 'c', 'd'];
for (let a of arr) {
  console.log(a); // a b c d
  if ( a === 'a') {
        continue;  //跳出循环
   }
}
// a  b c d
```
由此可见for of 跳出循环的方式与前两者一致
> for...in和for...of的区别
> for…of 是ES6新增的遍历方式，允许遍历一个含有iterator接口的数据结构（数组、对象等）并且返回各项的值，和ES3中的for…in的区别如下
> 
> -   for…of 遍历获取的是对象的键值，for…in 获取的是对象的键名；
> -   for… in 会遍历对象的整个原型链，性能非常差不推荐使用，而 for … of 只遍历当前对象不会遍历原型链；
> -   对于数组的遍历，for…in 会返回数组中所有可枚举的属性(包括原型链上可枚举的属性)，for…of 只返回数组的下标对应的属性值；

**总结：**for...in 循环主要是为了遍历对象而生，不适用于遍历数组；for...of 循环可以用来遍历数组、类数组对象，字符串、Set、Map 以及 Generator 对象。
##### 1.4.2.6 forEach() 
对数组每一项都运行传入的函数，没有返回值。
用法：
```js
//数组中的每个值都会调用回调函数，回调函数有三个参数：
//currentValue： 必需。当前元素
//index： 可选。当前元素的索引值。
//arr： 可选。当前元素所属的数组对象
let arr = [1,2,3,4,5]
arr.forEach((item, index, arr) => {
  console.log(index+":"+item)
})
// 0:1
// 1:2
// 2:3
// 3:4
// 4:5
//该方法还可以有第二个参数，用来绑定回调函数内部this变量（前提是回调函数不能是箭头函数，因为箭头函数没有this）
let arr = [1,2,3,4,5]
let arr1 = [9,8,7,6,5]
arr.forEach(function(item, index, arr){
  console.log(this[index])  //  9 8 7 6 5
}, arr1)

```
**forEach跳出循环的方式：**
```js
var arr = [1,3,5,7,9];
var id = 5;
try {
     arr.forEach(function (curItem, i) {
         if(curItem === 1) return;
         console.log(curItem)
         if (curItem === id) {
             throw Error();         //满足条件，跳出循环
         }
     })
 } catch (e) {
 }
 //3 5
```
> for和forEach的区别
> 
> foreach()不能使用break和continue这两个关键字，它实现break效果可以通过抛出异常的方式，实现continue的效果可以直接使用return。
> 
> forEach的优势就是，它传入的是一个回调函数，因此形成了一个作用域，它内部所定义的变量不会像for循环一样污染全局变量。
> 
**forEach()本身无法跳出循环，必须遍历所有的数据才能结束。**

forEach会改变原数组吗？
> 这些方法都不改变调用它们的数组。——js高级程序设计第四版是这么解释的

详细的可以看下这篇文章[# forEach到底可以改变原数组吗](https://blog.csdn.net/weixin_44628533/article/details/102495129)-->大致是说forEach会根据情况改变原数组。(forEach 的基本原理也是for循环，使用arr[index]的形式赋值改变，无论什么就都可以改变了。)

##### 1.4.2.7 map()

map() 方法会返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。该方法按照原始数组元素顺序依次处理元素。

注意： map() 不会对空数组进行检测，它会返回一个新数组，不会改变原始数组。

```js
//该方法的第一个参数为回调函数，他有三个参数：
//currentValue： 必须。当前元素的值
//index ：可选。当前元素的索引值
//arr ：可选。当前元素属于的数组对象
let arr13 = [3,2,4,1,4];
let arr14 = arr13.map(item=>item*2);
console.log(arr14);
// [6, 4, 8, 2, 8]
let arr = [1, 2, 3];
//链式调用
arr13.map(item => item+1).map(item => item+1)
// 返回值： [3, 4, 5]
//第二个参数用来绑定参数函数内部的this变量，可选：
 var arr = ['a', 'b', 'c']
[1, 2].map(function (e) {
    return this[e];
}, arr)
 // 返回值： ['b', 'c']
```
**终止循环**
```js
let arr = [1,2,3,4]  

// item：当前项，index：当前索引，arr：原数组

const result  = arr.map((item, index, arr)=> {      

if(item >2) {        

return item

      }  
  })    

console.log(result);
//[ undefined, undefined, 3, 4 ]
//return 不会终止循环(foreach 同理)

var arr = [1,3,5,7,9];
var id = 5;
try {
     arr.map(function (curItem, i) {
         if(curItem === 1) return;
         console.log(curItem)
         if (curItem === id) {
             throw Error();         //满足条件，跳出循环
         }
     })
 } catch (e) {
 }
 //3 5

```
**map和foreach一样无法跳出循环，只能通过抛出异常的方式结束循环。**
> **forEach和map方法有什么区别**
> 
> 这方法都是用来遍历数组的，两者区别如下：
> -   forEach()方法会针对每一个元素执行提供的函数，该方法没有返回值，是否会改变原数组取决于数组元素的类型是基本类型还是引用类型，详细解释可参考文章：[《forEach到底可以改变原数组吗》](https://blog.csdn.net/weixin_44628533/article/details/102495129)
> -   map()方法不会改变原数组的值，返回一个新数组，新数组中的值为原数组调用函数处理之后的值；

##### 1.4.2.8 filter()
对数组每一项都运行传入的函数，函数返回 true 的项会组成数组之后返回。用于过滤数组，满足条件的元素会被返回。它的参数是一个回调函数，所有数组元素依次执行该函数，返回结果为true的元素会被返回。该方法会返回一个新的数组，不会改变原数组。不符合条件的数组，可以用来删除或者替换。

```js
//该方法的第一个参数是回调函数，它有三个参数：
//currentValue： 必须。当前元素的值
//index ：可选。当前元素的索引值
//arr ：可选。当前元素属于的数组对象
let arr1 = [1, 2, 3, 4, 5]
arr1.filter(item => item > 2) 
// [3, 4, 5]
//同样，他也有第二个参数，用来绑定参数函数内部的this变量。
//实际运用

let arr2 = [1, undefined, 2, null, 3, false, '', 4, 0]
arr2.filter(Boolean)
// [1, 2, 3, 4]
```

##### 1.4.2.9 every()
every遍历数组中每一个元素是否能通过条件的测试返回bool值，对数组每一项都运行传入的函数，如果对每一项函数都返回 true，则这个方法返回 true。不改变调用它的数组。
```js
let arr21 = [3,2,4,1,4];
let arr22 = arr21.every(item=>item>2);
console.log(arr22);
//false
```

##### 1.4.2.10 some()
some遍历数组中有一个元素是否能通过条件的测试返回bool值,对数组每一项都运行传入的函数，如果有一项函数返回 true，则这个方法返回 true。不改变调用它的数组。
```js
let arr = [1, 2, 3, 4, 5]
arr.some(item => item > 4) 
// true
```
some()和every()方法都接受一个函数作为参数，该参数函数可以接收三个参数，分别是当前数组元素、当前元素索引、当前元素所在数组。
##### 1.4.2.11 find()
返回通过函数内判断的数组的第一个元素的值。该方法为数组中的每个元素都调用一次函数执行：
当数组中的元素在测试条件时返回 true 时， `find()` 返回符合条件的元素，之后的值不会再调用执行函数。

**注意:**  `find()` 对于空数组，函数是不会执行的。 该方法并没有改变数组的原始值。
如果没有符合条件的元素返回 undefined
```js
//该方法的第一个参数也是一个函数，它有三个参数：
//currentValue ：必需。当前元素
//index ：可选。当前元素的索引
//arr ：可选。当前元素所属的数组对象
let arr = [1, 2, 3, 4, 5]
arr.find(item => item > 2) 
//  3
```
##### 1.4.2.12 findIndex()
findIndex() 方法返回传入一个测试函数符合条件的数组第一个元素位置（索引）。该方法为数组中的每个元素都调用一次函数执行：

当数组中的元素在函数条件时返回 true 时， findIndex() 返回符合条件的元素的索引位置，之后的值不会再调用执行函数。
如果没有符合条件的元素返回 -1

**注意:**  `findIndex()` 对于空数组，函数是不会执行的。该方法并没有改变数组的原始值。
```js
//该方法的第一个参数也是一个函数，它有三个参数：
//currentValue ：必需。当前元素
//index ：可选。当前元素的索引
//arr ：可选。当前元素所属的数组对象
let arr = [1, 2, 3, 4, 5]
arr.findIndex(item => item > 2) 
//  2

```
find()返回第一个匹配的元素，findIndex()返回第一个匹配元素的索引。这两个方法也都接收第二个可选的参数，用于指定断言函数内部 this 的值。

##### 1.4.2.13 reduce()
reduce 为数组中的每一个元素依次执行回调函数，不包括数组中被删除或从未被赋值的元素，接受四个参数：初始值（或者上一次回调函数的返回值），当前元素值，当前索引，调用 reduce 的数组。
```js
//callback （执行数组中每个值的函数，包含四个参数）
//previousValue （上一次调用回调返回的值，或者是提供的初始值（initialValue））
//currentValue （数组中当前被处理的元素）
//index （当前元素在数组中的索引）
//array （调用 reduce 的数组）
//initialValue （作为第一次调用 callback 的第一个参数。）

var arr = [1, 2, 3, 4]
var sum = arr.reduce((prev, cur, index, arr) => {
    console.log(prev, cur, index);
    return prev + cur;
})
console.log(arr, sum);
//1 2 1
//3 3 3 2
//3 6 4 3
// [1, 2, 3, 4] 10
//加初始值
var arr = [1, 2, 3, 4]
var sum = arr.reduce((prev, cur, index, arr) => {
    console.log(prev, cur, index);
    return prev + cur;
}, 5)
console.log(arr, sum);

//3 5 1 0
//3 6 2 1
//3 8 3 2
//3 11 4 3
// [1, 2, 3, 4] 15
```
通过上面的两个例子，我们可以得出结论：如果没有提供initialValue，reduce 会从索引1的地方开始执行 callback 方法，跳过第一个索引。如果提供initialValue，从索引0开始

**注意**，该方法如果添加初始值，就会改变原数组，将这个初始值放在数组的最后一位。

reduce()方法从数组第一项开始遍历到最后一项。而 reduceRight()从最后一项开始遍历至第一项。
**终止循环**：
```js
reduce跳出循环
var arr = [1, 2, 3, 4];
var sum = arr.reduce((prev, cur, index, arr) => {
    console.log(prev, cur, index);
    if (index > 1) {
        throw new Error('error');
    }
    return prev + cur;
}
, 0)
console.log(arr, sum);

// [1, 2, 3, 4] 10;
```
由此可见reduce循环不可终止


##### 1.4.2.14循环的跳转控制
-  break: 直接跳出循环, 循环结束

-  break 某一条件满足时，退出循环，不再执行后续重复的代码

-  continue: 跳过本次循环次, 执行下一次循环体

-  continue 指令是 break 的“轻量版”。
-  continue 某一条件满足时，不执行后续重复的代码

总结：

![514fa1d67563347b70d2d5f19a2d9d3.png](https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/88ddae645e8c43e0978af2dbb1f72f07~tplv-k3u1fbpfcp-watermark.image?)

跳出循环详细情况可参考这篇文章-->[JS循环跳出方法](https://blog.csdn.net/qq_39370934/article/details/102870909?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-102870909-blog-124303375.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7ECTRLIST%7Edefault-1-102870909-blog-124303375.pc_relevant_default&utm_relevant_index=2)
 
 
 
 
 ### 1.5关键字
#### 1.5.1什么是关键字
关键字就是计算机中面向硬件的指令，简单的说就是方面用户和计算机进行交互的速记符，一般要求编程时用户定义的变量不能和关键字重名，否则程序运行出错。
#### 1.5.2JS的关键字
break do in typeof

case else instanceof var

catch export new void

class extends return while

const finally super with

continue for switch yield

debugger function this

default if throw

delete import try

## 2.JS基本数据类型(待完善)

Number

String
**属性： String.length** 该属性返回字符串中字符编码单元的数量。静态属性返回1，空字符串返回0.
```js
String.length
//1
''.length
//0
```
> JS 中的字符串是不可变的（immutable），意思是一旦创建，它们的值就不能变了。要修改
> 某个变量中的字符串值，必须先销毁原始的字符串，然后将包含新值的另一个字符串保存到该变量（创建一个新的字符串）。

Boolean

Undefined

Null

Object

BigInt

Symbol

共八种其中Symbol 和 BigInt 是ES6 中新增的数据类型。
其中 Symbol 和 BigInt 是ES6 中新增的数据类型：

> -   Symbol 代表创建后独一无二且不可变的数据类型，它主要是为了解决可能出现的全局变量冲突的问题。为了避免重名而被覆盖。
> -   BigInt 是一种数字类型的数据，它可以表示任意精度格式的整数，使用 BigInt 可以安全地存储和操作大整数，即使这个数已经超出了 Number 能够表示的安全整数范围。
> -   栈：原始数据类型（Undefined、Null、Boolean、Number、String、Symbol、BigInt）
> -   堆：引用数据类型（对象、数组和函数）
> 两种类型的区别在于**存储位置的不同：**
> -   原始数据类型直接存储在栈（stack）中的简单数据段，占据空间小、大小固定，属于被频繁使用数据，所以放入栈中存储；
> -   引用数据类型存储在堆（heap）中的对象，占据空间大、大小不固定。如果存储在栈中，将会影响程序运行的性能；引用数据类型在栈中存储了指针，该指针指向堆中该实体的起始地址。当解释器寻找引用值时，会首先检索其在栈中的地址，取得地址后从堆中获得实体。
> 
> 堆和栈的概念存在于数据结构和操作系统内存中，在数据结构中：
> 
> -   在数据结构中，栈中数据的存取方式为先进后出。
> -   堆是一个优先队列，是按优先级来进行排序的，优先级可以按照大小来规定。
> 
> 在操作系统中，内存被分为栈区和堆区：
> 
> -   栈区内存由编译器自动分配释放，存放函数的参数值，局部变量的值等。其操作方式类似于数据结构中的栈。
> -   堆区内存一般由开发者分配释放，若开发者不释放，程序结束时可能由垃圾回收机制回收。

## 3.今日精进
今天学习了华为布局物联网万亿赛道的商业思维模式。在车联网汽车智能化时代，华为选择造智能电动车的灵魂，而不造智能电动车的肉体。华为跟各大传统汽车厂商合作，帮助车企造车，把智能电动车烧钱多的三电系统交给传统车企去做。这类似于走谷歌安卓系统的路。华为一切都围绕着任正非布局的核心公司战略，从技术导向转向伸出导向。新能源汽车正在迅速崛起，新能源汽车比燃油车更加智能，汽车智能化是车联网未来的主战场。华为正围绕任正非制定的原则稳步前进，必将会引领一个围绕鸿蒙系统由车联网到手机、手表、汽车、智能家居一个全场景联动的万物互联新时代。

# Day3【2022年7月25日】
**学习重点**：判断数据类型的方法
## 1.Object.prototype.toString.call() 
使用 Object 对象的原型方法 toString 来判断数据类型：
**原理：**
> 为什么需要Object.prototype?
> 
> Object对象本身就有一个toString()方法，返回的是当前对象的字符串形式，原型上的toString()返回的才是我们真正需要的包含对象数据类型的字符串。
> 
> 为什么需要call？
> 
> 由于Object.prototype.toString()本身允许被修改，像Array、Boolean、Number的toString就被重写过，所以需要调用Object.prototype.toString.call(arg)来判断arg的类型，call将arg的上下文指向Object，所以arg执行了Object的toString方法。
> 
> 至于call，就是改变对象的this指向，当一个对象想调用另一个对象的方法，可以通过call或者apply改变其this指向，将其this指向拥有此方法的对象，就可以调用该方法了
[原文](https://blog.csdn.net/WCBandCTZ/article/details/115536202)

```js
function type(obj){
    return Object.prototype.toString.call(obj).slice(8,-1);
}
console.log(type('abc'));// String
console.log(type(123));//Number
console.log(type([1,2,3]));//Array
console.log(type(new Date()));//Date
console.log(type(function(){}));//Function
console.log(type(function(){this.name="22";}));//Function
console.log(type({name:"33"}));//Object
console.log(type(null));//Null
console.log(type(undefined));//Undefined
console.log(type(NaN));//Number
console.log(type(true));//Boolean
console.log(type(false));//Boolean
console.log(type(Symbol("name")));//Symbol
console.log(type(/^abc$/));//RegExp//正则
```
## 2.typeof 关键字：
其中数组、对象、null都会被判断为object，其他判断都正确。返回的是字符串
```js
console.log(typeof('abc'));//string
console.log(typeof(123));//Vnumber
console.log(typeof([1,2,3]));//object
console.log(typeof(new Date()));//object
console.log(typeof(function(){}));//function
console.log(typeof(function(){this.name="22";}));//function
console.log(typeof({name:"33"}));//object
console.log(typeof(null));//object
console.log(typeof(undefined));//undefined
console.log(typeof(NaN));//number
console.log(typeof(true));//boolean
console.log(typeof(false));//boolean
console.log(typeof(Symbol("name")));//symbol
console.log(typeof(/^abc$/));//object

```

## 3.instanceof 关键字：
instanceof可以正确判断对象的类型，其内部运行机制是判断在其原型链中能否找到该类型的原型。
instanceof**只能正确判断引用数据类型**，而不能判断基本数据类型。instanceof运算符可以用来测试一个对象在其原型链中是否存在一个构造函数的 prototype属性。返回Boolean值(基本类型返回false，引用类似返回true)
```js
console.log('abc' instanceof String);//false
console.log(123 instanceof Number);//false
console.log([1,2,3] instanceof Array);//true
console.log(new Date() instanceof Date);// true
console.log(function(){} instanceof Function);// true
console.log(function(){this.name="22";} instanceof Object);// true
console.log({name:"33"} instanceof Object);// true
console.log(NaN instanceof Number);// false
console.log(true instanceof Boolean);// false
console.log(false instanceof Boolean);// false
console.log(Symbol("name") instanceof Symbol);// false
console.log(/^abc$/ instanceof RegExp);// true
```

## 4.constructor 关键字：
constructor有两个作用，一是判断数据的类型，二是对象实例通过 constructor对象访问它的构造函数。需要注意，如果创建一个对象来改变它的原型，constructor就不能用来判断数据类型了：
```js
console.log(('abc').constructor === String);//true
console.log((123).constructor === Number);//true
console.log(([1,2,3]).constructor === Array);// true
console.log((new Date()).constructor === Date);//true
console.log((function(){}).constructor === Function);//true
console.log((function(){this.name="22";}).constructor === Object);// false
console.log(({name:"33"}).constructor === Object);// true
console.log((NaN).constructor === Number);// true
console.log((true).constructor === Boolean);// true
console.log((false).constructor === Boolean);// true
console.log((Symbol("name")).constructor === Symbol);// true
console.log((/^abc$/).constructor === RegExp);// true
```
改变原型
```js
function Fn(){};
 
Fn.prototype = new Array();
 
var f = new Fn();
 
console.log(f.constructor===Fn);    // false
console.log(f.constructor===Array); // true
```
## 5.今日精进
leetCode 2249. 统计圆内格点数目解题思维：根据公式 （x-y）**2 + (x+y)**2 = r**2  在x/ymin与x/ymax区间里面遍历查找符合的点count返回。

# Day4【2022年7月26日】
**学习重点**：执行上下文、作用域及闭包
## 1.执行上下文
> 执行上下文（以下简称“上下文”）的概念在 JavaScript 中是颇为重要的。变量或函数的上下文决定
> 、了它们可以访问哪些数据，以及它们的行为。每个上下文都有一个关联的变量对象（variable object），
> 而这个上下文中定义的所有变量和函数都存在于这个对象上。虽然无法通过代码访问变量对象，但后台
> 处理数据会用到它。

执行上下文可以理解为当前代码的执行环境，它会形成一个作用域。
### 1.1. 执行上下文类型类型

**（1）全局执行上下文**

任何不在函数内部的都是全局执行上下文，它首先会创建一个全局的window对象，并且设置this的值等于这个全局对象，一个程序中只有一个全局执行上下文。全局上下文就是我们常说的 window 对象，因此所有通过 var 定义的全局变量和函数都会成为 window 对象的属性和方法。
**组成：**
-   全局对象（浏览器里是 Window, Node 环境下是 Global）
-   this 变量。这里的 this ，指向的还是全局变量

**（2）函数执行上下文**

当一个函数被调用时，就会为该函数创建一个新的执行上下文，函数的上下文可以有任意多个。
**组成：**
-  函数上下文创建参数对象（arguments）；
-  this。动态的，如果它被一个引用对象调用，那么 this 就指向这个对象；否则，this 的值会被设置为全局对象或者 undefined（在严格模式下）

**（3）Eval 执行上下文**

执行在eval函数中的代码会有属于他自己的执行上下文，用的比较少了了解即可，跟面试官吹逼的时候可以用。

### 1.2. 执行上下文栈--执行上下文的管理

-   JavaScript引擎使用执行上下文栈来管理执行上下文
-   当JavaScript执行代码时，首先遇到全局代码，会创建一个全局执行上下文并且压入执行栈中，每当遇到一个函数调用，就会为该函数创建一个新的执行上下文并压入栈顶，引擎会执行位于执行上下文栈顶的函数，当函数执行完成之后，执行上下文从栈中弹出，继续执行下一个上下文。当所有的代码都执行完毕之后，从栈中弹出全局执行上下文。

```
function testA() {
        console.log('执行第一个测试函数的逻辑');
        testB();
        console.log('再次执行第一个测试函数的逻辑');
      }
      
      function testB() {
        console.log('执行第二个测试函数的逻辑');
      }
      
      testA();
//执行第一个测试函数的逻辑
//执行第二个测试函数的逻辑
//再次执行第一个测试函数的逻辑
```
执行顺序跟压入栈的顺序相反所以会先执行B-A-全局。
**特点：**
-   栈，先进后出
-   栈底永远是全局执行上下文环境window，其余的都是函数执行上下文
-   当前正在运行的永远是栈顶的执行上下文

### 1.3. 创建执行上下文

创建执行上下文有两个阶段：**创建阶段**和**执行阶段**

**1）创建阶段**

（1）this绑定

-   在全局执行上下文中，this指向全局对象（window对象）
-   在函数执行上下文中，this指向取决于函数如何调用。如果它被一个引用对象调用，那么 this 会被设置成那个对象，否则 this 的值被设置为全局对象或者 undefined

（2）创建词法环境组件

-   词法环境是一种有**标识符——变量映射**的数据结构，标识符是指变量/函数名，变量是对实际对象或原始数据的引用。
-   词法环境的内部有两个组件：**加粗样式**：环境记录器:用来储存变量个函数声明的实际位置**外部环境的引用**：可以访问父级作用域

（3）创建变量环境组件

-   变量环境也是一个词法环境，其环境记录器持有变量声明语句在执行上下文中创建的绑定关系。

**2）执行阶段**

此阶段会完成对变量的分配，最后执行完代码。

整个过程是一个动态的过程。

**简单来说执行上下文就是指：**

在执行一点JS代码之前，需要先解析代码。解析的时候会先创建一个全局执行上下文环境，先把代码中即将执行的变量、函数声明都拿出来，变量先赋值为undefined，函数先声明好可使用。这一步执行完了，才开始正式的执行程序。

-   全局上下文：变量定义，函数声明
-   函数上下文：变量定义，函数声明，`this`，`arguments`

在一个函数执行之前，也会创建一个函数执行上下文环境，跟全局执行上下文类似，不过函数执行上下文会多出this、arguments和函数的参数。上下文在其所有代码都执行完毕后会被销毁，包括定义在它上面的所有变量和函数（全局上下文在应用程序退出前才会被销毁，比如关闭网页或退出浏览器）。
## 2.作用域
### 2.1什么是作用域
编程语言最基本的能力都是**能够存储变量当中的值、并且允许我们对这个变量的值进行访问和修改**。那约定编程语言把变量放在那里，程序如何找到，怎么对变量进行存储访问变量的规则就叫**作用域**。一般情况作用域的时候，指的是这个规则约束下的一个变量、函数、标识符可以被访问的区域。就是能够储存变量当中的值，并且能在之后对这个 值进行访问或修改。**作用域分为三类：全局作用域、函数作用域、块级作用域（ES6后）。**
### 2.2全局作用域
#### 2.2.1声明在任何函数之外的顶层作用域的变量就是全局变量，这样的变量拥有全局作用域：
```js
var name = 'xiuyan'; // 全局作用域内的变量

// 函数作用域
function showName() {
    console.log(name);
}

// 块作用域
{
  name = 'BigBear'
}

showName(); // 输出 'BigBear'

window.name // 'BigBear'
```
**如果把 var改成let还会输出  'BigBear'吗？**
答案是会，但是不会挂在在window上，window.name 为空，说明声明的不是全局遍历，具体为什么会这样js高级程序设计已经给出解释了：
> 所有通过 var 定义的全局变量和函数都会成为 window 对象的属性和方法。使用 let 和 const 的顶级声明不会定义在全局上下文中，**但在作用域链解析上效果是一样的。**

#### 2.2.2 所有未定义直接赋值的变量自动声明为全局作用域(不推荐这么做，不规范)
```js
 function aa(){
    //报错  默认为函数内var声明的局部变量
    // var a =1;
    // a += 1;
    // a = a+1;
    // a++;
    //不报错，因为a是全局变量
    // a=1;
    console.log(a);
   }
    aa();
    console.log(a); 
```
### 2.2函数作用域
在函数内部定义的变量，拥有函数作用域，称为函数作用域。一般作用域是分层的，内层作用域可以访问外层作用域，反之不行。
```js
var name = 'xiuyan'; // name 是全局变量
function showName(myName) {
  // myName 是传入 showName 的局部变量
  console.log(myName);
}
function sayHello() {
  // hello 被定义成局部作用域变量
  var helloString = 'hello everyone';
  console.log(helloString);
}

showName(name); // 输出 'xiuyan'
sayHello(); // 输出 'hello everyone'
console.log(myName); // 抛出错误：myName 在全局作用域未定义
console.log(helloString); // 抛出错误：hello 在全局作用域未定义

{
  console.log(helloString, myName) // 抛出错误 
}
```
在这个例子里，myName 和 hello 都是在函数内部定义的变量，它们就被“画地为牢” ，作用域仅局限于函数内部。全局作用域和块作用域里都访问不到它们。

### 2.3块级作用域

使用ES6中新增的let和const指令可以声明块级作用域，块级作用域可以在函数中创建也可以在一个代码块中的创建（由`{ }`包裹的代码片段就称为块级作用域），let和const声明的变量不会有变量提升，也不可以重复声明，在循环中比较适合绑定块级作用域，这样就可以把声明的计数器变量限制在循环内部。
```js
{
    var a = 1;
    let b = 2;
}
console.log(a);//1
console.log(b);//报错 const同理
```
对于对象来说不是一个块级作用域如下箭头函数查找规则可看出。
```js
   var obj = {
    name: "obj",
    foo: () => {
        var bar = () => {
            console.log("bar:", this)
        }
        return bar

    }
}
var fn = obj.foo()
fn.apply("bbb")//window
```
可以看出，块作用域内的变量只要出了自己被定义的那个代码块，那么就无法访问了，而var没有块级作用域的概念。这点和函数作用域比较相似 —— 它们都只在“自己的地盘”上生效，所以它们也统称为” 局部作用域 “。

## 3.作用域链

> 在当前作用域中查找所需变量，但是该作用域没有这个变量，那这个变量就是自由变量。如果在自己作用域找不到该变量就去父级作用域查找，依次向上级作用域查找，直到访问到window对象就被终止，这一层层的关系就是作用域链。
> 
> 作用域链的作用是**保证对执行环境有权访问的所有变量和函数的有序访问，通过作用域链，可以访问到外层环境的变量和函数。**
> 
> 作用域链的本质上是一个指向变量对象的指针列表。变量对象是一个包含了执行环境中所有变量和函数的对象。作用域链的前端始终都是当前执行上下文的变量对象。全局执行上下文的变量对象（也就是全局对象）始终是作用域链的最后一个对象。当查找一个变量时，如果当前执行环境中没有找到，可以沿着作用域链向后查找。

**举例：**
```js
function addA(a) {
    console.log(a + b)
    console.log(c) // 报错
  }
  
  var b = 1
  
  addA(2) //3
```
关系示意图如下所示:

<img src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/80b1afda17184e5999acfaa25ff36e20~tplv-k3u1fbpfcp-watermark.image?" alt="1658822923526.png" width="50%" />

 addA 这个函数里访问变量 b 的时候，函数作用域内并没有对 b、c 这两个变量作定义，所以一开始肯定是找不到的。要想找到 b、c 去上层作用域（全局作用域找），找到了 b ，那么就可以直接拿来用了；没找到 c，并且全局作用域已经没有上层作用域了（头探不出去了），那就歇菜，报错！这就是上文“执行阶段 ”里我们描述的那个过程。在这个查找过程中，层层递进的作用域，就形成了一条作用域链。
 关系图如下：
 
<img src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/650a8f2db49341c29c9d90aa3db4ecb9~tplv-k3u1fbpfcp-watermark.image?" alt="1658823148965.png" width="50%" />

## 4.闭包
### 4.1什么是闭包？

**一个变量在函数中被使用，但它既不是函数参数、也不是函数的局部变量，而是一个不属于当前作用域的变量，此时它相对于当前作用域来说，就是一个自由变量**。**函数中引用了自由变量的函数，就叫闭包。**

简单来说：
**闭包是指有权访问另一个函数作用域中变量的函数**，创建闭包的最常见的方式就是在一个函数内创建另一个函数，创建的函数可以访问到当前函数的局部变量。

为了解决突破函数作用域的限制才有了闭包这种概念

### 4.2闭包的运用
#### (1) 模拟私有变量的实现
为什么要有私有变量：像有些比较敏感的信息如果定义在函数中可直接被访问是非常危险的，涉及到安全问题。在 JS 中，无法像java通过 private 这样的关键字直接在类里声明变量的私有性。

通过使用闭包，可以通过在外部调用闭包函数，从而在外部访问到函数内部的变量，可以使用这种方法来创建私有变量。

#### (2)偏函数与柯里化(持久保持)
**柯里化**
> 柯里化是把**接受 n 个参数的 1 个函数**改造为**只接受 1个参数的 n 个互相嵌套的函数**的过程。也就是 fn (a, b, c)fn(a,b,c) 会变成 fn (a)(b)(c)fn(a)(b)(c)。

```js

function generateName(prefix) {  
    return function(type) {
        return function (itemName) {
            return prefix + type + itemName
        }    
    }
}

// 生成大卖网商品名专属函数
var salesName = generateName('大卖网')

// “记住”prefix，生成大卖网母婴商品名专属函数
var salesBabyName = salesName('母婴')

// "记住“prefix和type，生成洗菜网生鲜商品名专属函数
var vegFreshName = generateName('洗菜网')('生鲜')

// 输出 '大卖网母婴奶瓶'
salesBabyName('奶瓶')
// 输出 '洗菜网生鲜菠菜'
vegFreshName('菠菜')

// 啥也不记，直接生成一个商品名
var itemFullName = generateName('洗菜网')('生鲜')('菠菜')
```
**偏函数**
原有的一次性传三个改造成先传一个参数在传两个参数
```js
  function generateName(prefix, type, itemName) {
    return prefix + type + itemName
}

// 调用时一口气传入3个入参
var itemFullName = generateName('大卖网', '母婴', '奶瓶')
```
改造后
```js
function generateName(prefix) {
    return function(type, itemName) {
        return prefix + type + itemName
    }
}

// 把3个参数分两部分传入
var itemFullName = generateName('大卖网')('母婴', '奶瓶')
```
**柯里化和偏函数的区别：**
柯里化是将一个 n 个参数的函数转换成 n 个单参数函数。你有 10 个入参，就得嵌套 10 层函数，且每层函数都只能有 1 个入参。它的目标就是把函数的入参拆解为精准的 n 部分。

偏函数应用相比之下就 “随意” 一些了。偏函数是说，固定你函数的某一个或几个参数，然后返回一个新的函数（这个函数用于接收剩下的参数）。你有 10 个入参，你可以只固定 2 个入参，然后返回一个需要 8 个入参的函数 —— 偏函数应用是不强调 “单参数” 这个概念的。它的目标仅仅是把函数的入参拆解为两部分。

### 4.2实例：
防抖节流是一种闭包的实际运用。（面试可提）
 ```js
 function addABC(){
    var a = 1,b = 2;
    
    function add(){
      return a+b+c;
    }
    return add;
  }
  
  var c = 3
  
  var globalAdd = addABC()
  
  console.log(globalAdd()) // 6
 ````
 面试的坑:
 下面代码输出什么
 ```js
   for (var i = 0; i < 5; i++) {
    setTimeout(function() {
        console.log(i);
    }, 1000);
}

console.log(i);
//5 5 5 5 5 5
 ```
 换成let
 ```js
 for (let i = 0; i < 5; i++) {
    setTimeout(function() {
        console.log(i);
    }, 1000);
}

console.log(i);
// Uncaught ReferenceError: i is not defined
// 0
// 1
// 2
// 3
// 4
 ```
 这个函数第一次被执行，也是 1000ms 以后的事情了(setTimeout异步)，此时它试图向外、向上层作用域（这里就是全局作用域）去找一个叫 i 的变量。此时 for 循环早已执行完毕， i 也进入了尘埃落定的最终状态 ——5。所以 1000ms 后，当这个函数第一次真正被执行的时候，引用到的 i 值已经是 5 了。

**改造方法：
第一种**

可以把 setTimeout 函数的第三个参数利用起来。setTimeout 从第三个入参位置开始往后，是可以传入无数个参数的。这些参数会作为回调函数的附加参数存在。
在这里我们可以把每一轮循环里 i 的值，存进 setTimout 的第三个参数里：
```js
for (var i = 0; i < 5; i++) {
    setTimeout(function(j) {
        console.log(j);
    }, 1000, i);
}
```
**第二种**

在 setTimeout 外面再套一层函数，利用这个外部函数的入参来缓存每一个循环中的 i 值：
```js
var output = function (i) {
    setTimeout(function() {
        console.log(i);
    }, 1000);
};

for (var i = 0; i < 5; i++) {
    // 这里的 i 被赋值给了 output 作用域内的变量 i
    output(i);  
}
```
**第三种**

 和第二种思路比较相似，同样是在 setTimeout 外面再套一层函数，只不过这个函数是一个**立即执行函数**。利用立即执行函数的入参来缓存每一个循环中的 i 值：
 ```js
 for (var i = 0; i < 5; i++) {
    // 这里的 i 被赋值给了立即执行函数作用域内的变量 j
    (function(j) {  
        setTimeout(function() {
            console.log(j);
        }, 1000);
    })(i);
}
 ```
 
 闭包的弊端
>  
>  1）由于闭包会使得函数中的变量都被保存在内存中，内存消耗很大，所以不能滥用闭包，否则会造成网页的性能问题，在IE中可能导致内存泄露。解决方法是，在退出函数之前，将不使用的局部变量全部删除。
> 
> 2）闭包会在父函数外部，改变父函数内部变量的值。所以，如果你把父函数当作对象（object）使用，把闭包当作它的公用方法（Public Method），把内部变量当作它的私有属性（private value），这时一定要小心，不要随便改变父函数内部变量的值。


## 5.今日精进
leetCode  剑指 Offer II 079. 所有子集（回溯算法解题）。

提升自己前要做好计划，合理安排时间，个人精力是有限的，抓住重点，做好笔记，定时复盘，最重要的是坚持。

# Day5【2022年7月27日】
**学习重点**：定义变量方式(var、let、const)
> js有 3 个关键字可以声明变量：var、const 和 let。其中，var 在
> ECMAScript 的所有版本中都可以使用，而 const 和 let 只能在 ECMAScript 6 (ES6)及更晚的版本中使用。

## 1.var
### 1.1作用域
var关键字用来声明变量时如果在函数中定义是函数作用域中的局部变量,数执行完的时候会销毁。在全局来定义变量是会挂载在window/global下的全局作用域中的全局变量。
示例如下
```js
function test() { 
 var message = "hi"; // 局部变量
} 
test(); 
console.log(message); // 出错！
```
这里定义的是一个局部作用域，调用之后变量随即被销毁，因此示例中的最后一行会导致错误。不过，在函数内定义变量时省略 var 操作符，可以创建一个全局变量（不推荐这么做，严格模式下会直接报错）：
```js
function test() {
message = "hi"; // 全局变量
}
test();
console.log(message); // "hi"

```
> 在严格模式下，不能定义名为 eval 和 arguments 的变量，否则会导致语法错误。

### 1.2.变量提升
> 从概念的字面意义上说，“变量提升”意味着变量和函数的声明会在物理层面移动到代码的最前面，但这么说并不准确。实际上变量和函数声明在代码里的位置是不会动的，而是在编译阶段被放入内存中。（）

> JavaScript 只会提升声明，不会提升其初始化。如果一个变量先被使用再被声明和赋值的话，使用时的值是 undefined。参见例子：

```js
console.log(num); // Returns undefine
var num;
num = 6;
//改造
console.log(num)
//如过只下下面其中一个
var num //提升
num //报错

//函数内
function foo() {
console.log(age);
var age = 26;
}
foo(); // undefined
```
函数内实际上js运行是看成下面的代码
```js
function foo() {
var age;
console.log(age);
age = 26;
}
foo(); // undefined
//这就是所谓的“提升”（hoist），也就是把所有变量声明都拉到函数作用域的顶部。
```
> var 声明会被拿到函数或全局作用域的顶部，位于作用域中所有代码之前。这个现象叫作“提升”
> （hoisting）。提升让同一作用域中的代码不必考虑变量是否已经声明就可以直接使用。可是在实践中，提
> 升也会导致合法却奇怪的现象，即在变量声明之前使用变量。在实际开发中还是要严谨一点少用这个属性，避免不必要的问题。

### 1.3.可重复定义变量
```js
function foo() {
var age = 16;
var age = 26;
var age = 36;
console.log(age)
}
foo(); // 36
```
示例方便理解：
```js
var x = 0; // x 是全局变量，并且赋值为 0

console.log(typeof z); // // undefined，因为 z 还不存在

function a() {
  var y = 2; // y 被声明成函数 a 作用域的变量，并且赋值为 2

  console.log(x, y); // 0 2

  function b() {
    x = 3; // 全局变量 x 被赋值为 3
    y = 4; // 已存在的外部函数的 y 变量被赋值为 4
    z = 5; // 创建新的全局变量 z，并且赋值为 5
           // (在严格模式下抛出 ReferenceError)
  }

  b(); // 调用 b 时创建了全局变量 z
  console.log(x, y, z); // 3 4 5
}

a(); // Also calls b.
console.log(x, z);     // 3 5
console.log(typeof y); // undefined，因为 y 是 a 函数的局部变量

```

## 2.let

> ES6 新增的 let 关键字跟 var 很相似，但它的作用域是块级的，这也是 JavaScript 中的新概念。块
> 级作用域由最近的一对包含花括号{}界定。换句话说，if 块、while 块、function 块，甚至连单独
> 的块也是 let 声明变量的作用域。最明显的区别是，let 声明的范围是块作用域，var 声明的是函数作用域。

验证var有没有块级作用域
```js
{
    var a =1;
    let b =2;
}
console.log(a);
console.log(b);
// 1
// Uncaught ReferenceError: b is not defined
```
### 2.1.作用域
let语句声明一个块级作用域的局部变量
实例
```js
if (true) { 
 let age = 26; 
 console.log(age); // 26 
} 
console.log(age);
// 26
// Uncaught ReferenceError: age is not defined
```
### 2.2.暂时性死区
一个实例可以说明什么是暂时性死区
```js
// name 会被提升
console.log(name); // undefined
var name = 'Matt';
// age 不会被提升
console.log(age); // ReferenceError：age 没有定义
let age = 26;
```
> 在解析代码时，JavaScript 引擎也会注意出现在块后面的 let 声明，只不过在此之前不能以任何方
> 式来引用未声明的变量。在 let 声明之前的执行瞬间被称为“暂时性死区”（temporal dead zone），在此
> 阶段引用任何后面才声明的变量都会抛出 ReferenceError。只可以在声明后使用。

### 2.3.不可重复定义
```js
let b =3;
let b =4;
// Uncaught SyntaxError: Identifier 'b' has already been declared
```
### 2.4.全局不挂载window

与 var 关键字不同，使用 let 在全局作用域中声明的变量不会成为 window 对象的属性（var 声明的变量则会）。
```js
var name = 'Matt';
console.log(window.name); // 'Matt'

let age = 26;
console.log(window.age); // undefined
```
let 的行为非常适合在循环中声明迭代变量。使用 var 声明的迭代变量会泄漏到循环外部，这种情况应该避免。
```js
for (var i = 0; i < 10; ++i) {}
console.log(i); // 10

for (let j = 0; j < 10; ++j) {}
console.log(j); // ReferenceError: j 没有定义
```

> 严格来讲，let 在 JavaScript 运行时中也会被提升，但由于“暂时性死区”（temporal dead zone）的缘故，实际上不能在声明之前使用 let 变量。因此，从写 JavaScript 代码的角度说，let 的提升跟 var是不一样的。

## 3.const
> const 的行为与 let 基本相同，唯一一个重要的区别是用它声明变量时必须同时初始化变量，且尝试修改 const 声明的变量会导致运行时错误。(常量的值是无法通过重新赋值改变的，也不能被重新声明。)声明的是一个内存地址值为不可改变的对象。

定义普通类型数据时，无法改变其值（最好大写定义），但是const定义引用型数据类型时，例如对象，可以修改它的值，改变属性的值，增加属性，方法等，但不可以修改对象的指针（变量的引用便不可修改）。

```js
const age = 26;
age = 36; // TypeError: 给常量赋值
// const 也不允许重复声明
const name = 'Matt';
const name = 'Nicholas'; // SyntaxError
// const 声明的作用域也是块
const name = 'Matt';
if (true) {
const name = 'Nicholas';
}
console.log(name); // Matt
```

const 声明的限制只适用于它指向的变量的引用。换句话说，如果 const 变量引用的是一个对象，那么修改这个对象内部的属性并不违反 const 的限制,改变指向就会报错。
```
const foo = {};
// 为 foo 添加一个属性，可以成功
foo.prop = 123;
foo.prop // 123
// 将 foo 指向另一个对象，就会报错
foo = {}; // TypeError: "foo" is read-only
//如果将另一个数组赋值给a会报错
const a = [];
a.push('Hello'); // 可执行
a.length = 0;    // 可执行
a = ['Dave'];    // 报错


```
JavaScript 引擎会为 for 循环中的 let 声明分别创建独立的变量实例，虽然 const 变量跟 let 变量很相似，但是不能用 const 来声明迭代变量（因为迭代变量会自增）：

```js
for (const i = 0; i < 10; ++i) {} // TypeError：给常量赋值
```
不过，如果你只想用 const 声明一个不会被修改的 for 循环变量，那也是可以的。也就是说，每次迭代只是创建一个新变量。这对 for-of 和 for-in 循环特别有意义：
```js
let i = 0;
for (const j = 7; i < 5; ++i) {
console.log(j);
}
// 7, 7, 7, 7, 7
for (const key in {a: 1, b: 2}) {
console.log(key);
}
// a, b
for (const value of [1,2,3,4,5]) {
console.log(value);
}
// 1, 2, 3, 4, 5
```

 ## 4.声明风格及最佳实践

> ECMAScript 6 增加 let 和 const 从客观上为这门语言更精确地声明作用域和语义提供了更好的支持。行为怪异的 var 所造成的各种问题，已经让 JavaScript 社区为之苦恼了很多年。随着这两个新关键字的出现，新的有助于提升代码质量的最佳实践也逐渐显现。
> 
> ### 4.1. 不使用 var
> 
> 有了 let 和 const，大多数开发者会发现自己不再需要 var 了。限制自己只使用 let 和 const有助于提升代码质量，因为变量有了明确的作用域、声明位置，以及不变的值。
> 
> ### 4.2. const 优先，let 次之
> 
> 使用 const 声明可以让浏览器运行时强制保持变量不变，也可以让静态代码分析工具提前发现不合法的赋值操作。因此，很多开发者认为应该优先使用 const 来声明变量，再使用 let。这样可以让开发者更有信心地推断某些变量的值永远不会变，同时也能迅速发现因意外赋值导致的非预期行为。
>  开发实践表明，如果开发流程并不会因此而受很大影响，就应该尽可能地多使用
const 声明，除非确实需要一个将来会重新赋值的变量。这样可以从根本上保证提前发现
重新赋值导致的 bug


## 5.let、const、var的区别

> 
> **（1）块级作用域：**块作用域由 `{ }`包括，let和const具有块级作用域，var不存在块级作用域。块级作用域解决了ES5中的两个问题：
> 
> -   内层变量可能覆盖外层变量
> -   用来计数的循环变量泄露为全局变量
> 
> **（2）变量提升：**var存在变量提升，let和const不存在变量提升，即在变量只能在声明之后使用，否在会报错。
> 
> **（3）给全局添加属性：**浏览器的全局对象是window，Node的全局对象是global。var声明的变量为全局变量，并且会将该变量添加为全局对象的属性，但是let和const不会。
> 
> **（4）重复声明：**var声明变量时，可以重复声明变量，后声明的同名变量会覆盖之前声明的遍历。const和let不允许重复声明变量。
> 
> **（5）暂时性死区：**在使用let、const命令声明变量之前，该变量都是不可用的。这在语法上，称为**暂时性死区**。使用var声明的变量不存在暂时性死区。
> 
> **（6）初始值设置：**在变量声明时，var 和 let 可以不用设置初始值。而const声明变量必须设置初始值。
> 
> **（7）指针指向：**let和const都是ES6新增的用于创建变量的语法。 let创建的变量是可以更改指针指向（可以重新赋值）。但const声明的变量是不允许改变指针的指向。
> 
>在函数内部如果用var声明变量和不用时有很大差别，用var声明的是局部变量，在函数外部访问这个变量是访问不到的，没var声明的是全局变量。在函数外部是可以访问到的。
## 6.今日精进
59 - I. 滑动窗口的最大值（维护一个单调队列，队头元素依次递减）。

# Day6【2022年7月28日】
**学习重点：** 总结一下js字符串常用的一些原生方法（API)(上)

相信应该会有小伙伴遇到这种情况，用过的一些js原生方法忘记具体用法或是每个参数的含义。总结一下常用的一些方法，以后不懂可以查本篇，不常用的不展开叙述。
## 1.字符串方法总结(上)
### 1.1 at()
返回指定字符串索引值(位置对应的值)，当传递负数时，支持从字符串末端开始的相对索引；也就是说，如果使用负数，返回的字符将从字符串的末端开始倒数。

**用法：**
```js
at(index)
//index要返回的字符串字符的索引（位置）
```
**返回值：**

> 由位于指定位置的单个 UTF-16 码元组成的 String。如果找不到指定的索引，则返回 undefined

**实例**
```js
let a = "a bcd"
let c = a.at(1);
let d = a.at(-1);
let e = a.at(4);
let f = a.at(5);

console.log(c);//  
console.log(d);// d
console.log(e);// d
console.log(f);// undefinde
console.log(a.at())//a
```
不传索引默认索引为0.
**' '也是有意义的字符串，也占位。**
### 1.2 charAt()
charAt() 方法从一个字符串中返回指定的字符。

**用法：**
```js
str.charAt(index)
//index一个介于 0 和字符串长度减 1 之间的整数。(0~length-1) 如果没有提供索引，charAt() 将使用 0。
```
**返回值：**

存在就返回存在的对应字符串，不存在则返回空字符串。

**实例：**
```js
let a = "a bcd";
let b = a.charAt(1);
let c = a.charAt(-1);
let d = a.charAt(4);

console.log(b);
console.log(c);
console.log(d);
//  
// 
// d
console.log(a.charAt())//a
```
不传索引默认索引为0.
由此可以看出charAt如果是负索引返回的是空字符串，如果索引不存在返回的也是空字符串，这跟at还是有一定区别的。
### 1.3 charCodeAt()
charCodeAt() 方法返回 0 到 65535 之间的整数，表示给定索引处的 UTF-16 代码单元。

**用法：**
```js
str.charCodeAt(index)
//一个大于等于 `0`，小于字符串长度的整数。如果不是一个数值，则默认为 `0`。
```
**返回值：**

指定 index 处字符的 UTF-16 代码单元值的一个数字；如果 index 超出范围，charCodeAt() 返回 NaN

**实例：**
```js
let a = "a bcd";
let b = a.charCodeAt(1);
let c = a.charCodeAt(-1);
let d = a.charCodeAt(4);
let e = a.charCodeAt('h');
let f = a.charCodeAt(0);

console.log(b);// 32
console.log(c);// NaN
console.log(d);// 100
console.log(e);// 97
console.log(f);// 97
console.log(a.charCodeAt())//97
```
不传索引默认索引为0.
### 1.4 codePointAt()
返回 一个 Unicode 编码点值的非负整数。

**用法：**
```js
str.codePointAt(pos)
//pos 这个字符串中需要转码的元素的位置。
```
**返回值：**

返回值是在字符串中的给定索引的编码单元体现的数字，如果在索引处没找到元素则返回 undefined 。

**实例：**
```js
let a = "a bcd";
let b = a.codePointAt(1);
let c = a.codePointAt(-1);
let d = a.codePointAt(4);
let e = a.codePointAt('h');
let f = a.codePointAt(0);
let g = a.codePointAt();


console.log(b);
console.log(c);
console.log(d);
console.log(e);
console.log(f);
console.log(g);
// 32
// undefined
// 100
// 97
// 97
// 97
```
**总结一下**（画表格）
### 1.5 concat()
将一个或多个字符串与原字符串连接合并，形成一个新的字符串并返回。

**用法：**
```js
str.concat(str2, [, ...strN])
// str 需要连接的字符串
```
**返回值：**

一个新的字符串，包含参数所提供的连接字符串

**实例：**
```js
let a = "a bcd";
let b = a.concat('vv');
let c = a.concat('vv', 'vv');
let d = a.concat(['vv', 'vv']);
let e = a.concat(['vv', 'vv'], 'vv');
let f = a.concat(1);
let g = a.concat(1, 'vv');
let h = a.concat();

console.log(b);
console.log(c);
console.log(d);
console.log(e);
console.log(f);
console.log(g);
console.log(h);
// a bcdvv
// a bcdvvvv
// a bcdvv,vv
// a bcdvv,vvvv
// a bcd1
// a bcd1vv
// a bcd
```
> concat 方法将一个或多个字符串与原字符串连接合并，形成一个新的字符串并返回。 concat 方法并不影响原字符串。**如果参数不是字符串类型，它们在连接之前将会被转换成字符串(例如toString等)。** 强烈建议使用赋值操作符（+, +=）代替 concat 方法(性能不好)。

### 1.6 endsWith()
endsWith()方法用来判断当前字符串是否是以另外一个给定的子字符串“结尾”的，根据判断结果返回 true 或 false。

**用法：**
```js
str.endsWith(searchString[, length])
//searchString要搜索的子字符串。
length 可选作为 str 的长度。默认值为 str.length。
```
**返回值：**

如果传入的子字符串在搜索字符串的末尾则返回true；否则将返回 false。

**实例：**
```js
let a = "a bcd";
let b = a.endsWith('d');
let c = a.endsWith('d', 1);
let d = a.endsWith('d', 5);
let j = a.endsWith();
let k = a.endsWith('bcd');

console.log(b);
console.log(c);
console.log(d);
console.log(j);
console.log(k);
console.log(a.length);
// true
// false
// true
// false
// true
// 5
```
### 1.7 includes()
用于判断一个字符串是否包含在另一个字符串中，根据情况返回 true 或 false。**该方法区分大小写。**

**用法：**
```js
str.includes(searchString[, position])
// searchString要在此字符串中搜索的字符串。

//position 可选从当前字符串的哪个索引位置开始搜寻子字符串，默认值为 `0`。

```
**返回值：**

如果当前字符串包含被搜寻的字符串，就返回 true；否则返回 false。

**实例：**
```js
'Blue Whale'.includes('blue'); //false
let a = "a bcd";
let b = a.includes('b');
let c = a.includes();
let d = a.includes('a', 1);


console.log(b);
console.log(c);
console.log(d);
// true
// false
// false
```
### 1.8 indexOf()
indexOf() 方法返回调用它的 String 对象中第一次出现的指定值的索引，从开始制度查找处进行搜索，不填默认为0(第二个参数)。如果未找到该值，则返回 -1。

**用法：**
```js
str.indexOf(searchValue [, fromIndex])
```
**searchValue**
> 要被查找的字符串值。如果没有提供确切地提供字符串，searchValue 会被强制设置为 "undefined"， 然后在当前字符串中查找这个值。
> 
> 举个例子：`'undefined'.indexOf()` 将会返回 0，因为 `undefined` 在位置 0 处被找到，但是 `'undefine'.indexOf()` 将会返回 -1 ，因为字符串 `'undefined'` 未被找到。

**fromIndex 可选**
> 数字表示开始查找的位置。可以是任意整数，默认值为 0。如果 fromIndex 的值小于 0，或者大于 str.length ，那么查找分别从 0 和str.length 开始。fromIndex 的值小于 0，等同于为空情况； fromIndex 的值大于或等于 str.length ，那么结果会直接返回 -1 。
> 
> 举个例子，`'hello world'.indexOf('o', -5)` 返回 `4` ，因为它是从位置`0`处开始查找，然后 `o` 在位置`4`处被找到。另一方面，`'hello world'.indexOf('o', 11)` （或 `fromIndex` 填入任何大于`11`的值）将会返回 `-1` ，因为开始查找的位置`11`处，已经是这个字符串的结尾了。

转化一下
a = 'abcd',a.length =4,索引为0-3，如果 fromIndex<0 那么默认会从0开始查找（相当于为空），如果fromIndex>=4 那么会从4开始查找则会返回-1。

**返回值：**

查找的字符串 searchValue 的第一次出现的索引，如果没有找到，则返回 -1。

**实例：**
```js
let a = "a bcd"
let b = a.indexOf('b');
let c = a.indexOf('b', 1);
let d = a.indexOf('b', 5);
let e = a.indexOf('b', -1);
let f = a.indexOf();
let g ='undefinde'.indexOf();
let h = a.indexOf('d', 8);
let i = a.indexOf('a', 0);
let j = a.indexOf('d', 4);

console.log(b);
console.log(c);
console.log(d);
console.log(e);
console.log(f);
console.log(g);
console.log(h);
console.log(i);
console.log(j);
// 2
// 2
//-1
// 2
// -1
// -1
// -1
// 0
// 4
```
### 1.9 localeCompare()
返回一个数字来指示一个参考字符串是否在排序顺序前面或之后或与给定字符串相同（大部分是结合排序使用）。
> 新的 `locales` 和 `options` 参数能让应用程序定制函数的行为，即指定用来排序的语言。`locales` 和 `options` 参数完全取决于实现，在旧的实现中忽略这两个参数。
**用法：**
```js

referenceStr.localeCompare(compareString[, locales[, options]])

```
compareString用来比较的字符串 
locales(语言环境)：用来指定比较字母的语言环境（默认是英文）
options(选项)：指定一些排序的规则如灵敏度等
**返回值：**
如果引用字符存在于比较字符之前则为负数; 如果引用字符存在于比较字符之后则为正数; 相等的时候返回 0 .
-   当 **引用字符串** 在 **比较字符串** 前面时返回 -1 (sort相同)
-   当 **引用字符串** 在 **比较字符串** 后面时返回 1(sort相同)
-   相同位置时返回 0

> **切勿依赖于 -1 或 1 这样特定的返回值。** 不同浏览器之间（以及不同浏览器版本之间）返回的正负数的值各有不同，因为 W3C 规范中只要求返回值是正值和负值，而没有规定具体的值。一些浏览器可能返回 -2 或 2 或其他一些负的、正的值。
相当于给定26个字母的顺序排序。
**实例：**
```js
let a = "a bcd";
let b = " bcd";
let c = "bcd";
console.log(a.localeCompare("a"));// 1
console.log(a.localeCompare("b"));// -1
console.log(a.localeCompare("a bcd"));// 0
console.log(b.localeCompare("a"));// -1
console.log(b.localeCompare("b"));// -1
console.log(b.localeCompare(" bcd"));// 0
console.log(c.localeCompare("a"));// 1
console.log(c.localeCompare("b"));// 1
console.log(c.localeCompare("bcd"));// 0
```
比较规则总结
```js
console.log("b".localeCompare("a"));
console.log("b".localeCompare("b"));
console.log("b".localeCompare("c"));
console.log("b".localeCompare("a bcd"));
console.log("b".localeCompare(" bcd"));
console.log("b".localeCompare("bcd"));
console.log("b".localeCompare("accd"));
```
如上所示，b对比多个字符串时候会先比较第一个若第一个相同再比较下一个，依次比较到处结果为止，''比较特殊默认是在a前面。
```js
console.log("a".localeCompare(" "));
```
### 1.10 match()
方法检索返回一个字符串匹配正则表达式的结果及分组捕获组的迭代器。

**用法：**
```js
str.match(regexp)
```
> 一个正则表达式对象。如果传入一个非正则表达式对象，则会隐式地使用 new RegExp(obj) 将其转换为一个 RegExp 。如果你没有给出任何参数并直接使用 match() 方法 ，你将会得到一个包含空字符串的 Array ：[""] 。

**返回值：**

> 如果使用 g 标志（全局匹配模式），则将返回与完整正则表达式匹配的所有结果，但不会返回捕获组。
> 如果未使用 g 标志（全局匹配模式），则仅返回第一个完整匹配及其相关的捕获组（Array）。 在这种情况下，返回的项目将具有如下所述的其他属性。
> 
> 附加属性
> 如上所述，匹配的结果包含如下所述的附加特性。
> groups: 一个命名捕获组对象，其键是捕获组名称，值是捕获组，如果未定义命名捕获组，则为 undefined。有关详细信息，请参阅组和范围。
> index: 匹配的结果的开始位置
> input: 搜索的字符串。
> 一个Array，其内容取决于 global（g）标志的存在与否，如果未找到匹配则为null。

**实例：**
```js
let a = "aBcd";
//匹配大写字母不带g 会返回捕获器
console.log(a.match(/[A-Z]/));// ['B', index: 1, input: 'aBcd', groups: undefined]
console.log(...a.match(/[A-Z]/));// B
//全局匹配模式 匹配所有的大写字母 仅返回第一个完整匹配及其相关的捕获组
console.log(a.match(/[A-Z]/g));// ['B']
console.log(a.match(/[a-z]/g) instanceof Array);// true
//如果匹配不存在则返回null
let a = "aBcd";
console.log(a.match(/h/g));// null
console.log(a.match(/h/));// null
```
扩展符(…)可以解析出来
不是特别熟悉的小伙伴可以看下这篇文章补一下正则表达式->[点击这里](https://blog.csdn.net/h610443955/article/details/81079439?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165902586016781647528127%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165902586016781647528127&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-81079439-null-null.142^v35^experiment_2_v1&utm_term=js%E6%AD%A3%E5%88%99%E8%A1%A8%E8%BE%BE%E5%BC%8F&spm=1018.2226.3001.4187)

### 1.11 matchAll()
返回一个包含所有匹配正则表达式的结果及分组捕获组的迭代器。

**用法：**
```js
str.matchAll(regexp)
```
> regexp正则表达式对象。如果所传参数不是一个正则表达式对象，则会隐式地使用 new RegExp(obj) 将其转换为一个 RegExp 。**RegExp必须是设置了全局模式g的形式，否则会抛出异常TypeError。（跟match的区别）**
> 
**返回值：**
> 一个迭代器（不可重用，结果耗尽需要再次调用方法，获取一个新的迭代器）。

**实例：**
```js
let str = 'test1test2';
console.log([...str.matchAll(/t/g)][0]);// ['t', index: 0, input: 'test1test2', groups: undefined]
console.log([...str.matchAll(/t/g)][1]);// ['t', index: 3, input: 'test1test2', groups: undefined]
console.log( [...str.matchAll(/t/g)]);// (4) [Array(1), Array(1), Array(1), Array(1)]
  console.log( ...str.matchAll(/t/g));//返回匹配的四个迭代器数组
//报错
console.log( [...str.matchAll(/t/)]);
```
match可以带g也可以不带g，如果带g将返回与完整正则表达式匹配的所有结果，不会返回捕获组，不带g仅返回第一个完整匹配及其相关的捕获组（Array）。matchAll必须是全局匹配。
### 1.12 normalize()
> 会按照指定的一种 Unicode 正规形式将当前字符串正规化。（如果该值不是字符串，则首先将其转换为一个字符串）

**用法：**
```js
str.normalize([form])
```
form可选四种 Unicode 正规形式（Unicode Normalization Form）`"NFC"`、`"NFD"`、`"NFKC"`，或 `"NFKD"` 其中的一个，默认值为 `"NFC"`。具体含义感兴趣的小伙伴可以去查。
**返回值：**
含有给定字符串的 Unicode 规范化形式的字符串。

### 1.13 padEnd() 
方法会用一个字符串填充当前字符串（如果需要的话则重复填充），返回填充后达到指定长度的字符串。从当前字符串的末尾（右侧）开始填充。

**用法：**
```js
str.padEnd(targetLength [, padString])
```
>  targetLength当前字符串需要填充到的目标长度。如果这个数值小于当前字符串的长度，则返回当前字符串本身。
> 
> padString 可选 填充字符串。如果字符串太长，使填充后的字符串长度超过了目标长度，则只保留最左侧的部分，其他部分会被截断。此参数的缺省值为 " "（U+0020）。

**返回值：**

在原字符串末尾填充指定的填充字符串直到目标长度所形成的新字符串。

**实例：**
```js
let a = "aBcd";

console.log(a.padEnd(10));//aBcd 后面填充空格
console.log(a.padEnd(10).length);//10  
console.log(a.padEnd(10, "foo"));//aBcdfoofoo
console.log(a.padEnd(6, "123456"));//  aBcd12
console.log(a.padEnd(1));//  aBcd
```
### 1.14 padStart()
法用另一个字符串填充当前字符串 (如果需要的话，会重复多次)，以便产生的字符串达到给定的长度。从当前字符串的左侧开始填充。

**用法：**
```js
str.padStart(targetLength [, padString])
```
> targetLength
> 当前字符串需要填充到的目标长度。如果这个数值小于当前字符串的长度，则返回当前字符串本身。
> padString 可选
> 填充字符串。如果字符串太长，使填充后的字符串长度超过了目标长度，则只保留最左侧的部分，其他部分会被截断。此参数的默认值为 " "（U+0020）。

**返回值：**

在原字符串开头填充指定的填充字符串直到目标长度所形成的新字符串。

**实例：**
```js
let a = "aBcd";

console.log(a.padStart(10));//       aBcd
console.log(a.padStart(10).length);//10  
console.log(a.padStart(10, "foo"));//foofooaBcd
console.log(a.padStart(6, "123456"));//  12aBcd
console.log(a.padStart(1));//  aBcd
```
实际上跟padEnd是一样的只不过一个是头另一个是尾部。
### 1.15 raw()（Spring.raw())
> 用来获取一个模板字符串的原始字符串的，比如说，占位符（例如 `${foo}`）会被处理为它所代表的其他字符串，而转义字符（例如 `\n`）不会。在大多数情况下，`String.raw()` 是用来处理模版字符串的。还模板字符串为原生的 String 对象

其他的方法都是挂载在# prototype（原型对象）下他是直接挂载String下的API所以使用方法会用不同，String原型对象下没有声明的字符串不能直接调用。
如图所示：

<img src="https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/c2f30fbd62954b509b792e5b9136d1b9~tplv-k3u1fbpfcp-watermark.image?" alt="image.png" width="50%" />

**用法：**
```js
String.raw(callSite, ...substitutions)

String.raw`templateString`
```
> callSite
> 一个模板字符串的“调用点对象”。类似 { raw: ['foo', 'bar', 'baz'] }。
> ...substitutions
> 任意个可选的参数，表示任意个内插表达式对应的值。
> templateString
> 模板字符串，可包含占位符（${...}）。

**返回值：**

给定模板字符串的原始字符串。

**实例：**
```js
// raw方法
String.raw`Hi\n${2+3}!`;
// 'Hi\\n5!'，Hi 后面的字符不是换行符，\ 和 n 是两个不同的字符

String.raw `Hi\u000A!`;
// "Hi\\u000A!"，同上，这里得到的会是 \、u、0、0、0、A 6 个字符，
// 任何类型的转义形式都会失效，保留原样输出，不信你试试.length

let name = "Bob";
String.raw `Hi\n${name}!`;
// "Hi\\nBob!"，内插表达式还可以正常运行

String.raw`Hi${2+3}!`;\\'Hi5!'

// 正常情况下，你也许不需要将 String.raw() 当作函数调用。
// 但是为了模拟 `t${0}e${1}s${2}t` 你可以这样做：
String.raw({ raw: 'test' }, 0, 1, 2); // 't0e1s2t'
// 等同于
String.raw({ raw: ['t','e','s','t'] }, 0, 1, 2);

// 注意这个测试，传入一个 string，和一个类似数组的对象
// 下面这个函数和 `foo${2 + 3}bar${'Java' + 'Script'}baz` 是相等的。
String.raw({
  raw: ['foo', 'bar', 'baz']
}, 2 + 3, 'Java' + 'Script'); // 'foo5barJavaScriptbaz'

```
可以看出 \n 转换会多出一个\这个要注意
### 1.16 repeat()
 构造并返回一个新字符串，该字符串包含被连接在一起的指定数量的字符串的副本(重复拼接当前字符串)。
 
**用法：**
```js
str.repeat(count)
``
count
介于 0 和 +Infinity(正无穷大) 之间的整数。表示在新构造的字符串中重复了多少遍原字符串。

**返回值：**
包含指定字符串的指定数量副本的新字符串。
**实例：**
```js
let a="aBcd"
console.log(a.repeat(2));//aBcdaBcd
```
## 2.今日精进
选择大于努力，思路决定出路，选择比努力更重要。




# Day7【2022年7月29日】 
**学习重点：** 总结一下js字符串常用的一些原生方法（API)(下)
## 1.字符串方法总结(下)
### 1.1 replace()
指定字符串中目标替换成给定的值，如果第一个值传入的是字符串则只会替换第一个，正则表达式则按照标准替换。

**用法：**
```js
str.replace(regexp|substr, newSubStr|function)
```
regexp 正则表达式（会全部替换）
substr 字符串，只会替换第一个目标元素。
newSubStr 用来替换的字符串元素。
function 用来替换的函数
function 怎么传值可以参考这个[MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace)

**返回值：**

被替代的新字符串。

**实例：**
```js
let a = "abcdaabd";
console.log(a.replace(/a/g, 'ff' ));//ffbcdffffbd
console.log(a.replace('a', 'ff' ));// ffbcdaabd
console.log(a.replace(/a/, 'ff' ));// ffbcdaabd

函数替换实例：
var str="他今年22岁，她今年20岁，他的爸爸今年45岁，她的爸爸今年44岁，一共有4人"
function test($1){
  var gyear=(new Date()).getYear()-parseInt($1)+1;
  return $1+"("+gyear+"年出生)";
}
var reg=new RegExp("(\\d+)岁","g");
var newstr=str.replace(reg,test);


console.log(newstr)//他今年22岁(101年出生)，她今年20岁(103年出生)，他的爸爸今年45岁(78年出生)，她的爸爸今年44岁(79年出生)，一共有4人
console.log(str)//他今年22岁，她今年20岁，他的爸爸今年45岁，她的爸爸今年44岁，一共有4人
```

### 1.2 replaceAll()
将指定字符串中目标全部替换成给定的值，如果正则表达式不是全局则会报错。

**用法：**
```js
const newStr = str.replaceAll(regexp|substr, newSubstr|function)
```
参数含义跟replace一样。

**返回值：**

新的字符串

**实例：**
```js
let a = "abcdaabd";
console.log(a.replaceAll(/a/g, 'ff' ));// ffbcdffffbd
console.log(a.replaceAll('a', 'ff' ));// ffbcdffffbd
console.log(a.replaceAll(/a/, 'ff' ));//报错
```
### 1.3 search()
用正侧表达式去匹配字符串对应的值，并返回索引。

**用法：**

```js
str.search(regexp)
```
regexp表示一个正则表达式对象。如果传入一个非正则表达式对象，则会使用 new RegExp(regexp) 隐式地将其转换为正则表达式对象。

**返回值：**

返回首次匹配项的索引，匹配不成功返回-1。

**实例：**
```js
let a  = "a Bcd";
console.log(a.search(/a/));// 0
console.log(a.search(/e/));//-1
```
相对与match()方法该方法会快一些。
search()对应正则表达式中的test()方法，match()对应正则表达式中的exec()方法。
search()返回第一个索引，match()返回捕获的迭代器。
### 1.4 slice()
截取字符串的一部分，并返回一个新的字符串，不会对原字符串改动。

**用法：**

```js
str.slice(beginIndex[, endIndex])
```
beginIndex 开始匹配的索引，如果是负数则会根据公式（str.length+beginIndex）转换。

endIndex **可选** 如果不选改参数，默认一直提取到字符串末尾，选择则提取到当前。若为负责则会跟begin一样加上字符串长度。

**返回值：**

返回一个被截取出来的的新字符串。

**实例：**
```js
let a = "a Bcd";
console.log(a.length);//5
//正数
console.log(a.slice(0,1)); //'a'
console.log(a.slice(0,2));//'a '
console.log(a.slice(0));'6 a Bcd'
//带负
console.log(a.slice(0,-1));'a Bc'
console.log(a.slice(-1,3));''
console.log(a.slice(-1));'d'
console.log(a.slice(-1,-2));
//试错
console.log(a.slice());''
console.log(a.slice(0,1,2));'a Bcd'
console.log(a.slice(6));//
console.log(a.slice(2,3)); //B
```
由此可以总结处，如果输入的索引超出字符串的长度会返回一个空字符串。
而且查找过程中包含开始的索引不包含结尾的索引。

### 1.5 split()
用指定的分隔字符串将目标字符串拆分成子数组。

**用法：**
```js
str.split([separator[, limit]]) 
```
separato指定表示每个拆分应发生的点的字符串，limit一个整数，限定返回的分割片段数量。

**返回值：**

数组

**实例：**
```js
let myString = "Hello World. How are you doing?";
console.log( myString.split(" ", 3));// ['Hello', 'World.', 'How']
console.log( myString.split(" ", 3).join(" "));// Hello World. How
console.log( myString.split(" "));// ['Hello', 'World.', 'How', 'are', 'you', 'doing?']
console.log( myString.split(" ").join(" "));// Hello World. How are you doing?
```
一般配合join（根据传入字符串为间隔拼接每个数组元素为字符串）方法一起用。
### 1.6 startsWith()
用来判断某个字符串是否以特定的字符串开头，返回ture/false,区分大小写。

**用法：**
```js
str.startsWith(searchString[, position])
```
searchString要搜索的子字符串。
position **可选**要搜索的初始位置，默认为0。
**返回值：**
ture/false

**实例：**
```js
let a = "a Bcd";
console.log(a.startsWith("a "));//true
console.log(a.startsWith("a B"));//true
console.log(a.startsWith("a bc"));//false
```
### 1.7 toLocaleLowerCase()
将指定字符串转换为小写格式

**用法：**
```js
str.toLocaleLowerCase()
str.toLocaleLowerCase(locale)
str.toLocaleLowerCase([locale, locale, ...])
```
locale 为指定要转换成小写格式的特定语言区域。默认值是当前计算机的语言格式。

**返回值：**

转换成小写格式的新字符串。

**实例：**
```js
let a = "a Bcd";
console.log(a.toLocaleLowerCase());//a bcd
```
### 1.8 toLocaleUpperCase()
将指定字符串转换为大写写格式，具体用法跟上面差不多，这里只举例说明。
```js
let a = "a Bcd";
console.log(a.toLocaleLowerCase());//a bcd
console.log(a.toLocaleUpperCase());//A BCD
```
### 1.9 toLowerCase()
将一个字符串转换为小写的形式并返回。

**用法：**
```js
str.toLowerCase()
```

**返回值：**

一个小写新的字符串。

**实例：**
```js
let a = "a Bcd";
console.log(a.toLocaleLowerCase());//a bcd
console.log(a.toLocaleUpperCase());//A BCD
console.log(a.toLowerCase());//a bcd
console.log(a);//a bcd
```
这里可以看出，toLocaleLowerCase和toLowerCase都不会影响字符串本身，都是返回一个新的字符串。
可以理解为toLocaleLowerCase是toLowerCase的一个加强版本，前者可以选择以什么样的特定语言来返回字符串的大小写，而后者不行，后者只能默认为计算机的语言。
### 1.10 toString()
返回一个字符串/某些值转化为字符串
**用法：**
```js
toString()
```

**返回值：**

String 包装对象的字符串值。

**实例：**
```
let a = "abc";
let b =  new String("abcd");
let c = 2
console.log(a.toString());// abc
console.log(b.toString());// abcd
console.log(true.toString());// true
console.log(c.toString());// 2
```
### 1.11 toUpperCase()
将字符串转换为大写（如果调用该方法的值不是字符串类型会被强制转换）。

**用法：**
```js
str.toUpperCase()
```
**返回值：**

返回一个转化为大写的字符串，不改变原字符串。

**实例：**
```js
let a = "abc";
console.log(a.toUpperCase());// ABC
非字符串转化为字符串
const b = String.prototype.toUpperCase.call(true);
console.log( b);.// TRUE
```

与toLocaleUpperCase的关系 同toLocaleLowerCase和toLowerCase类似
### 1.12 trim()
移除字符串左右两边的空白字符串。

**用法：**
```js
str.trim()
```
**返回值：**

一个去掉两端空白字符串的新字符串

**实例：**
```js
let a = "    a Bcd    ";
let b = a.trim();
console.log(b);//a Bcd
console.log(a.length);//13
console.log(b.length);//5
```
> 在这个上下文中的空白字符是所有的空白字符 (space, tab, no-break space 等) 以及所有行终止符字符（如 LF，CR 等）。

### 1.13 trimEnd()
也称之为trimRight()移除字符串的末尾空白字符串，不会直接修改原字符串，改名称标准叫法为trimEnd()，只是为了兼容性，还保留了trimRight()名称。

**用法：**
```js
str.trimEnd();
str.trimRight();
```
**返回值：**

符合要求的新字符串。

**实例：**
```js
let a = "a Bcd    ";
let b = a.trimEnd();
console.log(b);//a Bcd
console.log(a.length);//9
console.log(b.length);//5
```
### 1.14 trimStart()
也称之为trimLeft()，trimStart()是标准叫法，移除字符串左边的空字符串。为了兼容性保留了trimLeft()。

**用法：**

```js
str.trimStart();
str.trimLeft();
```
**返回值：**

新字符串

**实例：**
```js
let a = "    a Bcd    ";
let b = a.trimStart();
console.log(b);//a Bcd
console.log(a.length);//13
console.log(b.length);//9
```
trim，trimStart，trimEnd三个方法都是用来去除字符串中的空字符串，如果要去除数组中所有的字符串可以使用replaceAll 替换或者用for变量字符串替换。

<img src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8ff9203156914d76b9a512f917267020~tplv-k3u1fbpfcp-watermark.image?" alt="image.png" width="70%" />
由此图可以看出trimStart，trimEnd是标准的官网推荐的方法，在不久相信trimleft和trimleft会被废弃。
### valueOf()
返回对象的初始值，通常在js内部调用而不是显示带调用。

## 2.今日精进
49. 字母异位词分组​（哈希表解题）



# 参考资料
-   JavaScript高级程序设计（第4版）
-  [MDN](https://developer.mozilla.org/en-US/)
-  [鲨鱼哥的面试题总结](https://github.com/BigSharkLx/front-end-interview/blob/main/5%20offer%E6%94%B6%E5%89%B2%E6%9C%BA%E4%B9%8BJavaScript%E7%AF%87.md)
-  解锁前端面试体系核心攻略
-  [细数JavaScript中那些遍历和循环](https://cuggz.blog.csdn.net/article/details/107649549)
#  结语

志同道合的小伙伴可以加我，一起交流进步，我们坚持每日精进（互相监督思考学习，如果坚持不下来我可以监督你）。另外共享学习资料的小伙伴也可以联系我，进群技术交流资料free共享，我们交换资料一起努力鸭！
——>[点击这里](https://juejin.cn/pin/7123425224455880740)

# 备注
按照时间顺序倒叙排列，完结后按时间顺序正序排列方便查看知识点。








