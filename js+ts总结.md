##JavaScript

###一、基本语法
1.大小写敏感
2.标识符

标识符，就是指变量、函数、属性的名字，或者函数的参数。标识符可以是按照下列格式规则组合起来的一或多个字符:
第一个字符只能是字母、下划线（ _ ）或美元符号（ $ ）之一；
其他字符可以是字母、下划线、美元符号或数字。
按照惯例，ECMAScript（European Computer Manufacturers Association） 标识符采用 驼峰大小写格式，也就是第一个字母小写，剩下的每个单词的首字母大写，如getNameById
3.注释

4.语句
语句后的分号建议添加，但不必须。
5.关键字/保留字

break do instanceof typeof case else new var catch finally return void continue for switch while debugger function this with default if throw delete in try
6.变量

ECMAScript 的变量是==松散类型==的
定义变量时要使用 var 操作符，后跟变量名（即一个标识符），如下所示： var message; 这行代码定义了一个名为 message 的变量，该变量可以用来保存任何。

有一点必须注意，即用 var 操作符定义的变量将成为定义该变量的作用域中的局部变量。也就是说，如果在函数中使用 var 定义一个变量，那么这个变量在函数退出后就会被销毁，例如：

function test(){
    var message = "hi"; // 局部变量，去掉var即为全局变量
}
test();
alert(message); // 错误！
虽然省略 var 操作符可以定义全局变量，但这也不是我们推荐的做法。因为在局部作用域中定义的全局变量很难维护。那么正确的做法是什么？
###2.操作符
一元操作符 ++ --

布尔操作符 && || ！

除下列值为假外其余皆为真： false、null、undefined、''、0、NaN
&&和||都属于 短路操作！
算术操作符 + - * / %

注意以下代码：

var result = 5 + '5'; // 一个数值和一个字符串相加
console.log(result); // '55'
//============================================
var num1 = 5;
var num2 = 10;
var message = "The sum of 5 and 10 is " + num1 + num2;// (num1 + num2)，还可使用模板字符串``
console.log(message); // "The sum of 5 and 10 is 510"
关系操作符 <> <=>= == === != !==

注意: ===称为全等（值和类型）。

var x = 5;
console.log(x == 5);
console.log(x == '5');
console.log(x === 5);
console.log(x === '5');
条件（问号）操作符 ? :

能有效的简洁代码

var max = (num1 > num2) ? num1 : num2;
赋值操作符 = += -+ *= /= %=
###3.语句
if do-while while for for-in for-of break continue switch

注意，请为语句块添加 {}，不要吝啬
另外， for-of、forEach能简洁的遍历集合中的元素，如下代码：

var colors = ['red', 'green', 'blue', 'brown'];	//colors是一个数组
//传统遍历（基本不用了）
for(var i=0;i<colors.length;i++){
  console.log(colors[i]);
}
//for-in，专注下标
for(var c in colors){
  console.log(colors[c]);
}
//for-of，专注元素
for(var c of colors){
  console.log(c);
}
//高级遍历
colors.forEach(c => console.log(c));
var other = colors.map(c => c + 'X');//map不仅遍历，还返回另一个数组
console.log(other);
###4.函数
函数（ function）对任何语言来说都是一个核心的概念。通过函数可以封装任意多条语句，而且可以在任何地方、任何时候调用执行。以下是一个函数示例：


function sayHi(name, message) {
    console.log('Hello ' + name + ',' + message);
}
sayHi('Gridwang', '你好。');
ECMAScript 中的函数在定义时不必指定是否返回值。实际上，任何函数在任何时候都可以通过 return 语句后跟要返回的值来实现返回值。请看下面的例子：


function sum(num1, num2) {
    return num1 + num2;
}
var result = sum(3, 2);
console.log(result);
ECMAScript 函数不介意传递进来多少个参数，也不在乎传进来参数是什么数据类型。

也就是说，即便你定义的函数只接收两个参数，在调用这个函数时也未必一定要传递两个参数。可以传递一个、三个甚至不传递参数，而解析器永远不会有什么怨言（坑！）。

