---
theme: juejin
highlight: tomorrow
---

大家好我是牛哥，时间过得很快转眼间，已经更文挑战半个月了，前期有把时间浪费在一些不必要的内容上，接下来会好好梳理一下要学习的内容，尽量做道不失细节又通俗易懂。这周思考了一下，学习不仅仅要是学习知识点这些单纯表面的东西，更重要的是在思维层面，掌握道层面，这样学起任何东西来才会快，如果仅仅是停留在知识点表面，那并没有达到真正的学习目的。还要一个很重要的点，一定要多练习，实践出真知。废话不多说接下来开始我们这周的学习吧！


这里同步会更慢一些，实时更新可以到我[github](https://github.com/xiaoniuge36/ng-learning-for-1024-days)（二者同步）
# Day15【2022年8月8日】 
**学习重点：** 面向对象
## 1.什么是面向对象
> 面向对象程序设计（英语：Object-oriented programming，缩写：OOP）是种具有对象概念的编程典范，同时也是一种程序开发的抽象方针。它可能包含数据、特性、代码与方法。对象则指的是类（class）的实例。它将对象作为程序的基本单元，将程序和数据封装其中，以提高软件的重用性、灵活性和扩展性，对象里的程序可以访问及经常修改对象相关连的数据。在面向对象程序编程里，计算机程序会被设计成彼此相关的对象。

面向对象的三打特性：封装（将方法和属性封装到一个对象中，对外提供方法用于改变该对象的属性值）、继承（子类可以继承父类的方法和属性,实现重用代码，节省开发时间）、多态（指不同对象接收到同一消息时会产生不同的行为，一个接口，多种方法。）
简单来说万物皆对象，世界上的任何事和物都可以被视为对象，而我们需要关注的是对象本身可以实现的功能，不需要深入理解构成对象的元素。这是一个抽象的概念。
对象的概念还可以从两个层次来理解：
> 对象是单个事物的抽象
> 一本书、一辆汽车、一个人都可以是对象，一个数据库、一张网页、一个与远程服务器的连接也可以是对象。当实物被抽象成对象，实物之间的关系就变成了对象之间的关系，从而就可以模拟现实情况，针对对象进行编程。
> 
> 对象是一个容器，封装了属性(property)和方法(method)
> 属性是对象的状态，方法是对象的行为（完成某种任务）。比如，我们可以把动物抽象为animal对象，使用“属性”记录具体是那一种动物，使用“方法”表示动物的某种行为（奔跑、捕猎、休息等等）
> 在实际开发中，对象是一个抽象的概念，可以将其简单理解为 : 数据集或功能集。
## 2.创建对象的方式
### 2.1对象字面量：通过{}
```js
var person = {
    name: '张三',
    age: 18,
    };
    console.log(person.name);
```
### 2.2new Object+动态添加属性
```js
var person = new Object();
    person.name = '张三';
    person.age = 18;
    console.log(person.name);
```
以上两种方法在使用同一接口创建多个对象时，会产生大量重复代码，为了解决此问题，工厂模式被开发。
### 2.3工厂模式创建对象
工厂模式的主要工作原理是用函数来封装创建对象的细节，从而通过调用函数来达到复用的目的。但是它有一个很大的问题就是创建出来的对象无法和某个类型联系起来，它只是简单的封装了复用代码，而没有建立起对象和类型间的关系。
```js
//工厂模式创建对象
function createPerson(name, age) {
    var obj = new Object();
    obj.name = name;
    obj.age = age;
    return obj;
}
var person = createPerson('张三', 18);
console.log(person.name);
console.log(person.age);
```
工厂模式解决了重复实例化多个对象的问题，但没有解决对象识别的问题。
### 2.4构造函数创建对象
> js 中每一个函数都可以作为构造函数，只要一个函数是通过 new 来调用的，那么就可以把它称为构造函数。执行构造函数首先会创建一个对象，然后将对象的原型指向构造函数的 prototype 属性，然后将执行上下文中的 this 指向这个对象，最后再执行整个函数，如果返回值不是对象，则返回新建的对象。因为 this 的值指向了新建的对象，因此可以使用 this 给对象赋值。构造函数模式相对于工厂模式的优点是，所创建的对象和构造函数建立起了联系，因此可以通过原型来识别对象的类型。但是构造函数存在一个缺点就是，造成了不必要的函数对象的创建，因为在 js 中函数也是一个对象，因此如果对象属性中如果包含函数的话，那么每次都会新建一个函数对象，浪费了不必要的内存空间，因为函数是所有的实例都可以通用的。
```js
//构造函数创建对象
function Person(name, age) {
    this.name = name;
    this.age = age;
}
var person = new Person('张三', 18);
console.log(person.name);
console.log(person.age);
```
构造函数也有其缺陷，每个实例都包含不同的Function实例（ 构造函数内的方法在做同一件事，但是实例化后却产生了不同的对象，方法是函数 ，函数也是对象）因此产生了原型模式
### 2.5原型模式创建对象
每一个函数都有一个 prototype 属性，这个属性是一个对象，它包含了通过构造函数创建的所有实例都能共享的属性和方法。因此可以使用原型对象来添加公用属性和方法，从而实现代码的复用。这种方式相对于构造函数模式来说，解决了函数对象的复用问题。但是这种模式也存在一些问题，一个是没有办法通过传入参数来初始化值，另一个是如果存在一个引用类型如 Array 这样的值，那么所有的实例将共享一个对象，一个实例对引用类型值的改变会影响所有的实例。
```js
//原型模式创建对象
function Person() {

}
Person.prototype.name = '张三';
Person.prototype.age = 18;
var person = new Person();
console.log(person.name);
console.log(person.age);
```
### 2.6 组合使用构造函数模式和原型模式
这是创建自定义类型的最常见方式。因为构造函数模式和原型模式分开使用都存在一些问题，因此可以组合使用这两种模式，通过构造函数来初始化对象的属性，通过原型对象来实现函数方法的复用。这种方法很好的解决了两种模式单独使用时的缺点，但是有一点不足的就是，因为使用了两种不同的模式，所以对于代码的封装性不够好。
```js
//构造函数和原型模式创建对象
function Person(name,age,family){
    this.name = name;
    this.age = age;
    this.family = family;
}

Person.prototype = {
    constructor: Person,  //每个函数都有prototype属性，指向该函数原型对象，原型对象都有constructor属性，这是一个指向prototype属性所在函数的指针
    say: function(){
        alert(this.name);
    }
}

var person1 = new Person("lisi",21,["lida","lier","wangwu"]);
console.log(person1);
var person2 = new Person("wangwu",21,["lida","lier","lisi"]);
console.log(person2);
```
可以看出，混合模式共享着对相同方法的引用，又保证了每个实例有自己的私有属性。最大限度的节省了内存。

### 2.7动态原型模式
这一种模式将原型方法赋值的创建过程移动到了构造函数的内部，通过对属性是否存在的判断，可以实现仅在第一次调用函数时对原型对象赋值一次的效果。这一种方式很好地对上面的混合模式进行了封装。
```js
function Person(name, age, job){
 
    //属性
    this.name = name;
    this.age = age;
    this.job = job;
 
    //方法
    if (typeof this.sayName != "function"){
 
        Person.prototype.sayName = function(){
            alert(this.name);
        };
 
    }
}
 
var friend = new Person("Nicholas", 29, "Software Engineer");
friend.sayName();
```

### 2.8寄生构造函数模式
这一种模式和工厂模式的实现基本相同，我对这个模式的理解是，它主要是基于一个已有的类型，在实例化时对实例化的对象进行扩展。这样既不用修改原来的构造函数，也达到了扩展对象的目的。它的一个缺点和工厂模式一样，无法实现对象的识别。
```js
function Person (name, sex, age) {
  this.name = name
  this.sex = sex
  this.age = age
  this.sayName = function () {
    console.log(this.name)
  }
}
const p1 = new Person('windy-boy', 'male', '18')
console.log(p1) // Person {name: "windy-boy", sex: "male", age: "18", sayName: ƒ}
```

## 3.类
以上创建对象的方式就是创建类（es5）
类是“特殊的函数”，就像你能够定义的函数表达式和函数声明一样，类语法有两个组成部分：类表达式和类声明。Es6 新增的类很大程度上是基于既有原型机制的语法糖。
类和构造函数的含义是基本相同的，创建方法相似。都可以用类或者构造函数创建对象。
创建类：
```js
```
```js
//es6类的实现
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    sayName() {
        console.log(this.name);
    }
}
var person = new Person('张三', 18);
person.sayName();
```
## 4.对象继承的方式
### 4.1 es6 extends继承
ES6 中的 extends语法，在内部实现继承时，使用的是寄生组合式继承。
```js
// es6类的继承  extends super class 
class Student extends Person {
    constructor(name, age, grade) {
        super(name, age);
        this.grade = grade;
    }
    sayGrade() {
        console.log(this.grade);
    }
}
var student = new Student('张三', 18, '一年级');
student.sayName();
student.sayGrade();
```
extends 关键字也可以在类表达式中使用，因此 let Bar = class extends Foo {}是有效的语法。
### 4.2 原型链继承
这种实现方式存在的缺点是，在包含有引用类型的数据时，会被所有的实例对象所共享，容易造成修改的混乱。还有就是在创建子类型的时候不能向超类型传递参数。
```js
//原型继承
function Parent() {
   this.isShow = true
   this.info = {
       name: "mjy",
       age: 18,
   };
}

Parent.prototype.getInfo = function() {
   console.log(this.info);
   console.log(this.isShow);
}

function Child() {};
Child.prototype = new Parent();

let Child1 = new Child();
Child1.info.gender = "男";
Child1.getInfo(); // {name: 'mjy', age: 18, gender: '男'} ture

let child2 = new Child();
child2.isShow = false
console.log(child2.info.gender) // 男
child2.getInfo(); // {name: 'mjy', age: 18, gender: '男'} false
```
### 4.3 构造函数继承
通过在子类型的函数中调用超类型的构造函数来实现的，这一种方法解决了不能向超类型传递参数的缺点，但是它存在的一个问题就是无法实现函数方法的复用，并且超类型原型定义的方法子类型也没有办法访问到。
```js
function Parent(gender) {
  this.info = {
    name: "yhd",
    age: 19,
    gender: gender
  }
}

function Child(gender) {
    Parent.call(this, gender)
}

let child1 = new Child('男');
child1.info.nickname = 'xiaoma'
console.log(child1.info);

let child2 = new Child('女');
console.log(child2.info);

```
### 4.4 组合继承
组合继承是将原型链和借用构造函数组合起来使用的一种方式。通过借用构造函数的方式来实现类型的属性的继承，通过将子类型的原型设置为超类型的实例来实现方法的继承。这种方式解决了上面的两种模式单独使用时的问题，但是由于我们是以超类型的实例来作为子类型的原型，所以调用了两次超类的构造函数，造成了子类型的原型中多了很多不必要的属性。
```js
function Person(gender) {
  console.log('执行次数');
  this.info = {
    name: "mjy",
    age: 19,
    gender: gender
  }
}

Person.prototype.getInfo = function () {   // 使用原型链继承原型上的属性和方法
  console.log(this.info.name, this.info.age)
}

function Child(gender) {
  Person.call(this, gender) // 使用构造函数法传递参数
}

Child.prototype = new Person()

let child1 = new Child('男');
child1.info.nickname = 'xiaoma'
child1.getInfo()
console.log(child1.info);

let child2 = new Child('女');
console.log(child2.info);

```
### 4.5 原型式继承
型式继承的主要思路就是基于已有的对象来创建新的对象，实现的原理是，向函数中传入一个对象，然后返回一个以这个对象为原型的对象。这种继承的思路主要不是为了实现创造一种新的类型，只是对某个对象实现一种简单继承，ES5 中定义的 Object.create() 方法就是原型式继承的实现。缺点与原型链方式相同。
```js
//构造函数形式
function createObject(obj) {
  function Fun() {}
  Fun.prototype = obj
  return new Fun()
}

let person = {
  name: 'mjy',
  age: 18,
  hoby: ['一年', '男'],
  showName() {
    console.log('my name is:', this.name)
  }
}

let child1 = createObject(person)
child1.name = 'xxxy'
child1.hoby.push('r')
let child2 = createObject(person)

console.log(child1)
console.log(child2)
console.log(person.hoby) // ['一年', '男', 'r']
//Object.create()原型式继承
var person = {
    name: '张三',
    age: 18,
    sayName: function () {
        console.log(this.name);
    }
}
var student = Object.create(person);
student.sayName();
```
### 4.6 寄生式继承
寄生式继承的思路是创建一个用于封装继承过程的函数，通过传入一个对象，然后复制一个对象的副本，然后对象进行扩展，最后返回这个对象。这个扩展的过程就可以理解是一种继承。这种继承的优点就是对一个简单对象实现继承，如果这个对象不是自定义类型时。缺点是没有办法实现函数的复用。
```js
function objectCopy(obj) {
        function Fun() { };
        Fun.prototype = obj;
        return new Fun();
      }
      
      function createAnother(obj) {
        let clone = objectCopy(obj);
        clone.showName = function () {
          console.log('my name is：', this.name);
        };
        return clone;
      }
      
      let person = {
           name: "mjy",
           age: 18,
           hobby: ['一年级', '男']
      }
      
      let child1 = createAnother(person);
      child1.hobby.push("篮球");
      console.log(child1.hobby); // ['一年级', '男', '篮球']
      child1.showName(); // my name is： mjy
      
      let child2 = createAnother(person);
      console.log(child2.hobby); // ['一年级', '男']


````
### 4.7 寄生组合式继承
组合继承的缺点就是使用超类型的实例做为子类型的原型，导致添加了不必要的原型属性。寄生式组合继承的方式是使用超类型的原型的副本来作为子类型的原型，这样就避免了创建不必要的属性。
```js
//寄生组合继承实现
function createObject(obj) {
    function Fun() {}
    Fun.prototype = obj
    return new Fun()
  }

    function inheritPrototype(subType, superType) {
        var prototype = Object.create(superType.prototype)
        prototype.constructor = subType
        subType.prototype = prototype
    }
    function Person(name, age) {
        this.name = name;
        this.age = age;
    }
    Person.prototype.sayName = function () {
        console.log(this.name);
    }
    function Student(name, age, grade) {
        Person.call(this, name, age);
        this.grade = grade;
    }
    inheritPrototype(Student, Person)
    Student.prototype.sayGrade = function () {
        console.log(this.grade);
    }
    var student = new Student('张三', 18, '一年级');
    student.sayName();
    student.sayGrade();
```

继承详解好文推荐[点击这里](https://juejin.cn/post/6844903696111763470)
## 今日精进
人在逆境时才是修心处，不遇到便无法开悟。
# Day16【2022年8月9日】 
**学习重点：** 事件
## 1.事件流
- 事件流：描述的是事件在页面中传播的顺序
- 事件：它描述的是发生在浏览器里的动作。这个动作可以是用户触发的，也可以是浏览器触发的。像点击（click）、鼠标悬停（mouseover）、鼠标移走（mousemove）这些都是事件。
- 事件监听函数：事件发生后，浏览器如何响应——用来应答事件的函数，就是事件监听函数，也叫事件处理程序。常见事件监听方式：在script中直接监听（用的少）；DOM属性，通过元素的on来监听事件；通过EventTarget中的addEventListener来监听。
## 2.事件冒泡
默认情况下事件是从最内层的向外依次传递的顺序，这个顺序称之为事件冒泡（Event Bubble）;
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件冒泡</title>
</head>
<body>
    <div id="div1" style="width: 100px; height: 100px; background-color: blue;"></div>
    <script>
        let divEl = document.querySelector("#div1");
        let bodyEl = document.body;
        let htmlEl = document.documentElement;
        divEl.addEventListener("click", function(event) {
            alert("div被点击~");
            console.log("div1被点击");
        });
        bodyEl.addEventListener("click", function(event) {
            alert("body被点击~");
            console.log("body被点击");
        });
        htmlEl.addEventListener("click", function(event) {
            alert("html被点击~");
            console.log("html被点击");
        });
    </script>
</body>
</html>
```
**执行结果：**

<img src="https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d742b69d18b44a40a6912d1bb0aea221~tplv-k3u1fbpfcp-watermark.image?" alt="微信图片_20220809094242.png" width="30%" />

也就是说，div元素，即被点击的元素，最先触发 click 事件。然后，click 事件沿 DOM 树一
路向上，在经过的每个节点上依次触发，直至到达 document 对象。
<img src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/e687f8ba34164f2292926e2298d77c9d~tplv-k3u1fbpfcp-watermark.image?" alt="微信图片_20220809094521.png" width="70%" />

## 3.事件捕获
事件流的方式就是从外层到内层，这种称之为事件捕获（Event Capture），要设置addEventListener第三个元素为true才可以捕获到，否则捕获不到。
**如下所示**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>事件捕获</title>
</head>
<body>
    <div id="div1" style="width: 100px; height: 100px; background-color: blue;"></div>
    <script>
        let divEl = document.querySelector("#div1");
        let bodyEl = document.body;
        let htmlEl = document.documentElement;
        divEl.addEventListener("click", function(event) {
            alert("div被点击~");
            console.log("div1被点击");
        }, true);
        bodyEl.addEventListener("click", function(event) {
            alert("body被点击~");
            console.log("body被点击");
        },true);
        htmlEl.addEventListener("click", function(event) {
            alert("html被点击~");
            console.log("html被点击");
        },true);
    </script>
</body>
</html>
````
<img src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/abc9479b8c1d4fcea1c4704bba1380e0~tplv-k3u1fbpfcp-watermark.image?" alt="微信图片_20220809095304.png" width="30%" />

实际当中几乎不会使用事件捕获。通常建议使用事件冒泡，特殊情
况下可以使用事件捕获。
**具体如下图所示**

<img src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/6465da83457d4cde886cd6427cca419c~tplv-k3u1fbpfcp-watermark.image?" alt="微信图片_20220809095103.png" width="70%" />

## 4.完整DOM事件流
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM事件</title>
</head>
<body>
    <div id="div1" style="width: 100px; height: 100px; background-color: blue;"></div>
    <script>
        let divEl = document.querySelector("#div1");
        let bodyEl = document.body;
        let htmlEl = document.documentElement;
        divEl.addEventListener("click", function(event) {
            alert("div被点击~");
            console.log("div1被点击");
        });
        bodyEl.addEventListener("click", function(event) {
            alert("body被点击~");
            console.log("body被点击");
        });
        htmlEl.addEventListener("click", function(event) {
            alert("html被点击~");
            console.log("html被点击");
        });
        divEl.addEventListener("click", function(event) {
            alert("div被点击~");
            console.log("div1被点击");
        }, true);
        bodyEl.addEventListener("click", function(event) {
            alert("body被点击~");
            console.log("body被点击");
        },true);
        htmlEl.addEventListener("click", function(event) {
            alert("html被点击~");
            console.log("html被点击");
        },true);
    </script>
</body>
</html>
```
**执行结果**

<img src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/689135ba36174dfca32554eda249b9ce~tplv-k3u1fbpfcp-watermark.image?" alt="微信图片_20220809100504.png" width="30%" />

**流程图**

<img src="https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/5cea6fcf11634b7bac09c29d0bf34a48~tplv-k3u1fbpfcp-watermark.image?" alt="微信图片_20220809100829.png" width="70%" />


<img src="https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/40b5b88df1ef4a3eb90bd357d109af13~tplv-k3u1fbpfcp-watermark.image?" alt="微信图片_20220809100958.png" width="70%" />

执行顺序：
- 捕获阶段（Capturing phase）： 事件（从 Window）向下走近元素。
- 目标阶段（Target phase）： 事件到达目标元素。
- 冒泡阶段（Bubbling phase）： 事件从元素上开始冒泡。
还可以可以通过event对象来获取当前的阶段：eventPhase.

**开发中通常会使用事件冒泡，所以事件捕获了解即可。**
## 5.事件对象
在 DOM 中发生事件时，所有相关信息都会被收集并存储在一个名为 event 的对象中。这个对象包
含了一些基本信息，比如导致事件的元素、发生的事件类型，以及可能与特定事件相关的任何其他数据。

常用的事件对象有type（事件的类型）、target（当前事件发生的元素）、currentTarget（当前处理事件的元素）。
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>事件对象</title>
  <style>
    body {
      padding: 20px;
    }

    .box {
      width: 100px;
      height: 100px;
      background-color: red;
    }
  </style>
</head>
<body>

  <div class="box"></div>
  <script>

    var boxEl = document.querySelector(".box")
    boxEl.addEventListener("click", function(event) {
      console.log(event);
      
      console.log(this === event.target); // this指向事件的目标元素 event.target指向事件的目标元素 
    })
    // boxEl.addEventListener("click",function(e) {
    //   console.log(e);
    //   console.log(this === e.target); // true 
    // });
  </script>

</body>
</html>
```
## 6.事件代理（事件委托）
事件委托利用事件冒泡，可以只使用一个事件处理程序来管理一种类型的事件。

事件委托模式也是一种设计模式

**实现：**

当子元素被点击时，父元素可以通过冒泡可以监听到子元素的点击；并且可以通过event.target获取到当前监听的元素。

**例子：** 如下所示希望点击以此每一个li都能输出一次，可以利用冒泡事件的事件代理进行处理
```js
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>事件委托</title>
</head>
<body>
  <ul id="poem">
    <li>鹅鹅鹅</li>
    <li>曲项向天歌</li>
    <li>白毛浮绿水</li>
    <li>红掌拨清波</li>
    <li>锄禾日当午</li>
    <li>汗滴禾下土</li>
    <li>谁知盘中餐</li>
    <li>粒粒皆辛苦</li>
    <li>背不动了</li>
    <li>我背不动了</li>
  </ul>
  <script>
    //事件委托
    var poem = document.querySelector("#poem");
    poem.addEventListener("click", function(event) {
      console.log(event.target.innerHTML);
    });
  </script>
</body>
</html>
```
## 7.今日精进
万事随缘，顺其自然。这是中庸的生活。 逆流而上，见机行事。方能活出人生精彩。 每个人都有属于自己的生活方式。
# Day17【2022年8月10日】 
**学习重点：**  ES6模块与CommonJS模块
## 1. ES6模块与CommonJS模块
### 1.1CommonJS模块
CommonJS 规范概述了同步声明依赖的模块定义。这个规范主要用于在服务器端实现模块化代码组织，但也可用于定义在浏览器中使用的模块依赖。CommonJS 模块语法不能在浏览器中直接运行。一般运用于node一般认为，Node.js的模块系统使用了CommonJS规范，实际上并不完全正确。Node.js使用了轻微修改版本的 CommonJS，因为 Node.js 主要在服务器环境下使用，所以不需要考虑网络延迟问题。

**浏览器中使用：**
> CommonJS 依赖几个全局属性如 require 和 module.exports。如果想在浏览器中使用 CommonJS
> 模块，就需要与其非原生的模块语法之间构筑“桥梁”。模块级代码与浏览器运行时之间也需要某种“屏
> 障”，因为没有封装的 CommonJS 代码在浏览器中执行会创建全局变量。这显然与模块模式的初衷相悖。
> 常见的解决方案是提前把模块文件打包好，把全局属性转换为原生 JavaScript 结构，将模块代码封
> 装在函数闭包中，最终只提供一个文件。为了以正确的顺序打包模块，需要事先生成全面的依赖图。

**实例：**

**commonjs导出**
```js
//test8.js
//定义commonjs模块
//拷贝 
function add(x, y) {
    return x + y;
};

function sub(x, y) {
    return x - y;
}


//分别导出
// exports.add = add;
// exports.sub = sub;

//统一导出
module.exports = {
    add,
    sub,
    a:1,
    a1:2,
    a2:2
    // add: add,
    // sub: sub
}
```
**commonjs导入**
```js
//test9.js 导入test8.js
//分别导入 add 和 sub
var test8 = require('./test8');
//统一导入
var {add , sub } = require('./test8');
//可同时用两种方式导入
var {add:add1, sub:sub1 ,a } = require('./test8');
//
console.log(add(1, 2));
console.log(sub(1, 2));

console.log(test8.add(1, 2));
console.log(test8.sub(1, 2));

console.log(add1(1, 2));
console.log(sub1(1, 2));
console.log(a);

// 无论一个模块在 require()中被引用多少次，模块永远是单例。在下面的例子中，moduleA 只会
// 被打印一次。这是因为无论请求多少次，moduleA 只会被加载一次。
console.log('moduleA'); 
var a1 = require('./test8'); 
var a2 = require('./test8'); 
console.log(a1 === a2); // true
```
由此可见分别导出可对应统一导入/分别导入，统一导入也可对应分别导入和统一导入，使用起来非常灵活。
### 1.2ES6 Module模块
每个模块只能有一个默认导出。重复的默认导出会导致 SyntaxError。

> ECMAScript 6 模块的独特之处在于，既可以通过浏览器原生加载，也可以与第三方加载器和构建工
> 具一起加载。有些浏览器还没有原生支持 ES6 模块，因此可能还需要第三方工具。事实上，很多时候使
> 用第三方工具可能会更方便。
> 
> 完全支持 ECMAScript 6 模块的浏览器可以从顶级模块加载整个依赖图，且是异步完成的。浏览器
> 会解析入口模块，确定依赖，并发送对依赖模块的请求。这些文件通过网络返回后，浏览器就会解析它
> 们的内容，确定它们的依赖，如果这些二级依赖还没有加载，则会发送更多请求。这个异步递归加载过
> 程会持续到整个应用程序的依赖图都解析完成。解析完依赖图，应用程序就可以正式加载模块了。
> 
> 这个过程与 AMD 风格的模块加载非常相似。模块文件按需加载，且后续模块的请求会因为每个依
> 赖模块的网络延迟而同步延迟。即，如果 moduleA 依赖 moduleB，moduleB 依赖 moduleC。浏览器在
> 对 moduleB 的请求完成之前并不知道要请求 moduleC。这种加载方式效率很高，也不需要外部工具，
> 但加载大型应用程序的深度依赖图可能要花费很长时间。

**ES6 模块支持两种导出：命名导出和默认导出。不同的导出方式对应不同的导入方式**
**因为命名导出和默认导出不会冲突，所以 ES6 支持在一个模块中同时定义这两种导出**

**ES6 模块导出**
```js
// ES6模块导出
function add(x, y) {
    return x + y;
};

function sub(x, y) {
    return x - y;
}


// 默认导出一个
// export default add;

console.log(this); // undefined

//命名导出
//最好声明和导出分开
export { add , sub  } ;
export { add as add1, sub as sub1 };
export const a = 1;
const b = 2;
export { b };
export { a as a1, b as b1 };
export function test() {
    console.log('默认导出函数');
}

//默认导出只能有一个重复的默认导出会导致 SyntaxError。

//默认导出一个
// export default add;
//默认导出多个
const c =2;
export default {
    add,
    sub,
    c
}
// 等同于 export default foo; 
//export { foo as default };
//二者可以同时使用
//常见的错误 先复制再导出不容易出错
// 会导致错误的不同形式：
// 行内默认导出中不能出现变量声明
//export default const foo = 'bar'; 
// 只有标识符可以出现在 export 子句中(要先赋值)
//export { 123 as foo } 
// 别名只能在 export 子句中出现
//export const foo = 'foo' as myFoo;

```
**ES6 模块导入**
```js
//ES6 导入
//命名导入
//命名导出可以使用*批量获取并赋值给保存导出集合的别名，而无须列出每个标识符：
import { add as add2, sub as sub2 } from './test10.js';
// import { add , sub as sub2 } from './test10.js';
console.log(add(1, 2));
console.log(sub2(1, 2));

import * as test10 from './test10.js';
console.log(test10.add(1, 2));
console.log(test10.sub(1, 2));
console.log(test10.a);




// 默认导入
import test100 from './test10.js';
console.log(test100.c);

import {default as test101} from './test10.js';//与上面的区别是，这里使用了别名 等价
console.log(test101.c);

//同时使用默认导入和命名导入
import test102, { add as add3, sub as sub3 } from './test10.js';
console.log(add3(1, 2));
console.log(sub3(1, 2));
console.log(test102.a); //不存在返回undefined
console.log(test102.c);

import{default as test103, add , sub as sub4} from './test10.js';
console.log(add(1, 2));
console.log(sub4(1, 2));
console.log(test103.c);
import test104, * as test105 from './test10.js';
console.log(test104.c);
console.log(test105.a);
console.log(test105.a);


```
ECMAScript 6 模块借用了 CommonJS 和 AMD 的很多优秀特性。下面简单列举一些。
- 模块代码只在加载后执行。
- 模块只能加载一次。
- 模块是单例。
- 模块可以定义公共接口，其他模块可以基于这个公共接口观察和交互。
- 模块可以请求加载其他模块。
- 支持循环依赖。

**ES6 模块系统也增加了一些新行为。**

- ES6 模块默认在严格模式下执行。
- ES6 模块不共享全局命名空间。
- 模块顶级 this 的值是 undefined（常规脚本中是 window）。
- 模块中的 var 声明不会添加到 window 对象。
- ES6 模块是异步加载和执行的。

ES6 Module和CommonJS模块的区别：

-   CommonJS是对模块的浅拷⻉，ES6 Module是对模块的引⽤，即ES6 Module只存只读，不能改变其值，也就是指针指向不能变，类似const；
-   import的接⼝是read-only（只读状态），不能修改其变量值。 即不能修改其变量的指针指向，但可以改变变量内部指针指向，可以对commonJS对重新赋值（改变指针指向），但是对ES6 Module赋值会编译报错。

> 浏览器运行时在知道应该把某个文件当成模块时，会有条件地按照上述 ECMAScript 6 模块行为来施
> 加限制。与script type="module"关联或者通过 import 语句加载的 JavaScript 文件会被认定为模块。
> 共同点：

-   CommonJS和ES6 Module都可以对引⼊的对象进⾏赋值，即对对象内部属性的值进⾏改变。

## 2.今日精进
心态很重要，心是一块田，种什么因、得什么果。凡事想开、看开、放下、学会释怀，没有必要拿别人的闲言碎语，来惩罚自己。背后的评论你若是在意了，证明你也落入别人的圈套了。

# Day18【2022年8月11日】 
**学习重点：**  解构赋值和扩展运算符（浅拷贝）
## 1. 解构赋值
解构赋值是对赋值运算符的扩展。是一种针对数组或者对象进行模式匹配，然后对其中的变量进行赋值。在代码书写上简洁且易读，语义更加清晰明了；也方便了复杂对象中数据字段获取。

### 1.1数组结构解析
```js
//数组模型的解构
var [a, b, c] = [1, 2, 3];
console.log(a, b, c); //1 2 3
//数组的解构赋值嵌套
var [a, [b, c]] = [1, [2, 3]];
console.log(a, b, c); //1 2 3
//数组的解构赋值忽略元素
var [a, , b] = [1, 2, 3];
console.log(a, b); //1 3
//数组的解构赋值不完全解构
var [a, [b]] = [1, [2, 3]];
console.log(a, b); //1 2
//数组的解构赋值和扩展运算符
var [a, b, ...c] = [1, 2, 3, 4, 5];
console.log(a, b, c); //1 2 [3,4,5]
//数组的解构赋值字符串
var [a, b, c] = 'hello';
console.log(a, b, c); //h e l l o
//数组的解构赋值和函数参数的解构赋值
var [a, b] = move({ x: 3, y: 1 });
console.log(a, b); //3 1
```
### 1.2对象结构解析
```js
//对象模型的解构
var { foo, bar } = { foo: 'aaa', bar: 'bbb' };
console.log(foo, bar);  //aaa bbb
//对象的解构赋值可嵌套
var { foo: { bar } } = { foo: { bar: 'baz' } };
console.log(bar); //baz
//对象的结构解析可忽略属性
var { foo, bar, baz = 'default' } = { foo: 'aaa', bar: 'bbb' };
console.log(foo, bar, baz); //aaa bbb default
//对象的结构解析不完全解构
var obj = {p: [{y: 'world'}] };
var {p: [{ y }, x ] } = obj;
console.log(x, y); //world 3
//对象的解构赋值和扩展运算符
let {a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40};
console.log(a, b, rest); //10 20 {c: 30, d: 40}
```
### 1.3对象结构解析和数组结构解析一些区别

数组的解构赋值是先将数组赋值给一个变量，然后再对该变量解构。

对象的解构赋值是先将对象赋值给一个变量，然后再对该变量解构。

对象的解构赋值和数组的解构赋值的用法有些类似，但是数组的解构赋值是为了获取数组的成员，而对象的解构赋值是为了获取对象的属性。

数组的解构赋值的内部机制，是先找到数组的最后一项，将它的值赋给变量，然后再删除该数组最后一项。

对象的解构赋值的内部机制，是先找到名称与变量同名的属性，将它的值赋给变量，然后再删除该对象的该属性。

### 1.4函数结构解析
```js
//函数参数的解构赋值
function add([x, y]) {
    return x + y;
}
console.log(add([1, 2])); //3
//函数参数的解构赋值
function move({ x = 0, y = 0 } = {}) {
    return [x, y];
}
console.log(move({ x: 3, y: 8 }));  //[3, 8]
console.log(move({ x: 3 })); //[3, 0]
console.log(move({})); //[0, 0]
console.log(move()); //[0, 0]
```
### 1.5默认结构解析
```js
//解构赋值的默认值对象
var { foo = 'aaa' } = {}; 
console.log(foo); //aaa
var { foo = 'aaa' } = { foo: 'bbb' };
console.log(foo); //bbb
var { foo = 'aaa' } = {};
console.log(foo); //aaa
var { foo = 'aaa' } = { foo: undefined };
console.log(foo); //aaa 遇到undefined就用默认值
var { foo = 'aaa' } = { foo: null };
console.log(foo); // 遇到null就用null
var { foo = 'aaa' } = { foo: NaN };
console.log(foo); //NaN 遇到NaN就用NaN
var { foo = 'aaa' } = { foo: true };
console.log(foo); //true 遇到true就用true
var { foo = 'aaa' } = { foo: false };
console.log(foo); //false 遇到false就用false
var { foo = 'aaa' } = { foo: 0 };
console.log(foo); //0 遇到0就用0
var { foo = 'aaa' } = { foo: '' };
console.log(foo); //'' 遇到空字符串就用空字符串

//解析赋值的默认值数组
var [a, b = 'bbb'] = [1];
console.log(a, b); //1 bbb
var [a, b = 'bbb'] = [1, 2];
console.log(a, b); //1 2
var [a, b = 'bbb'] = [1, undefined];
console.log(a, b); //1 bbb
var [a, b = 'bbb'] = [1, null];
console.log(a, b); //1 null
var [a, b = 'bbb'] = [1, NaN];
console.log(a, b); //1 NaN
```
## 2.扩展运算符
> 扩展语法( ...) 允许在需要零个或多个参数（用于函数调用）或元素（用于数组字面量）的地方扩展可迭代对象，例如数组或字符串。在对象字面量中，扩展语法枚举对象的属性并将键值对添加到正在创建的对象中。
> 
> 扩展语法看起来与解析语法完全一样。在某种程度上，展开语法与解析语法相反。扩展语法将数组“扩展”为它的元素，而解析语法收集多个元素并将它们“压缩”为单个元素。

由此可以看出两者是完全相反的操作。
```js
let [a, b, ...rest] = [10, 20, 30, 40, 50];
undefined
console.log(a,b,rest);
// 10, 20 , [30, 40, 50]
let c = [1,2,3,4]
console.log(...c);
//1 1 2 3 4
```
函数的合并
```js
// 将传入add函数的参数合并为数组
function add(...arr){
    console.log(arr);
}
add(9,9)     //[ 9, 9 ]
add(1,2,3)      //[ 1, 2, 3 ]
add(4,5,6,7)        //[ 4, 5, 6, 7 ]

```
### 2.1对象扩展运算符

对象的扩展运算符(...)用于取出参数对象中的所有可遍历属性，拷贝到当前对象之中。

```
let bar = { a: 1, b: 2 };
let baz = { ...bar }; // { a: 1, b: 2 }
```

**等价于:**

```
let bar = { a: 1, b: 2 };
let baz = Object.assign({}, bar); // { a: 1, b: 2 }
```

`Object.assign`方法用于对象的合并，将源对象`（source）`的所有可枚举属性，复制到目标对象`（target）`。`Object.assign`方法的第一个参数是目标对象，后面的参数都是源对象。(**如果目标对象与源对象有同名属性，或多个源对象有同名属性，则后面的属性会覆盖前面的属性**)。

同样，如果用户自定义的属性，放在扩展运算符后面，则扩展运算符内部的同名属性会被覆盖掉。

```
let bar = {a: 1, b: 2};
let baz = {...bar, ...{a:2, b: 4}};  // {a: 2, b: 4}
```

利用上述特性就可以很方便的修改对象的部分属性。在`redux`中的`reducer`函数规定必须是**一个纯函数**，`reducer`中的`state`对象要求不能直接修改，可以通过扩展运算符把修改路径的对象都复制一遍，然后产生一个新的对象返回。

需要注意：**扩展运算符对****对象实例的拷贝属于浅拷贝**。

### 1.2数组扩展运算符

数组的扩展运算符可以将一个数组转为用逗号分隔的参数序列，且每次只能展开一层数组。

```
console.log(...[1, 2, 3])
// 1 2 3
console.log(...[1, [2, 3, 4], 5])
// 1 [2, 3, 4] 5
```

下面是数组的扩展运算符的应用：

-   **将数组转换为参数序列**

```
function add(x, y) {
  return x + y;
}
const numbers = [1, 2];
add(...numbers) // 3
```

-   **复制数组**

```
const arr1 = [1, 2];
const arr2 = [...arr1];
```

-   **合并数组**

如果想在数组内合并数组，可以这样：

```
const arr1 = ['two', 'three'];
const arr2 = ['one', ...arr1, 'four', 'five'];
// ["one", "two", "three", "four", "five"]
```

-   **扩展运算符与解构赋值结合起来，用于生成数组**

```
const [first, ...rest] = [1, 2, 3, 4, 5];
first // 1
rest  // [2, 3, 4, 5]
```

需要注意：**如果将扩展运算符用于数组赋值，只能放在参数的最后一位，否则会报错。**

```
const [...rest, last] = [1, 2, 3, 4, 5];         // 报错
const [first, ...rest, last] = [1, 2, 3, 4, 5];  // 报错
```

-   **将字符串转为真正的数组**

```
[...'hello']    // [ "h", "e", "l", "l", "o" ]
```

-   **任何 Iterator 接口的对象，都可以用扩展运算符转为真正的数组**

比较常见的应用是可以将某些数据结构转为数组：

```
// arguments对象
function foo() {
  const args = [...arguments];
}
```

用于替换`es5`中的`Array.prototype.slice.call(arguments)`写法。

-   **使用**`Math`**函数获取数组中特定的值**

```
const numbers = [9, 4, 7, 1];
Math.min(...numbers); // 1
Math.max(...numbers); // 9
```
### 2.3函数扩展运算符

```js
//接受多个不固定参数的函数
function foo(...args) {
    console.log(args);
}
foo(1, 2, 3); // [1, 2, 3]

//接收多个固定参数的函数
function foo(a, b, ...rest) {
    console.log(a, b, rest);
}
foo(1, 2, 3, 4, 5); // 1 2 [3, 4, 5]

function foo(a, b) {
    console.log(a, b);
}
foo(...[1, 2]); // 1 2
```
猜测函数接收扩展运算符相当于做了以下操作
```js
function foo(...args) {
    console.log(arguments);// arguments是一个类数组对象
    console.log(...arguments);// 1 2 3
    console.log(args);
}
foo(1, 2, 3); // [1, 2, 3]
//相当于
let [ ...args] = [1, 2, 3];
```
## 3.今日精进
真正的情商高手都是懂得倾听的，在人际关系中，他们往往不会急于去表达自我，而是懂得安心安然地倾听。
# Day19【2022年8月12日】 
**学习重点：** 模板字符串

模板字符串使用反引号 (` `) 来代替普通字符串中的用双引号和单引号。模板字符串可以包含特定语法（${expression}）的占位符。
## 1.模板字符串的优点
字符串更容易拼了，更易读了，代码整体的质量都变高了。允许用${}的方式嵌入变量。在模板字符串中，空格、缩进、换行都会被保留，模板字符串完全支持“运算”式的表达式，可以在${}里完成一些计算。还可以用模板字符串插入html表达式。模板字符串不是字符串，而是一种特殊的 JavaScript 句法表达式，只不过求值后得到的是字符串。
## 2.使用模板字符串
```js
let value = 5; 
let exponent = 'second'; 
// 以前，字符串插值是这样实现的(需要考虑空格缩进)：
let interpolatedString = 
 value + ' to the ' + exponent + ' power is ' + (value * value); 
// 现在，可以用模板字面量这样实现(还可以进行计算)：
let interpolatedTemplateLiteral = 
 `${ value } to the ${ exponent } power is ${ value * value }`; 
console.log(interpolatedString); // 5 to the second power is 25 
console.log(interpolatedTemplateLiteral); // 5 to the second power is 25
````
插入HTML模板
```js
let list = `
    <ul>
        <li>列表项1</li>
        <li>列表项2</li>
    </ul>
`;
console.log(message); // 正确输出，不存在报错
```
所有插入的值都会使用 toString()强制转型为字符串，而且任何 JavaScript 表达式都可以用于插值。
```js
//将表达式转换为字符串时会调用 toString()：
let foo = { toString: () => 'World' }; 
console.log(`Hello, ${ foo }!`); // Hello, World! 
```
与函数的使用
```js
//在插值表达式中可以调用函数和方法：
function capitalize(word) { 
 return `${ word[0].toUpperCase() }${ word.slice(1) }`; 
} 
console.log(`${ capitalize('hello') }, ${ capitalize('world') }!`); // Hello, World! 、

//重复调用模板也可以插入自己之前的值：
let value = ''; //全局变量不在顶层window对象上，所以不能使用window.value
function append() { 
 value = `${value}abc` 
 console.log(value); 
} 
append(); // abc 
append(); // abcabc 
append(); // abcabcabc
```
## 今日精进
在孤独中进步，在孤独中反思认清自己。前进途中时刻保持谦虚谨慎，不断check自己发力的方向是否正确。
# Day20【2022年8月13日】 
## 今日精进
永远不要轻易言否定自己，给自己设定一个上限。希望是本无所谓有，无所谓无的，正如地上的路；其实地上本没有路。走的人多了，也便成了路。
# Day21【2022年8月14日】 
**学习重点：**  隐式类型转换
## 1.隐式类型转换
> 在js中，当运算符在运算时，如果两边数据不统一，CPU 就无法计算，这时我们编译器会自动将运算符两边的数据做一个数据类型转换，转成一样的数据类型再计算这种无需程序员手动转换，而由编译器自动转换的方式就称为隐式转换
> 例如1 > "0"这行代码在js中并不会报错，编译器在运算符时会先把右边的 "0" 转成数字 0 然后在比较大小。
> 
### 1.1ToPrimitive
ToPrimitive，这是 JavaScript 中每个值隐含的自带的方法，用来将值 （无论是基本类型值还是对象）转换为基本类型值。如果值为基本类型，则直接返回值本身；如果值为对象，其看起来大概是这样：

```
/**
* @obj 需要转换的对象
* @type 期望的结果类型
*/
ToPrimitive(obj,type)
```

`type`的值为`number`或者`string`。

**当**`type`**为**`number`**时规则如下：**

-   调用`obj`的`valueOf`方法，如果为原始值，则返回，否则下一步；
-   调用`obj`的`toString`方法，后续同上；
-   抛出`TypeError` 异常。

**当**`type`**为**`string`**时规则如下：**

-   调用`obj`的`toString`方法，如果为原始值，则返回，否则下一步；
-   调用`obj`的`valueOf`方法，后续同上；
-   抛出`TypeError` 异常。

可以看出两者的主要区别在于调用`toString`和`valueOf`的先后顺序。默认情况下：

-   如果对象为 Date 对象，则`type`默认为`string`；
-   其他情况下，`type`默认为`number`。

总结上面的规则，对于 Date 以外的对象，转换为基本类型的大概规则可以概括为一个函数：

```
var objToNumber = value => Number(value.valueOf().toString())
objToNumber([]) === 0
objToNumber({}) === NaN
```
### 1.2转换规则
而 JavaScript 中的隐式类型转换主要发生在`+、-、*、/`以及`==、>、<`这些运算符之间。而这些运算符只能操作基本类型值，所以在进行这些运算前的第一步就是将两边的值用`ToPrimitive`转换成基本类型，再进行操作。

以下是基本类型的值在不同操作符的情况下隐式转换的规则 （对于对象，其会被`ToPrimitive`转换成基本类型，所以最终还是要应用基本类型转换规则）：

- 转成 string 类型： +（字符串连接符）
- 转成 number 类型：++ --（自增自减运算符）+ - * / % **（算术运算符）> < >= <= == !=（关系运算符）
- 转成 boolean 类型：! !!（逻辑非运算符）


1.  +操作符`+`操作符的两边有至少一个`string`类型变量时，两边的变量都会被隐式转换为字符串；其他情况下两边的变量都会被转换为数字。

```
1 + '23' // '123'
 1 + false // 1 
 1 + Symbol() // Uncaught TypeError: Cannot convert a Symbol value to a number
 '1' + false // '1false'
 false + true // 1
```

2.  -、*、\操作符NaN也是一个数字

```
1 * '23' // 23
 1 * false // 0
 1 / 'aa' // NaN
```

3.  对于**`==`**操作符

操作符两边的值都尽量转成`number`：

```
3 == true // false, 3 转为number为3，true转为number为1
'0' == false //true, '0'转为number为0，false转为number为0
'0' == 0 // '0'转为number为0
```

4.  对于**`<`**和**`>`**比较符

如果两边都是字符串，则比较字母表顺序：

```
'ca' < 'bd' // false
'a' < 'b' // true
```

其他情况下，转换为数字再比较：

```
'12' < 13 // true
false > -1 // true
```

以上说的是基本类型的隐式转换，而对象会被`ToPrimitive`转换为基本类型再进行转换：

```
var a = {}
a > 2 // false
```

其对比过程如下：

```
a.valueOf() // {}, 上面提到过，ToPrimitive默认type为number，所以先valueOf，结果还是个对象，下一步
a.toString() // "[object Object]"，现在是一个字符串了
Number(a.toString()) // NaN，根据上面 < 和 > 操作符的规则，要转换成数字
NaN > 2 //false，得出比较结果
```

又比如：

```
var a = {name:'Jack'}
var b = {age: 18}
a + b // "[object Object][object Object]"
```

运算过程如下：

```
a.valueOf() // {}，上面提到过，ToPrimitive默认type为number，所以先valueOf，结果还是个对象，下一步
a.toString() // "[object Object]"
b.valueOf() // 同理
b.toString() // "[object Object]"
a + b // "[object Object][object Object]"
```
5.其他类型转布尔值
只有 0、NaN、null、undefined、空字符串、false 转为布尔类型时为 false，其余情况转换为布尔类型都是 true，而且没有特殊情况。
```js
console.log(!0); // true 
console.log(!!''); // false
```
## 2.今日精进
今天浅读阳明心学，其有三个部分，心即理、知行合一、致良知，分别对应开端、实践及目的。大道至简，真理至易。心为万事之本、万事之源。人成就上的成败，处境上的好坏，全部源于内心的造作，只要你拥有一颗强大的内心，那么破解问题的门道自然无需外求。
-   JavaScript高级程序设计（第4版）
-  [MDN](https://developer.mozilla.org/en-US/)
-  [鲨鱼哥的面试题总结](https://github.com/BigSharkLx/front-end-interview/blob/main/5%20offer%E6%94%B6%E5%89%B2%E6%9C%BA%E4%B9%8BJavaScript%E7%AF%87.md)
-  解锁前端面试体系核心攻略
-  [细数JavaScript中那些遍历和循环](https://cuggz.blog.csdn.net/article/details/107649549)

#  结语

志同道合的小伙伴可以加我，一起交流进步，我们坚持每日精进（互相监督思考学习，如果坚持不下来我可以监督你）。另外共享学习资料的小伙伴也可以联系我，进群技术交流资料free共享，我们交换资料一起努力鸭！
——>[点击这里](https://juejin.cn/pin/7123425224455880740)

# 备注
按照时间顺序倒叙排列，完结后按时间顺序正序排列方便查看知识点,工作日更新。