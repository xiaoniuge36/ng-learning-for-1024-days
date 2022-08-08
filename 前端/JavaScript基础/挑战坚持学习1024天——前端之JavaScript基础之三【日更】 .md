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
按照时间顺序倒叙排列，完结后按时间顺序正序排列方便查看知识点,工作日更新，每周一总结周末做的事情：学习/其他。