之所以会这样，原因是 ECMAScript 中的参数在内部是用一个数组来表示的。函数接收到的始终都是这个数组，而不关心数组中包含哪些参数（如果有参数的话）。如果这个数组中不包含任何元素，无所谓；如果包含多个元素，也没有问题。

如果在 ECMAScript中定义了两个名字相同的函数，则该名字只属于后定义的函数。请看下面的例子：


function addSomeNumber(num){
    return num + 100;
}
function addSomeNumber(num) {
    return num + 200;
}
console.log(addSomeNumber(100)); //300
###5.对象Object
对象 Object 是ECMAScript 中使用最多的一个类型。我们常将数据和方法封装在对象中。

创建对象有如下两种方式，我们常用第二种。


//方式一new
var person = new Object();//生成空对象
person.name = 'Elon Musk';//设置对象的属性
person.age = 46;
person.job = 'SpaceX Rocket';
person.sayName = function(){    //设置对象的方法/函数，注意此处
    console.log(this.name);
};
//方式二字面量
var person = {
    name: 'Lary Page',
    age: 47,
    job: 'Software Engineer',
    sayName: function(){        //注意此处
        console.log(this.name);
    }
};
console.log(person.job);
person.sayName();
虽然 Object 构造函数或对象字面量都可以用来创建单个对象，但这些方式有个明显的缺点：使用同一个接口创建很多对象，会产生大量的重复代码。为解决这个问题，人们开始使用工厂模式的一种变体。代码如下：


function createPerson(name, age, job){
    var o = new Object();
    o.name = name;
    o.age = age;
    o.job = job;
    o.sayName = function(){
        console.log(this.name);
    };
    return o;
}
var person1 = createPerson('Steve Jobs',56 , 'Inventor');
var person2 = createPerson('Linus Torvalds', 49, 'Software Engineer');
var person2 = createPerson('Julian Assange', 47, 'Ethical Hacker');
###6.数组Array
除了 Object 之外， Array 类型恐怕是 ECMAScript 中最常用的类型了。

ECMAScript 中的数组与其他多数语言中的数组有着相当大的区别。虽然 ECMAScript 数组与其他语言中的数组都是数据的有序列表，但与其他语言不同的是，ECMAScript 数组的每一项 可以保存任何类型的数据（不建议！）。

也就是说，可以用数组的第一个位置来保存字符串，用第二位置来保存数值，用第三个位置来保存对象，以此类推。而且，ECMAScript 数组的大小是可以动态调整的，即可以随着数据的添加自动增长以容纳新增数据。

创建数组有以下两种方法，我们常用第二种。


//方式一new
var colors = new Array('red', 'blue', 'green');
//方式二字面量
var colors = ['red', 'blue', 'green']; // 创建一个包含 3 个字符串的数组
console.log(colors[1]);
colors[3] = 'brown';
console.log(colors.length);
var names = []; // 创建一个空数组
var hyBird = [1, 2, 'haha', {firstName: 'Yong', lastName: 'Wang'}]; //不推荐！
console.log(hyBird[3].firstName);
常用的数组方法如下：

元素联合


var colors = ['red', 'green', 'blue'];
console.log(colors.join(',')); //red,green,blue
console.log(colors.join('||')); //red||green||blue
堆栈方法

栈是一种 LIFO（Last-In-First-Out，后进先出）的数据结构，也就是最新添加的项最早被移除。而栈中项的插入（叫做推入）和移除（叫做弹出），只发生在一个位置——栈的顶部。

ECMAScript 为数组专门提供了 push() 和 pop() 方法，以便实现类似栈的行为。


var colors = []; // 创建一个数组
var count = colors.push('red', 'green'); // 末尾推入两项
console.log(count); //2
colors.push('black'); // 末尾推入另一项
console.log(colors); //3
var item = colors.pop(); // 末尾弹出最后一项
console.log(item); //'black'
console.log(colors); //2
队列方法

栈数据结构的访问规则是 LIFO（后进先出），而队列数据结构的访问规则是 FIFO（First-In-First-Out，先进先出）。队列在列表的末端添加项，从列表的前端移除项。

