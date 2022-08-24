---
theme: juejin
highlight: tomorrow
---
**挑战坚持学习1024天——前端之JavaScript高级**

大家好我是牛哥，经过三周的总结大概把基础部分过完一遍，在复盘基础的同时也穿插着复盘了一些js高级的一些内容。在复盘总结时发现知识点与知识点之间是紧密相连的，在实际开发过程中如果但凡有一个知识点不清楚，后续就会比较困难。由此可见js每一个基础知识都是非常重要的。基础知识只是暂时性的告一段落，后续还会持续更新，如有遗漏的还请各位小伙伴指出。学完不代表结束了，还要定期复盘，根据艾宾浩斯遗忘曲线，一周后的记忆存留率仅为25%，唯有利用高效记忆的技巧不断的巩固复习，不断的实践，相信在不久的将来有面试官问到这些知识点时你将脱口而出。希望该系列文章可以帮到大家。

接下来将开启新的一个阶段--js高级部分，吸取了之前的教训发现效率还是不够高，决定接下来提高学习效率，浓缩精华，一起进步！坚持每日精进，坚持不下去的时候咬咬牙，强者站在高处看风景，弱者还在为琐事而焦虑。

js基础部分可到我文章专栏去看 ---[点击这里](https://juejin.cn/column/7123014837294235662)
# Day22【2022年8月15日】 
**学习重点：** this指向
## 1.this绑定规则
this绑定有四个规则：
- 默认绑定
- 隐式绑定
- 显示绑定
- new绑定

**this 的指向是在调用时决定的，而不是在书写时决定的。这点和闭包恰恰相反。**
### 1.1默认绑定
一般默认绑定为独立函数的调用。

独立的函数调用可以理解成函数没有被绑定到某个对象上进行调用。
this 指向全局对象。在浏览器中，指向 window；在 Node 中，指向 Global。（严格模式下，指向 undefined）。

#### 1.1.1普通的函数被独立的调用
```js
function foo() {
      console.log("foo:", this) //window
    }
    foo()
// foo: Window {0: global, window: Window, self: Window, document: document, name: '', location: Location, …}
```
#### 1.1.2定义在对象中函数的独立调用
下文举例出实例进行对比，相当于先赋值再调用。
```js
var obj = {
      name: "why",
      bar: function() {
        console.log("bar:", this) // 输出: window
      }
    }
    obj.bar(); //{name: 'why', bar: ƒ}  隐式绑定
    //默认绑定
    var baz = obj.bar
    console.log(baz) //ƒ () {console.log("bar:", this) // 输出: window} 
    baz()
```
#### 1.1.3高级函数
```js
var obj = {
      name: "why",
      bar: function() {
        console.log("bar:", this) // 输出: window
      }
    }
function test(fn) {
      fn()
    }
    test(obj.bar) // window
```
**严格模式下, 独立调用的函数中的this指向的是undefined**
### 1.2.隐式绑定
常见的式某个对象对函数进行调用

**实例** 
```js
function foo() {
      console.log("foo函数:", this)
    }

    var obj = {
      bar: foo
    }

    obj.bar() // foo函数: {bar: ƒ}
    
```
### 1.3.显示绑定
通过call()/apply()/bind()方法直接指定this的绑定对象
#### 1.3.1 call/apply/bind
首先介绍一些call/apply/bind这三个方法用法及其区别。
##### 1.3.1.1 call
使用一个指定的 this 值和单独给出的一个或多个参数来调用一个函数。
允许为不同的对象分配和调用属于一个对象的函数/方法。可以用call实现继承，写一个方法，然后让另外一个新的对象来继承它（而不是在新对象中再写一次这个方法）。
**用法**
```js
function.call(指定this指向, arg1, arg2, ...)
```
- 指定的两个参数this指向（可选）在**非严格模式**下，如果不指定/null/undefined的话则默认绑定window。**严格模式**传入null和undefined，指向对应传入的，如果不传参数this就是undefined。

- 第二个默认为参数列表，依次传入(可选)为多个。

**返回值**
> 使用调用者提供的 this 值和参数调用该函数的返回值。若该方法没有返回值，则返回 undefined。

**实例**
```js
var obj = {
    name: "why"
  }

  function foo() {
    console.log("foo函数:", this)
  }
    foo(); //window
    foo.call(obj);   //foo函数: {name: "why"}
```
##### 1.3.1.2 apply
调用一个具有给定 this 值的函数，以及以一个数组（或一个类数组对象）的形式提供的参数。把需要传递给fn的参数放到一个数组（或者类数组）中传递进去，虽然写的是一个数组，但是也相当于给fn一个个的传递。

**用法**
```js
apply(指定this指向, argsArray)
```
第一个参数this指向用法跟call完全一样
第二个参数arrArray则传入数组，只有两个参数。

**返回值**
调用有指定 this 值和参数的函数的结果。

**实例**
```js
//在函数中使用
function foo() {
    console.log("foo函数:", this)
}
var obj = {
    name: "why"
}
foo.apply(obj);   //foo函数: {name: "why"}

var numbers = [5, 6, 2, 3, 7];

var max = Math.max.apply(null, numbers); // 7

console.log(max);//7

```
> 虽然这个函数的语法与 call() 几乎相同，但根本区别在于，call() 接受一个参数列表，而 apply() 接受一个参数的单数组。

##### 1.3.1.3 bind
bind() 方法创建一个新的函数，在 bind() 被调用时，这个新函数的 this 被指定为 bind() 的第一个参数，而其余参数将作为新函数的参数，供调用时使用。

bind并不会把函数立即执行，它是预先处理函数中的this和参数的，语法和call一模一样，区别在于立即执行还是等待执行，bind不兼容IE6~8。bind在实际的运用中式相对较少（react中有较多运用），一般开发过程中用call，apply用的较多。

用法完全跟call一样

**返回值**

返回一个原函数的拷贝，并拥有指定的 this值和初始参数。

**实例**
从实例可看出，直接调用bind不执行，回返回该函数，用赋值语句可调用指向bind。，若函数没形惨则传入argurments回接收到。
```js
function foo(name) {
    console.log("foo函数:", this);
    console.log("打印参数列表",name);
    console.log(arguments); //Arguments(2) ['1sefrser', '2sefrser', callee: ƒ, Symbol(Symbol.iterator): ƒ]
}
var obj = {
    name: "why"
}
 foo.bind(obj); //不调用函数，返回一个函数
 foo.call(obj,'1sefrser'); //foo函数: {name: "why"} 打印参数列表 1sefrser
 //调用bind
    // var foo1 = foo.bind(obj);
    // foo1("1sefrser"); //foo函数: {name: "why"}   打印参数列表 1sefrser
    var foo1 = foo.bind(obj,'1sefrser','2sefrser');
    foo1(); //foo函数: {name: "why"}  打印参数列表 1sefrser
```

![73d92fe3b5429afa14e90a456a69adc.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d9b200013d5a436e884e9d3353d4a202~tplv-k3u1fbpfcp-watermark.image?)
### 1.4 new绑定
回顾一下new会执行那些操作

使用new关键字来调用函数时，会执行如下的操作：
- 创建一个全新的对象；
- 这个新对象会被执行prototype连接；
- 这个新对象会绑定到函数调用的this上（this的绑定在这个步骤完成）；
- 如果函数没有返回其他对象，表达式会返回这个新对象。

使用new关键字调用一个构造函数时会默认return函数中的属性值（函数中没有定义return也会返回）。 可看day12 return的介绍有解析。
```js
function foo() {
    this.name = "why"//如果没有属性则返回空对象
    console.log("foo函数:", this)
}

new foo()
// foo函数: foo {name: 'why'}
//foo {name: 'why'} //默认返回的
```
## 2.this指向优先级
先说以上几种this绑定规则的优先级的结论（依次从上到下）：
* new
* bind
* apply/call
* 隐式绑定
* 默认绑定

**默认规则的优先级最低**
毫无疑问，默认规则的优先级是最低的，因为存在其他规则时，就会通过其他规则的方式来绑定this。

**显示绑定优先级高于隐式绑定**

代码测试
```js
function foo() {
      console.log("foo:", this)
     }
// 1.1.测试一:apply高于默认绑定
    var obj = { foo: foo }
    obj.foo.apply("abc")
    obj.foo.call("abc")

    // 1.2.测试二:bind高于默认绑定
    var bar = foo.bind("aaa")
    var obj = {
      name: "why",
      baz: bar
    }
    obj.baz()
```

**new绑定优先级高于隐式绑定**

代码测试
```js
function foo() {
      console.log("foo:", this)
     }
// 2.new绑定优先级高于隐式绑定
    var obj = {
      name: "why",
      foo: function () {
        console.log("foo:", this)
        console.log("foo:", this === obj)
      }
    }
    new obj.foo()
```



**new绑定优先级高于bind**
new绑定和call、apply是不允许同时使用的，所以不存在谁的优先级更高new绑定可以和bind一起使用，new绑定优先级更高，且bind大于call。

代码测试
```js
function foo() {
      console.log("foo:", this)
     }
// 3.new/显式
    // 3.1. new不可以和apply/call一起使用

    // 3.2. new优先级高于bind
    function foo() {
      console.log("foo:", this)
    }
    var bindFn = foo.bind("aaa")
    new bindFn()


    // 4.bind/apply优先级
    // bind优先级高于apply/call
    function foo() {
      console.log("foo:", this)
    }
    var bindFn = foo.bind("aaa")
    bindFn.call("bbb")
```
## 3.箭头函数的this
> 箭头函数中的 this 比较特别，它和严格模式、非严格模式啥的都没关系。它和闭包很相似，都是认“死理”—— 认“词法作用域”的家伙。所以说箭头函数中的 this，和你如何调用它无关，由你书写它的位置决定（和咱们普通函数的 this 规则恰恰相反～）
回顾一下箭头函数一些特性：
- 箭头函数不会绑定this、arguments属性； 
- 箭头函数不能作为构造函数来使用（不能和new一起来使用，会抛出错误）没有prototype。

箭头函数没有自己的this，说默认绑定外层this式错误的说法，其实箭头函数的this类似于变量查找规则，这样显得箭头函数中有自己的this，本质上式符合变量查找规则。

**箭头函数中, 压根没有this**
```js
    var bar = () => {
      console.log("bar:", this)
    }
    bar() //window
    //通过apply调用时, 也是没有this
    bar.apply("aaaa") //window

    console.log("全局this:", this)
    var message = "global message"
```
**查找规则**
bar向上查找，到obj的name不是一个作用域，只是一个对象而已，所以还会继续向上查找直到找到window的this。
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
    fn.apply("bbb") //window
```
## 4.一些特殊的规则
在三种特殊情境下，this 会 100% 指向 window：

-   立即执行函数（IIFE）
-   setTimeout 中传入的函数
-   setInterval 中传入的函数

**正常显示绑定**
```js
var name = 'BigBear'

var me = {
  name: 'xiuyan',
  hello: function() {
      console.log(`你好，我是${this.name}`)
  }
}

me.hello() // 你好，我是xiuyan
```
**立即执行函数实例：**

实际上是默认绑定，找到挂载在全局作用域下的name
```js
var name = 'BigBear'

var me = {
  name: 'xiuyan',
  // 声明位置
  sayHello: function() {
    console.log(`你好，我是${this.name}`)
  },
  hello: function() {
    (function(cb) {
      // 调用位置
      cb()
    })(this.sayHello)
  }
}

me.hello() // 你好，我是BigBear
```
**setTimeout 和 setInterval传入的函数**
```js
var name = 'BigBear'

var me = {
  name: 'xiuyan',
  hello: function() {
    setTimeout(function() {
      console.log(`你好，我是${this.name}`)
    })
  }
}

me.hello() // 你好，我是BigBear
```
**以上三种特殊情况，用call/apply/bind也无法改变他们的this指向，这点倔强跟箭头函数很相似认死理。**

**立即执行函数实例**
```js
var name = 'BigBear'

var me = {
  name: 'xiuyan',
  // 声明位置
  sayHello: function() {
    console.log(`你好，我是${this.name}`)
  },
  hello: function() {
    // (function(cb) {
    //   // 调用位置
    //   cb()
    // })(this.sayHello)
    (function(){
        console.log(`你好，我是${this.name}`)
    })()
  }
}

me.hello() // 你好，我是BigBear
me.hello.call({a:1}) //你好，我是BigBear
me.hello.apply({a:1}) //你好，我是BigBear
me.hello.bind({a:1})() //你好，我是BigBear
```
**setTimeout 和 setInterval实例**
```js
var name = 'BigBear'

var me = {
  name: 'xiuyan',
  hello: function() {
    setTimeout(function() {
      console.log(`你好，我是${this.name}`)
    })
  }
}

me.hello() // 你好，我是BigBear
me.hello.call({a:1}) // 你好，我是BigBear
me.hello.apply({a:1}) // 你好，我是BigBear
me.hello.bind({a:1})() // 你好，我是BigBear
```
## 5.严格模式
use strict 是一种 ECMAscript5 添加的（严格模式）运行模式，这种模式使得 Javascript 在更严格的条件下运行。设立严格模式的目的如下：

-   消除 Javascript 语法的不合理、不严谨之处，减少怪异行为;
-   消除代码运行的不安全之处，保证代码运行的安全；
-   提高编译器效率，增加运行速度；
-   为未来新版本的 Javascript 做好铺垫。

区别：

-   禁止 this 关键字指向全局对象。
-   对象不能有重名的属性。
-   未声明的变量赋值，则会导致抛出 ReferenceError
-   严格模式不允许使用 with 语句，否则会抛出错误（影响性能）
-   未经声明就初始化变量会报错。
对函数的限制：
严格模式对函数也有一些限制：
- 函数不能以 eval 或 arguments 作为名称；
- 函数的参数不能叫 eval 或 arguments； 
- 两个命名参数不能拥有同一个名称。
如果违反上述规则，则会导致语法错误，代码也不会执行。

**ES6 模块默认在严格模式下执行。**
## 6.严格模式下一些特殊规则
严格模式下不完全所有的情况调用this都是返回undefined这个要视情况而定，不能形成固式思维

**普通函数下this指向**
```js
function showThis() {
    console.log(this)
  }
  
  showThis() // window

  'use strict'
//没有指定对象返回undefined
function showThis() {
  console.log(this)
}

showThis() // undefined
```
**全局代码中的 this 在严格模式下的表现(全局作用域下执行的函数 / 代码段里的 this)**

直接在全局代码里尝试去拿 this
```js
'use strict'
console.log(this) //window
```
setTimeout 和 setInterval等挂载在window下的方法
```js
var me = {
  name: 'xiuyan',
  hello: function() {
    // 全局作用域下实现的延时函数
    setTimeout(function() {
      console.log(`你好，我是${this.name}`)
    })
  }
}

me.hello() // 你好，我是BigBear
```
> 像这样处于全局代码中的 this， 不管它是否处于严格模式下，它的 this 都指向 Window（`这点要特别注意，区分度非常高，很多同学面试的时候会误以为这里也是 undefined `）

## 5.今日精进
# Day23【2022年8月16日】 
**学习重点：** this指向一些面试题及补充
## 1.题目一
```js
var name = "window";

var person = {
  name: "person",
  sayName: function () {
    console.log(this.name);
  }
};

function sayName() {
  var sss = person.sayName;

  sss(); // 绑定: 默认绑定, window -> window

  person.sayName(); // 绑定: 隐式绑定, person -> person

  (person.sayName)(); // 绑定: 隐式绑定, person -> person

  (b = person.sayName)(); // 术语: 间接函数引用, window -> window
}

sayName();

```
## 2.题目二
```js
var name = 'window'


// {} -> 对象
// {} -> 代码块
var person1 = {
  name: 'person1',
  foo1: function () {
    console.log(this.name)
  },
  foo2: () => console.log(this.name),
  foo3: function () {
    return function () {
      console.log(this.name)
    }
  },
  foo4: function () {
    // console.log(this) // 第一个表达式this -> person1
    // console.log(this) // 第二个表达式this -> person2
    // console.log(this) // 第三个表达式this -> person1
    
    return () => {
      console.log(this.name)
    }
  }
}

var person2 = { name: 'person2' }


// 开始题目:
person1.foo1(); // 隐式绑定: person1
person1.foo1.call(person2); // 显式绑定: person2

person1.foo2(); // 上层作用域: window
person1.foo2.call(person2); // 上层作用域: window

person1.foo3()(); // 默认绑定: window
person1.foo3.call(person2)(); // 默认绑定: window
person1.foo3().call(person2); // 显式绑定: person2

person1.foo4()(); // person1
person1.foo4.call(person2)(); // person2
person1.foo4().call(person2); // person1
```
## 3.题目三
```js
var name = 'window'

/*
  1.创建一个空的对象
  2.将这个空的对象赋值给this
  3.执行函数体中代码
  4.将这个新的对象默认返回
*/
function Person(name) {
  this.name = name
  this.foo1 = function () {
    console.log(this.name)
  },
  this.foo2 = () => console.log(this.name),
  this.foo3 = function () {
    return function () {
      console.log(this.name)
    }
  },
  this.foo4 = function () {
    return () => {
      console.log(this.name)
    }
  }
}

// person1/person都是对象(实例instance)
var person1 = new Person('person1')
var person2 = new Person('person2')


// 面试题目:
person1.foo1() // 隐式绑定: person1
person1.foo1.call(person2) // 显式绑定: person2

person1.foo2() // 上层作用域查找: person1
person1.foo2.call(person2) // 上层作用域查找: person1

person1.foo3()() // 默认绑定: window
person1.foo3.call(person2)() // 默认绑定: window
person1.foo3().call(person2) // 显式绑定: person2

person1.foo4()() // 上层作用域查找: person1(隐式绑定)
person1.foo4.call(person2)() //  上层作用域查找: person2(显式绑定)
person1.foo4().call(person2) // 上层作用域查找: person1(隐式绑定)
```
## 4.题目四
```js
var name = 'window'

/*
  1.创建一个空的对象
  2.将这个空的对象赋值给this
  3.执行函数体中代码
  4.将这个新的对象默认返回
*/
function Person(name) {
  this.name = name
  this.obj = {
    name: 'obj',
    foo1: function () {
      return function () {
        console.log(this.name)
      }
    },
    foo2: function () {
      return () => {
        console.log(this.name)
      }
    }
  }
}

var person1 = new Person('person1')
var person2 = new Person('person2')

person1.obj.foo1()() // 默认绑定: window
person1.obj.foo1.call(person2)() // 默认绑定: window
person1.obj.foo1().call(person2) // 显式绑定: person2

person1.obj.foo2()() // 上层作用域查找: obj(隐式绑定)
person1.obj.foo2.call(person2)() // 上层作用域查找: person2(显式绑定)
person1.obj.foo2().call(person2) // 上层作用域查找: obj(隐式绑定)
```
## 5.面试题五
```js
// {} -> 对象
// {} -> 代码块
var a = 1
var obj = {
  a: 2,
  func2: () => {
    console.log(this.a)
  },
  
  func3: function() {
    console.log(this.a)
  }
}

// func1
var func1  = () => {
  console.log(this.a)
}

// func2
var func2 = obj.func2
// func3
var func3 = obj.func3

func1() // 1
func2() ///1
func3() //1
obj.func2() // 1
obj.func3() //2 不是箭头函数，是普通函数，所以this指向的是obj 显示调用
```
## 6.今日精进
接触了产品运营及解决方案架构层面，打开了自身认知，改变了之前的纯想靠技术吃饭，一技术到头的思维。技术只是基石，吃香只是短期只能保你一时，要想持续保持竞争力，关键是跳出技术寻求突破，上升到产品、管理、销售、商业层。程序员带来的商业价值才是其存在的意义，一旦失去商业价值未来随时可被替代。所以技术不是核心，关键是技术背后帮助企业实现的商业之道。

# Day24【2022年8月17日】-Day28【2022年8月21日】
**外出**
## 精进
利他，就是最好的利己。利他的前提是先做好自己，有余力了再利他。利他类似一种投资行为，很难保证所有投资都有回报，但有时候一个不经意的小项目也许会给带来巨大的收益。
# 参考资料
-   JavaScript高级程序设计（第4版）
-  [MDN](https://developer.mozilla.org/en-US/)
-  某知名大神的资料
#  结语

志同道合的小伙伴可以加我，一起交流进步，我们坚持每日精进（互相监督思考学习，如果坚持不下来我可以监督你）。另外共享学习资料的小伙伴也可以联系我，进群技术交流资料free共享，我们交换资料一起努力鸭！
——>[点击这里](https://juejin.cn/pin/7123425224455880740)

# 备注
按照时间顺序倒叙排列，完结后按时间顺序正序排列方便查看知识点,工作日更新。