由于 push() 是向数组末端添加项的方法，因此要模拟队列只需一个从数组前端取得项的方法。实现这一操作的数组方法就是 shift() ，它能够移除数组中的第一个项并返回该项，同时将数组长度减1。


var colors = new Array(); //创建一个数组
colors.push('red', 'green'); //推入两项
console.log(colors); //2
count = colors.push('black'); //推入另一项
console.log(colors); //3
var item = colors.shift(); // 前端弹出第一项
console.log(item); //'red'
console.log(colors);
ECMAScript 还为数组提供了一个 unshift() 方法。它能在数组前端添加任意个项并返回新数组的长度。


var colors = new Array(); //创建一个数组
var count = colors.unshift('red', 'green'); // 推入两项
console.log(colors);
count = colors.unshift('black'); // 推入另一项
console.log(colors);
var item = colors.pop(); // 取得最后一项
console.log(item); //'green'
console.log(colors);
总结：由上可知， push、pop操作在数组末，而 unshift、shift操作在数组头；push、unshift压入而pop、shift弹出。

反转数组项


var values = [1, 2, 3, 4, 5];
values.reverse();
console.log(values); //5,4,3,2,1
链接方法


var colors1 = ['red', 'green', 'blue'];
var colors2 = ['yellow', 'black'];
console.log(colors1.concat(colors2));
console.log(colors2.concat(colors1));
console.log(colors2.concat('brown'));
console.log(color2)//注意：concat返回一个新数组，原数组没改变
分片方法

slice() ，它能够基于当前数组中的一或多个项创建一个新数组。 slice() 方法可以接受一或两个参数，即要返回项的起始和结束位置。

在只有一个参数的情况下， slice() 方法返回从该参数指定位置开始到当前数组末尾的所有项。如果有两个参数，该方法返回起始和结束位置之间的项——但不包括结束位置的项。

注意， slice() 方法不会影响原始数组。


var colors1 = ['red', 'green', 'blue', 'yellow', 'purple'];
var colors2 = colors1.slice(1);
var colors3 = colors1.slice(2, 4);
var colors4 = colors1.slice(2, 2);//结果是什么？
console.log(colors1);
console.log(colors2);
console.log(colors3);
splice方法

splice() 方法恐怕要算是最强大的数组方法了，它可对数组如下3种操作。

注意， splice() 方法直接更改原始数组。

删除：可以删除任意数量的项，只需指定 2 个参数：要删除的第一项的位置和要删除的项数。 例如， splice(0,2) 会删除数组中的前两项。

插入：可以向指定位置插入任意数量的项，只需提供 3 个参数：起始位置、0（要删除的项数） 和要插入的项。如果要插入多个项，可以再传入第四、第五，以至任意多个项。例如， splice(2,0,'red','green') 会从当前数组的位置 2 开始插入字符串 'red' 和 'green' 。

替换：可以向指定位置插入任意数量的项，且同时删除任意数量的项，只需指定 3 个参数：起 始位置、要删除的项数和要插入的任意数量的项。插入的项数不必与删除的项数相等。例如， splice (2,1,'red','green') 会删除当前数组位置 2 的项，然后再从位置 2 开始插入字符串 'red' 和 'green' 。


var colors = ['red', 'green', 'blue'];
var removed = colors.splice(0,1); // 删除第一项
console.log(colors); // green,blue
console.log(removed); // red，返回的数组中只包含一项
removed = colors.splice(1, 0, 'yellow', 'orange'); // 从位置 1 开始插入两项
console.log(colors); // green,yellow,orange,blue
console.log(removed); // 返回的是一个空数组
removed = colors.splice(1, 1, 'red', 'purple'); // 插入两项，删除一项
console.log(colors); // green,red,purple,orange,blue
console.log(removed); // yellow，返回的数组中只包含一项
###7.链式语法
链式语法已变得非常流行。实际上这是一种非常容易实现的模式。基本上，你只需要让每个函数返回 this代表包含该函数的对象，这样其他函数就可以立即被调用。看看下面的例子。


//链式语法
var bird = {//定义对象字面量
  catapult: function() {
    console.log( 'Yippeeeeee!' );
    return this;//返回bird对象自身
  },
  destroy: function() {
    console.log( "That'll teach you... you dirty pig!" );
    return this;
  }
};
bird.catapult().destroy();//destroy()后还可以再链接吗？
###8.闭包
闭包是什么?闭包是Closure，这是静态语言所不具有的一个新特性。但是闭包也不是什么复杂到不可理解的东西，简而言之，闭包就是：

函数的局部变量集合，只是这些局部变量在函数返回后会继续存在。

闭包就是就是函数的“堆栈”在函数返回后并不释放，我们也可以理解为这些函数堆栈并不在栈上分配而是在堆上分配

当在一个函数内定义另外一个函数就会产生闭包。如下代码：


function greeting(name) {
    var text = 'Hello ' + name; // local variable
    // 每次调用时，产生闭包，并返回内部函数对象给调用者
    return function() { console.log(text); }//注意该函数无名称，称为匿名函数
}
var sayHello = greeting('Closure');//调用greeting()返回了什么？
sayHello();  // 注意此处的使用方法。通过闭包访问到了局部变量text
上述代码的执行结果是：Hello Closure，因为sayHello指向了greeting函数对象，sayHello()则对其进行调用，greeting函数执行完毕后将返回greeting函数内定义的匿名函数对象，而该匿名函数仍然可以访问到了定义在greeting之内的局部变量text，注意此时我们已从greeting函数中退出了（但请留意，也只有该内部匿名函数能访问，其它任何代码都不能访问）。以下是另外一个例子：


var scope = 'global scope';	//全局变量
function checkScope(){
    var scope = 'local scope';	//局部变量
    function f(){
        return scope;
    }
    return f;
}
checkScope()();		//注意此处的使用方法。返回值为local scope而非global scope
##TypeScript
###1.Typescript是什么
TypeScript是JavaScript类型的超集（当前我们处于ES5），它可以编译成纯JavaScript。

TypeScript给JavaScript加上可选的类型系统，给JavaScript加上静态类型后，就能将调试从运行期提前到编码期，诸如类型检查、越界检查这样的功能才能真正发挥作用。 TypeScript的开发体验远远超过以往纯JavaScript的开发体验，无需运行程序即可修复潜在bug。

TypeScript支持未来的ES6甚至ES7。在TypeScript中，可以直接使用ES6的最新特性，在编译时它会自动编译到ES3或ES5。

TypeScript可以构建大型程序，并在任何浏览器、任何计算机和任何操作系统上运行，且是开源的。
###2.TS配置
安装好NodeJS后，以管理员身份运行终端，使用npm -g install ts-node typescript命令进行全局安装

如在VS Code中开发，请安装TSLint、TypeScript Hero、Bracket Pair Colorizer等插件

新建一个.ts后缀的文件，任意写一段JS代码，点击运行试试是否配置成功

TypeScript的学习请前往其官网或中文网站

以下我们就Typescript涉及前端框架Angular和相关特性的一些知识点进行介绍

let 和 const
不使用var，使用let或const申明变量，并加上类型说明，且作用域为块级即以{}为界


let lang: string = 'TypeScript';//如果省略类型说明，TS也可进行自动推断
lang = 1010;//error! 如果需要可以使用联合类型：let lang: number | string = 'TS';
let age: number = 89;
let age = 64;//error!

const pi: number = 3.14159;//pi以后不可改变，类似常量
pi = 3.14;//error!
###3.let 和 const
不使用var，使用let或const申明变量，并加上类型说明，且作用域为块级即以{}为界


let lang: string = 'TypeScript';//如果省略类型说明，TS也可进行自动推断
lang = 1010;//error! 如果需要可以使用联合类型：let lang: number | string = 'TS';
let age: number = 89;
let age = 64;//error!

const pi: number = 3.14159;//pi以后不可改变，类似常量
pi = 3.14;//error!
###4.解构
将对象、数组中的元素拆分到指定变量中，以方便使用


//解构数组
let input = [89, 64, 2018, 10];
let [first, second] = input;//注意使用[]
console.log(first); // 89
console.log(second); // 64
let [one, ...others] = input; //剩余变量
console.log(...others);
//展开
let newArr = [89, ...others, 18];
console.log(newArr);
//解构对象
let o = {
  a: "foo",
  b: 12,
  c: "bar"
};
let {a, b} = o;//注意使用{}，且变量名需与对象中道属性名一致
console.log(a, b);
###5.函数
使用完整函数类型定义


//命名函数，有完整的参数和返回类型。可以不用，TS将自动进行类型推断但推荐使用！
function add(x: number, y: number): number {
  return x + y;
}
//匿名函数
let myAdd = function(x: number, y: number): number { return x + y; };
console.log(myAdd(1, '2'));//error
console.log(myAdd(1));//error
console.log(typeof myAdd(1, 2));//number 
可选参数


//可选参数，必须放在必要参数后
function greeting(firstName: string, lastName?: string) {
  if(lastName) {
      return `Hello ${firstName} ${lastName}!`;
  }
  return `Hello ${firstName}!`;
}
console.log(greeting('QiGe'));
console.log(greeting('QiGe', 'Wang'));
console.log(greeting('QiGe', 'Wang', 'Yong'));//error!
          
默认参数


//默认参数，不必在必要参数后
function greeting(firstName: string, lastName = 'Wang') {
  return `Hello ${firstName} ${lastName}!`;
}
console.log(greeting('QiGe'));
console.log(greeting('QiGe', 'HaHaHa'));
console.log(greeting('QiGe', 'HaHaHa', 'Yong'));//error!
          
剩余参数

必要参数，默认参数和可选参数有个共同点：它们表示某一个参数。 有时，你想同时操作多个参数，或者你并不知道会有多少参数传递进来， 在TypeScript里，你可以把所有参数收集到一个变量里


//剩余参数，会被当做个数不限的可选参数。可以一个都没有，也可以有任意个
function greeting(firstName: string, ...restName: string[]) {
  return `Hello ${firstName} ${restName.join(' ')}!`;
}
console.log(greeting('Osama', 'bin', 'Muhammad', 'bin', 'Awad', 'bin', 'Laden'));
console.log(greeting('Laden'));
          
箭头函数

特点：简化函数定义、解决this问题（如需进一步了解可查看文档）


//无参数，函数体代码只有一行，则该行结果即为函数返回值
let greeting1 = () => `Hello TS!`;
console.log(greeting1());
//一个参数，函数体代码只有一行，则该行结果即为函数返回值
let greeting2 = (name: string) => `Hello ${name}`;
console.log(greeting2('QiGe'));
//两个及以上的参数，函数体代码只有一行，则该行结果即为函数返回值
let add1 = (n1: number, n2: number) => n1 + n2;
console.log(add1(1, 2));
//两个及以上的参数，函数体代码多于一行,则必须用{}包裹，且显式给出return
let add2 = (n1: number, n2: number) => {
  let sum = n1 + n2;
  return sum;//改为sum++结果如何？
}
console.log(add2(1, 2));
          
###6.类class
类是属性（有些什么）和函数（能干什么）的集合，是生成对象（Object）或类实例的模板。（请注意，我们要用的Angular框架大量使用类）

类的定义和使用


//类的定义和使用
class MyInfo { //class是关键字，类名默认全部大写首字母
  name: string; //属性
  weather: string; //属性
  
  constructor(name: string, weather: string){ //构造函数，一般用于初始化。如果没有，TS会自动生成一个，以备用new创建类实例时调用。
    this.name = name;
    this.weather = weather;
  }
  printInfo(): void { //其它函数，无返回值
    console.log(`Hello, ${this.name}.`);
    console.log(`Today is ${this.weather}.`);
  }
}

let myData = new MyInfo('QiGe', 'raining'); //使用new关键字生成对象，即该类的实例
myData.printInfo();
          
类的属性和函数的访问权限

类中的属性和函数都有访问权限，默认为public即全局可访问，其次为protected即可在类的内部和其子类的内部可访问，最后为private，只能在该类内部可访问。


//访问权限
class MyInfo { //class是关键字，类名默认全部大写首字母
  public name: string; //public属性，可省略
  private _weather: string; //私有属性，习惯以_开头进行命名
  
  constructor(name: string, weather: string){ //构造函数，一般用于初始化
    this.name = name;
    this._weather = weather;
  }
  printInfo(): void { //其它函数
    this._test();
    console.log(`Hello, ${this.name}.`);
    console.log(`Today is ${this._weather}.`);
  }
  private _test(): void {
    console.log('You can not call me outside!');
  }
}

let myData = new MyInfo('QiGe', 'raining'); //使用new关键字生成对象
console.log(myData._weather); //error!
myData._test(); //error
myData.printInfo();
          
存取器-getter、setter

当在类外部时，建议设置getter和setter操作其private属性，即使public属性也如此。


//getter和setter
class MyInfo { //class是关键字，类名默认全部大写首字母
  private readonly _name: string; //私有属性，外部不可访问。readonly使其只能在初始化时赋值，以后不可更改。    
  private _weather: string; //私有属性，习惯以_开头进行命名

  constructor(name: string, weather: string){ //构造函数，一般用于初始化
    this._name = name;
    this._weather = weather;
  }
  get name(): string {
    return this._name;
  }
  set name(value: string) {  //error！ _name有readonly属性
    this._name = value;
  }
  get weather(): string {
    return this._weather;
  }
  set weather(value: string) {
    this._weather = value;
  } 
}
  
let myData = new MyInfo('QiGe', 'raining'); //使用new关键字生成对象
console.log(myData.name, myData.weather);
myData.weather = 'sunny'; //OK
myData.name = 'Wang'; //error!
console.log(myData);
          
静态属性

类中的属性或函数有static修饰，则可直接使用而不需要实例化


//静态属性，内建或自定义，无需new即可使用
console.log(Math.round(89.64)); //90
console.log(Math.pow(2, 8)); //256
class MyStaticClass {
  static place = 'Earth';
  static printInfo() {
    console.log('We have only one Earth!');
  }
}
console.log(MyStaticClass.place);
MyStaticClass.printInfo();
          
继承

可以通过extends关键字继承其它类，从而成为其子类


class Animal {
  // 当构造函数传入的参数加上了“访问权限控制符”，则同时会声明同名类属性，并赋值
  constructor(public name: string) { }
  protected log(message: string) {
    console.log(message);
  }
  move(distanceInMeters: number = 0) {        
    this.log(`${this.name} moved ${distanceInMeters}m.`);//请注意name来自何处
    this.log('==============');
  }
}

class Horse extends Animal {
  constructor(name: string) { 
    super(name); // 通过super调用父类构造器
  }
  run(distanceInMeters = 50) { //自己独有的函数
    this.log("Clop, clop..."); 
    super.move(distanceInMeters); // 通过super调用父类方法
  }
}

class Eagle extends Animal {
  constructor(name: string) { super(name); }
  reborn() { //自己独有的函数
    console.log('Reborn？ It is a joke, hahaha!');
  }

}

let tom: Horse = new Horse("Tommy the Palomino");
tom.run(8964);
let sam: Eagle = new Eagle("Sammy the Hawk");
sam.move(1024);//sam的move函数来自何处？
sam.reborn();
###7.模块Module
对于大型的项目，我们需要使用模块进行管理。每个 .ts 文件就是一个模块，通过 export 来对外部模块暴露元素，通过 import 来引入模块。

在项目文件夹下新建目录modules和文件main.ts，并在modules下新建name.ts和weather.ts文件，如下：

modules/name.ts
modules/weather.ts
main.ts

export class Name { //用export对外部暴露该类
  constructor(private first: string, private second: string) {}
  get nameMessage() {
    return `Hello ${this.first} ${this.second}`;
  }
}            