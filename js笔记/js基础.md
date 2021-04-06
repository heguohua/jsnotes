---

---

# 1.JavaScript介绍

### 1.1  js的大致的历史

1995年诞生，Netscape 公司，为了让页面可以验证表单，发明了它

同年，微软不甘示弱，也发明了自己的js —— jScript

两大公司相互竞争，导致程序员非常的痛苦，。

后来Netscape把js提交给 ECMA 协会，要求统一标准 —— ECMAScript 这个标准

一直发展，发展出了很多的版本、最早 JavaScript1.1 --> ECMAScript 1.0

有ECMAScript5，ECMAScript6

### 1.2JavaScript的组成

* ECMAScript - 简称es，用来规范JavaScript的语法的，具有多个版本。
* DOM - 文档对象模型，用来操作页面上的标签的
* BOM - 浏览器对象模型，用来操作浏览器的部分功能的



## 2.JavaScript的三种样式

JavaScript和css一样，也有三种书写方式

### 2.1 内嵌式

在一个固定的标签 —— script , 写js代码

```html
<script>
  alert('邮箱的名字不合理');
</script>
```



### 2.2 外联式

1.在外部准备一个js文件，使用script标签引入

```html
// 语法  <script src="js文件的路径" ></script>

<script src="./01.js"></script>
```



### 2.3 行内式

写在标签的属性里面的，通常都是  onXXX 这些属性里面

```html
<input type="button" value="按钮" onclick="alert('hello world');">
```



> 总结：
>
> 1.使用方式有3中，开发里面外联使用的多，上课多用内嵌，行内几乎不用
>
> 2.建议js都写在其他的结构标签的后面 —— 后面学习的时候再解释
>
> 3.外联式的script里面不要写代码



## 4. 四个常用js方法

#### 4.1 alert()

作用： 用于来浏览器弹出一个提示框

~~~js
// 弹窗提示
alert('不好意思，您的账号输入错误！');
~~~

效果：

<img src="js基础.assets/image-20201108141923290.png" alt="image-20201108141923290" style="zoom:80%;" />

#### 4.2 prompt()

作用：在浏览器里面弹出一个输入框，让用户输入

~~~js
prompt("请输入你的银行卡密码"); // 同样使用引号包起来
~~~

<img src="js基础.assets/image-20201108142346537.png" alt="image-20201108142346537" style="zoom:80%;" />

#### 4.3 console.log()

作用：这个方法可以在开发者工具的 `Console`选项，也就是我们所说的`控制台`里面输出消息

~~~js
 // 在浏览器控制台窗口显示内容（后期主要用于调试代码）
console.log('测试一下~')
~~~

<img src="js基础.assets/image-20201108142213143.png" alt="image-20201108142213143" style="zoom:80%;" />

#### 4.4 document.write()

作用：这是一个比较早期的时候，浏览器里面提供的一个在页面的body标签里面输出消息的方式，现在很少用了

~~~js
//使用js把内容写入页面
document.write('今天天气真好');
~~~

效果：

<img src="js基础.assets/image-20201108142129807.png" alt="image-20201108142129807" style="zoom:80%;" />



## 5. 变量

如果我们使用prompt()方法让用户输入了数据，我们又想要把用户输入的数据保存起来，怎么办呢？

在JavaScript中有一种专门用于保存数据的语法：**变量**

### 5.1 什么是变量

变量就是存储数据的容器

### 5.2 变量的语法

用是先定义再使用

### 5.3 变量定义

```javascript
var 变量名 = 数据;
```

使用`var`这个单词，告诉浏览器，我们要定义一个变量，使用`=`号告诉浏览器，我们要把左边的数据存储到变量里面

当我们想使用这个数据的时候，就可以直接使用这个变量代替这个实际数据

```javascript
// example 1
var pwd = prompt('请输入你的很行卡密码');
console.log(pwd);
// example 2
var num1 = 10;
var num2 = 20;
console.log(num1 + num2);//计算两个数字的和
```

变量定义分为两个过程：变量声明和变量赋值

```javascript
// 变量声明
var a;
// 变量赋值
a = 10;
```

变量可以被重新赋值

```javascript
var b = 100;
b = 200;
```

上面代码中，`200`被称为变量`b`的`值` 



### 5.5 变量命名规范

变量的命名规范

1. 能够使用那些字符 ： 数字、字母、下划线、$
2. 不能使用数字开头
3. 不能使用js里面具有特殊功能的单词 —— 关键字,也不建议使用保留字
4. 区分大小写
5. 建议命名有意义
6. 建议使用驼峰命名 - 单词的首字母，第一个单词小写，其他的单词的首字母大写

错误演示

~~~js
// 变量不能使用数字开头
var 15a = 10;
// 会在控制台中报错：Uncaught SyntaxError: Unexpected number
// Uncaught - 未捕获的
// SyntaxError - 语法错误
// Unexpected - 意料之外的
// number - 数字
// 翻译过来就是： 这行有一个语法错误，你的数字不符合语法要求

// 变量名字不能使用关键字
var var = 20;
// 会在控制台中报错： Uncaught SyntaxError: Unexpected token var
// token - 标记，记号，在编程中我们翻译成 '标识符'
// 意思是这行有一个语法错误，出现了一个意料之外的标识符 var

// 变量名字是区分大小写的
var a = 10;
console.log(a);// 正常输出
console.log(A);// 在控制台中报错：Uncaught ReferenceError: A is not defined
// ReferenceError - 引用错误
// not defined - 未定义
// 意思是 A 这个变量我们没有定义就使用了，可见a和A是不一样的，不是同一个变量
~~~

> Tips :
>
> 大家在学习的过程中，会遇到许多错误，要习惯看控制台中的错误代码，也可以自己准备一个错题集，把常见的错误记录下来，以便以后遇到同样的错误的时候可以借鉴以前解决错误的思路





## 6. 数据类型

### 6.1 简单类型

###  数值（number）

其实就是数字，就是整数、小数、负数....

```js
var num1 = 123;
```

小数相加可能会有bug

```js
console.log(0.1 + 0.2); // 不是0.3 , 是一个不准确的数字
```

数值类型中 还有一个非常特殊的存在： NaN， 先记住，一会再介绍是什么





###  字符串(string)

字符串主要作用就是用来表示文本的，单词、字母、汉字、文章、名字...

##### 固定格式

```jade
'字符'
"字符"
```

我们发现，在js的语法中，已经使用了引号来做为格式了，如果我们就是要输出一个引号，不使用特殊的手段是做不到的，如果希望引号里面出现引用

```js
// 1.嵌套引号
console.log('<div id="box"></div>');
// 2 转义字符
console.log("<div id=\"box\"></div>")
```

所谓转义字符，就是在想要转义的字符前面加上一 `\`，这样就把带有特殊意思的字符变成了普通的字符，就可以输出了



###  布尔(Boolean)

是在编程中专门为了表示条件结果的，只有两个值： true 和 false

true - 表示结果成立，为真

false - 表示结果不成立，为假

```js
var result = 4 > 5;
console.log(result);// false ,因为 4 > 5 不成立
var res = 5 < 6;
console.log(res); // true 因为 5 < 6 成立
```



### null(空)和undefined（未定义）

undefined  —— 未定义 ，一般很少主动使用，知道是未定义的意思就行

通常就是我们声明了变量但是没有赋值，就是undefined

null —— 空 , 什么都没有 ， 通常也是不会主动使用，而是得到的一个结果是null

```js
prompt('输入框'); // 如果点击了取消，就是 null
```





### 6.2 复杂类型(引用类型)

#### 	1.Object(对象)

#### 	2.Array (数组)

#### 	3.Function(函数)



## 7. typeof判断基本类型

我们学习了这么多的数据类型，怎么知道一个数据到底是什么类型呢？js提供了一个可以返回数据类型的关键字：typeof

用法有两种

```javascript
typeof 数据;
typeof(数据);
```

```javascript
console.log(typeof 123);// number
console.log(typeof 'abc');//string
console.log(typeof true); // true
console.log(typeof undefined); // undefined
```

> 



## 8. 浏览器里面调试代码

第一步： 打开sources选项卡

![image-20200111114140860](js基础.assets/image-20200111114140860.png)

左边可能会有文件，也可能没有，需要自己把文件点出来

<img src="js基础.assets/image-20200111114321900.png" alt="image-20200111114321900" style="zoom:50%;" />

在需要断点的地方打断点(哪里有问题就在哪里打断点)

<img src="js基础.assets/image-20200111114532086.png" alt="image-20200111114532086" style="zoom:50%;" />

刷新就会停在断点的行上面

<img src="js基础.assets/image-20200111114642643.png" alt="image-20200111114642643" style="zoom:50%;" />

然后就观察，每个变量的当前的值是多少

<img src="js基础.assets/image-20200111114732882.png" alt="image-20200111114732882" style="zoom:50%;" />



> 



## 9. 数据类型转换

在js中，数据类型是可以相互转换的

主要是三大类：转成数字、转成字符串、转成布尔

~~~js
把其他转成数字： Number() 、 parseInt() 、 parseFloat()
把其他转成字符串：String() 、.toString()
把其他转成布尔: Boolean()
~~~



把其他转换为数字

```js
Number(数据) // 把其他的类型转换为数字
parseInt(数据) // 把字符串转换为整数
parseFloat(数据) // 把字符串转换为小数
var result = Number('3000');  // 3000
parseInt('1.22') // 1
parseFloat('1.22') // 1.22
```



其他转字符串

```js
String(数据)
(数据).toString() // 小数和null、undefined在使用的时候要小心

var res1 = String(123);
console.log(res1);  // 输出字符串的 123
console.log(typeof res1); // 输出 string

var res2 = String(true);
console.log(res2); // 输出字符串的 true
console.log(typeof res2); // 输出 string

var res3 = (123).toString();
console.log(res1); // 输出字符串123
console.log(typeof res1); // 输出string

var res4 = undefined.toString();
console.log(res3); // 报错：Cannot read property 'toString' of undefined

var res5 = null.toString();
console.log(res4); //报错： Cannot read property 'toString' of null
```

> 但是转换为字符串是很少用的，了解就行



-转换为布尔 （*只有 0 ， ' ' , null, undefined, false, NaN 转为false*)

```js
Boolean(数据);
只有以下几个是false，其他都是true
console.log(Boolean(0));
console.log(Boolean(''));
console.log(Boolean(null));
console.log(Boolean(undefined));
console.log(Boolean(false));
console.log(Boolean(NaN));
```



## 10. 运算符

### 10.1算术运算符

`+ `操作符的作用有：

1. 字符串相连
2. 数字相加

```jsx
1. 字符串 + 其他 = 字符串
会把其他类型 转换为 字符串 ， 两个字符串连接到一起
2. 数字 + 数字 = 数字
会把其他类型 转换为 数字 ，再相加
```



-`操作符的作用就是数字相减

```js
- 
都是优先把非数字的转换为数字，再运算
var res3 = '456' - 123; 
console.log(res3); // 输出 数字 333
var res4 = 'abc' - 123;
console.log(res4); // 输出NaN
这是因为，数字和字符串在相减的过程中，会把字符串隐式转换成数字，再相减。但是如果字符串在转换的过程中，无法转换成数字，就会转换成NaN，再计算就无法得到一个正确的数字结果
```



`*`操作符的作用是两个数字相乘

`/`操作符的作用是两个数字相除

`%`操作符的作用是两个数字求模(得到余数)

```js
% 
  作用： 得到两个数字相除的余数
  无法整除的部分就是余数
  
  看看一个数字是否整除另一个数字
```

### 隐式转换

隐式转换是指在数据在参与运算的过程中，数据根据操作符的运算规则自动进行的数据类型转换。



### 10.2. 比较运算符

```js
> <  >=  <= 
  以上都是和数学里面的比较是一样的规则

== 
  判断两个值是否相等
console.log(5 % 2 == 0);

!=
  判断两个值不相等
console.log(5 % 2 != 0);

===
  判断类型和值是否相等
console.log(undefined === null);
!==
  判断类型和值是否不相等

console.log(NaN == NaN); // false 
// 如何验证一个数据, 不是NaN
//  isNaN(数据) 判断一个数据是否是NaN
console.log(isNaN(NaN)) //  NaN是一个NaN, 所以得到的是true
console.log(isNaN(123)) //  123不是一个NaN, 所以得到的是false
```

## 11.数据类型的转化

### 1.转化成数值类型

​	1Number() 数值 整数 分数 小数

```
	Number() 转成数字

     parseInt() 转成整型
​    parseFloat() 转成浮点数（小值） 但是不会自动补充小数点

 	var str1 = '300';
​    var num1 = '12.9';

​    var str2 = '15jkejkdksksd';

​    var str3 = '1.23';

​    console.log(Number(str1)); //300
	console.log(Number(num1)); //12.9
	 console.log(Number('10asas')); //NaN

​    console.log(parseInt(str1)); //300
	console.log(parseInt(num1));//12
	console.log(parseInt(str2)); //15
	console.log(parseInt('skdsds2123')); //NaN
	 console.log(parseInt('abc')); //NaN
	console.log(parseFloat(str3)); //1.23

​   console.log(parseFloat(str1));// 300 
	  console.log(parseFloat("abc"));  // NaN
	 console.log(parseFloat(60));  //60
	 console.log(parseFloat(str2));//15
	 console.log(parseFloat('12ksdkd')); //12
​    
```

### 2.转为字符串 

1. String()  转为字符串

```
 var num1 = 30;

​    console.log(String(num1), typeof String(num1));
     //30  string
```

2. num2.toString() 得到一个字符串

```
  var num2 = 3000;

  console.log(num2.toString(), typeof num2.toString()); //3000   string
```

3. num3+' ' 得到一个字符串

```
     var num3 = 3000;

     console.log(num3 + "", typeof (num3 + "")); 
```

​	

### 3.转化为布尔值

​     1.布尔值只有两个： true false

​      **<u>记住：只有这六个值，转成布尔值是false: '' 0 null underfined NaN false</u>**

 	 **其余转布尔值为true**

```
var num = -20;

​    console.log(Boolean(num));

​    var a = '';

​    var b = 0;

​    var c = null;

​    var d = undefined;

​    var e = NaN;

​    var f = false;
​    console.log(Boolean(a)); // false  

​    console.log(Boolean(b)); // false 

​    console.log(Boolean(c)); // false 

​    console.log(Boolean(d)); // false 

​    console.log(Boolean(e)); // false 

​    console.log(Boolean(f)); // false 
```



## 12.运算符

####       1.算数运算

```
 console.log(3 + 5);

​    console.log(3 - 5);

​    console.log(3 * 5);

​    console.log(3 / 5);

​    console.log(10 ** 3); // 表示10 的3次方
​    console.log(10 % 2); //如果对2 取余等于0，说明是偶数，否则是奇数
```

####        2.加号的作用

```
/* 

​    加号'+''的作用

​    1.算数运算 加号两边都是数字

​    2.字符串拼接 加号两边只要有一边为字符串，结果就为字符串

​    3.在类于数字的字符串前面加一个‘+’，可以把它换成数字

​    */

​    console.log(3 + 5); //8

​    console.log(3 + '5'); //35

​    console.log('3' + 5 + 5); //355

​    console.log(+'5', typeof (+'5'));





​    var age = 26;

​    console.log(name1 + '的年龄是：' + age + '.'); //字符串拼接
```

#####      		2.1加号的运用

```
   /* 

​      1.算数运算 加号两边都是数字

​      2.字符串拼接 加号两边只要有一边为字符串， 结果都为字符串

​      3.在类似于数字的字符串前面加一个“+”，可以把它换成数字

​    */

​    console.log(3 + '5');

​    console.log(+'5', typeof (+'5'));

​    var age = 26;

​    console.log(name + '的年龄是' + age + '.');
```



#### 3.比较运算

  // 比较运算符

​    // > < == === >= <= !=

```
    console.log(3 < 5); //true

​    console.log(3 > 5); //false

​    console.log(3 >= 5); //false

​    console.log(5 >= 5); //true

​    console.log(5 <= 5); //true

​    console.log(5 < 5); //false


​    console.log(5 == 5); //true


​    console.log('5' == 5);//true 双等号的判断。，不带类型判断

​    console.log('5' === 5); //false 三等号（全等号）的判断，带类型判断



​    console.log(5 === 5); //true

​    // NaN 特殊值， 不和任何值相等， 包括自己也不相等



​    console.log('===========================================');

​    console.log(NaN == 2);//false

​    console.log(NaN == NaN); //false

​    console.log(NaN === NaN); //false



​    console.log(3 != 5);

​    console.log('5' != 5); //false



​    console.log('5' !== 5); //true 加了类型的判断
```

#### 4.逻辑运算符

```
    //  && 与 并且    || 或     !非(取反符号)

​    console.log(true && true); // true 两个为真,结果为真. 

​    console.log(true && false); // false 

​    console.log(false && true); // false 

​    console.log(false && false); // false 

​    console.log("--------------------------------------------------");

​    console.log(true || true);  // true

​    console.log(true || false); // true

​    console.log(false || true); // true

​    console.log(false || false); // false

​    console.log("--------------------------------------------------");

​    console.log(!true);  // false

​    console.log(!false); // true

​    console.log(!3);  // false  3进行隐式转换,再取反

​    console.log(!"");  // true

​    console.log(!0);  // true

​    console.log(!NaN);  // true

​    console.log(!undefined);  // true

​    console.log(!null);  // true



​    // 结论:

​    // && 两边只要有一个为false 最终结果为false.两个都成立,结果才会成立.

​    // || 两边只要有一个为true 最终结果就为true.两边只要有一个成立,结果就会成立.



​    // 可以在后面的if语句中的条件判断去使用.
```





### 13.增和自减的用法

单独作为一行的时候，num++和++num效果是一样的

当他们和其他语句一起使用的时候：

num++  表示先使用，再马上+1

++num   表示先+1，再使用

  // ++ 自增符号  自加

```
    var num = 10;

​    // num++;    // 当单独作为一行代码执行的时候, num++和++num效果一样.

​    // ++num;

​    // console.log(num++); // 10  

​    // console.log(num); // 11



​    // console.log(++num); // 11

​    // console.log(num); // 11



​    // console.log(num--); // 10

​    // console.log(num); // 9



​    // console.log(--num); // 9

​    // console.log(num); //9



​    // 练习题:

​    var num2 = 30;

​    var result = num2 + ++num;  

​    console.log(result); // 41

​    console.log(num); // 11

​    var result2 = num2 + num++;

​    console.log(result,result2, num); // 41 41 12
​    // i++;

​    // ++i;
```

### 14判断语句

##### 	1.if语句

​		 如果 (条件)...就....

​      格式:

​      if(条件){

​        // 条件成立就会执行这里的代码

​        // 条件最终结果为true, 就会执行这里的代码

​      }

​      特点: 大括号里面的代码不一定会执行

```
 // 判断年龄是不是大于等于18, 如果是,就语序进入网吧.
​    var age = 15;
​    if(age>=18){
​      console.log("已成年,可以进入网吧!");
​    }
```

##### 	2.if else

​		/*

​      如果 (条件)...就.... 否则....

​      格式:

​      if(条件){

​        // 条件成立就会执行这里的代码

​        // 条件最终结果为true, 就会执行这里的代码

​      }else{

​        // 条件不成立就会执行这里的代码

​        // 条件最终结果为fasle, 就会执行这里的代码

​      }

​    特点: 两个大括号里面的代码一定会执行其中一个

​    */

```
 var age = 15;

​    if(age>=18){

​      console.log("已成年,可以进入网吧!");

​    }else{

​      console.log("未成年,回家写作业吧!");

​    }
```

##### 	3.多条件判断

​		 // 多条件判断语句

```
    // 需求：用户数字1-7其中一个数字，然后弹出对应的星期数。 比如：用户输入3， 弹出星期三



​    var num1 = +prompt("请输入一个数字(1~7):");



​    if(num1 === 1){

​      console.log("星期一");

​    }else if(num1 === 2){

​      console.log("星期二");

​    }else if(num1 === 3){

​      console.log("星期三");

​    }else if(num1 === 4){

​      console.log("星期四");

​    }else if(num1 === 5){

​      console.log("星期五");

​    }else if(num1 === 6){

​      console.log("星期六");

​    }else if(num1 === 7){

​      console.log("星期日");

​    }else{

​      // 这里的代码,当上面所有条件都不成立, 就执行这里的代码

​      console.log("请务必输入1-7");

​    }

​    // 从第一个条件开始判断,如果不满足条件就继续往下一个条件判断.

​    // 如果满足了条件,就执行对应的大括号里面的代码, 执行完大括号里面代码之后,整个语句就结束了.不会再继续判断了

​    // 如果所有条件都不满足,就执行else里面的代码
```

##### 		4.三元运算

条件 ? 结果1:结果2;    条件如果成立,整个式子就被结果1代替了,不成立就被结果2代替了

```
 // 需求：把num1和num2中较大的数字赋值给c
​    var num1 = 600;
​    var num2 = 100;
​    var c;
​    // 判断哪个大,就把它赋值给c
​    // if(num1>num2){
​    //   c = num1;
​    // }else{
​    //   c = num2;
​    // }
​    c = num1>num2?num1:num2;
​    console.log(c);
```

##### 5.switch-case

 小阔号里面的变量 全等于 case 后面的值得时候,这个case后面的代码就会被执行.

​     如果后面没有写break;则代码会继续往下执行.直到遇到break才结束 这个switch语句

​     如果小阔号里面的变量 都不等于所有的case后面的值,就会执行default 后面的代码



```
// 需求：用户数字1-7其中一个数字，然后弹出对应的星期数。 比如：用户输入3， 弹出星期三

​    var num = +prompt("请输入一个数字(1-7):")
​    switch(num){

​      case 1: alert("星期一");break;

​      case 2: alert("星期二");break;

​      case 3: alert("星期三");break;

​      case 4: alert("星期四");break;

​      case 5: alert("星期五");break;

​      case 6: alert("星期六");break;

​      case 7: alert("星期日");break;

​      default: alert("请输入正确的数字:1-7"); break;

​    }
```

## 15循环语句

##### 	1.for循环

​		    for(设置初始值; 设置循环条件; i递增/递减){

​      循环体

​    }



```
    for(var i = 初始值;i<=终止值;i++){

​      i<=终止值;成立 大括号里面的代码就会执行. 执行完之后,又做i递增, 在进行 i<=终止值;的判断.成立就又执行大括号里面的代码,执行完又做i递增 ....

​      直到 i<=终止值; 不成立了,循环就结束了

​    }

​    总结循环的使用: 一段代码想要重复执行很多遍的时候,就可以使用循环来做

​    // for循环最常用的一个格式.

​    for(var i=1;i<=10;i++){

​      console.log("打印一次ok!");

​    }

```

练习题

```
// 需求1： 快速输出5次"ok"；

​    // for(var i=1;i<=5;i++){

​    //   console.log("ok"+i);

​    // }



​    // // 需求2： 快速输出数字1到10

​    // for(var i=1;i<=10;i++){

​    //   console.log(i);

​    // }

​    // var sum = 0; // sum用来保存这个计算结果
​    // 计算:
​    // sum = sum + 1 = 0 + 1

​    // sum = sum + 2 = (0 + 1) + 2

​    // sum = sum + 3 = (0 + 1 + 2) + 3

​    // sum = sum + 4 = (0 + 1 + 2 + 3) + 4

​    // ...

​    // sum = sum + 10 = (0 + 1 + 2 + ...+ 9) + 10
​    // for(var i=1;i<=10;i++){

​    //   sum = sum + i

​    // }

​    // console.log("累加和为: ", sum);

​    var sum = 0;
​    for(var i=0;i<=10;i++){

​      // if(i是偶数){

​      if(i%2===0){

​        // 就把i加到sum里面去

​        sum = sum + i  

​      }

​     
​    }

​    console.log("偶数的累加和为: ", sum);
```

##### 2练习

 // 需求：

​    // 在浏览器中用*打印一个四行四列的矩形

​    // document.write() 在浏览器页面中输出内容

​    /*

​      ****

​      ****

​      ****

​      ****

​    */

输出星号图片

```
 for(var i=1;i<=4;i++){
​      for(var j=1;j<=4; j++){

​        document.write("*");
​      } 
​      document.write("<br />");

​    }
```

##### 3.行和内

 // 需求：

​    // 在浏览器中用*打印一个四行四列的矩形

​    // document.write() 在浏览器页面中输出内容

​    /*

​      *

​      **

​      ***

​      ****

​    */

```
    for(var i=1;i<=7;i++){ // i 是行数

​      for(var j=1;j<=i;j++){  // 第i行有i列

​        document.write("*");
​      }
​      document.write("<br />");
​    }
```

九九乘法表

 // 需求：

​    // 在浏览器中用*打印一个四行四列的矩形

​    // document.write() 在浏览器页面中输出内容

​    /*

​      *

​      **

​      ***

​      ****

​    */

```
    for(var i=1;i<=9;i++){ // i 是行数
​      for(var j=1;j<=i;j++){  // 第i行有i列
​        document.write(j+"x"+i+"="+(j*i)+"&nbsp;&nbsp;&nbsp;");
​      }
​      document.write("<br />");
​    }
```

##### 4.while循环

 // 循环: 重复执行某段代码



​    /*

​      var i=1;

​      while(i<=终止值){

​        // 小阔号里面的条件成立,就执行这里的代码,执行完,又回到小括号的条件,判断是否成立,如果还是成立就继续执行这里的代码...

​        // 直到 小括号里面的条件不成立, 循环就结束了

​        要循环执行的代码,写在这里

​        i++;

​      }

​    */

​    // 打印5次 ok

```
    // var i = 1;
​    // while(i<=5){
​    //   console.log("ok");
​    //   i++;
​    // }
```



​    // 打印1到10

  

```
  // var i = 1;
​    // while(i<=10){
​    //   console.log(i);
​    //   i++
​    // }
```



​    // 打印1到10的累加和

```
    var sum = 0;
​    var i=1;
​    while(i<=10){
​      sum = sum + i;
​      i++
​    }
​    console.log("和为:",sum);
```

##### 5.do  ....while

  /*

​      do{

​        循环体

​      }while(条件)

​    */



  // 求1-100之间所有整数的和

```
    var i = 1;
​    var sum = 0;
​    do{
​      sum += i;
​      i++;
​    }while(i<=100);
​    console.log(sum);

​    // do ... while 特点: 循环体里面的代码至少执行1次
```

## 16.结束语句

##### 1.break

​	break 结束的是整个循环, 后面的循环也不执行了

  //需求：在循环打印1到5的过程中，打印到3就停下来，不打印了，后面的4，和5也不打印了。(只打印1 2)

```
  for(var i=1;i<=5;i++){
​    // if(i等于3){
​    //   停止整个循环
​    // }
​    if(i===3){
​      break;
​    }
​    console.log(i);
  }
```

##### 2.continue

 // continue 结束的是本次循环,循环还是会继续

 // 需求：在循环打印1到5的过程中，打印到3就停下来，但是后面的4和5还会打印。 (1 2  4 5 )

```
  for(var i=1;i<=5;i++){
​    // if(i等于3){
​    //   结束本次循环
​    // }
​    if(i===3){
​      continue;
​      console.log("continue后面的代码不会执行");
​    }
​    console.log(i);
  }
```

2.1应用

 // 需求：让用户输入用户名和密码， (用户名为admin， 密码为123456 )，只要用户输入的用户名不是admin,密码不是123456， 就提示用户名或者密码错误。

​    // 直到用户名和密码都输入正确，才提示登录成功



```
    do{
​      var username = prompt("请输入用户名");
​      var password = prompt("请输入密码");
​      // 判断用户输入是否正确
​      // if(用户名和密码输入都正确){
​      //   结束整个循环
​      // }
​      if(username==="admin" && password==="123456"){
​        alert("登录成功!");
​        break
​      }
​      alert("用户名或者密码错误,登录失败!");
​    }while(true);
```

2.2应用

 // 需求：不断要求用户输入用户名，直到用户输入 "q" 才停止让用户输入。

​    

```
// do{

​    //   var str = prompt("请输入用户名");
​    //   // if(用户输入的是 "q"){
​    //   //   结束这个循环
​    //   // }
​    //   if(str === "q"){
​    //     break
​    //   }
​    // }while(true);
​    //   var str = prompt("请输入用户名");
​    //   if(str === "q"){
​    //     break
​    //   }
​    // }
​    // for(var i=1;true;){
​    //   var str = prompt("请输入用户名");
​    //   if(str === "q"){
​    //     break
​    //   }
​    // }

​    // 仅做了解

​    // var str;
​    // for(var i=1;str !== "q";){
​    //   str = prompt("请输入用户名"); 
​    // }
```

### 17数组

```
 var name1 = "张三";
​    var name2 = "李四";
​    var name3 = "王五";
​    var name4 = "赵六";
​    var names = ["张三","李四","王五","赵六", "李七", 4123];  // 定义一个数组, 把"张三","李四","王五","赵六"保存到names这个数组里面
```

​	     数组里面可以有任意多个数据,我们把它们称为元素.每一个元素都有自己的下标. 

​     第1个元素下标为0,第2个元素下标为1,第3个元素下标为2 ...  第n个元素,下标为n-1

​     下标有一个专业的称呼: 索引

​    可以通过下标来获取到元素 , 格式:  数组名[下标]

​     可以获取到数组中元素的个数: 格式:  数组名.length

​     修改王五,变成 张五,格式:  数组名[下标] = 新的值;

​     

​     一般来说,数组中数据类型最好保持一致, 便于操作. 有多个数据类型也不会报错,但是不便于后面的处理

##### 2.数组的遍历

​	  遍历数组的格式:   

​      for(var i=0;i<数组名.length;i++){

​        // i表示 下标

​        // arr[i]表示 当前找到的元素

​      }  

​      每找到一个元素,大括号里面的代码就会执行1次

```
  var arr = [10,20,30,40,50,60,70];
​    // 打印出数字中每一个元素

​    // console.log(arr[0]);

​    // console.log(arr[1]);

​    // console.log(arr[2]);

​    // console.log(arr[3]);

​    // console.log(arr[4]);

​    // 遍历一个数组   // 遍历: 一个一个地找, 一个一个地访问,这个过程叫做遍历

​    for(var i=0;i<arr.length;i++){

​      // 遍历数组的时候, i是它们的下标

​      // arr[i] 就是当前找到的这个元素  

​      console.log(arr[i]);

​      // arr[i] = arr[i] + 2

​    }
​    // console.log(arr);
```

###### 	案例

​	 **1.求数组中数字的和**

```
	var arr = [10,20,30,40,50,60,70];
​    var sum = 0 // 保存这个和
​    // 把数组中每一个元素追加到sum里面去
​    // sum+=arr[0]
​    // sum+=arr[1]
​    for(var i=0;i<arr.length;i++){
​      sum += arr[i]
​    }
​    console.log("和为:", sum);
```

​	**2.求数组中最大值**

```
	  var arr = [10, 20, 300, 40, 60, -5, 6, 5, 2];
​    // 定义一个变量,存放最大值, 假设最大值就是第一个元素
​    var max = arr[0];
​    // 一个一个地找arr中的元素(遍历), 和max进行比较

​    // 如果比max的值还要大, 就把这个值赋值给max

​    for(var i=0;i<arr.length;i++){
​      //arr[i] 找到的这个元素
​      if(arr[i]>max){
​        max = arr[i];
​      }
​    }
​    console.log("最大值为:", max);
```

##### 		3.求数组中去零

```
	  //我们可以通过  数组名[数组名.length] = 值, 来给数组中添加一个新的值
​    // 去掉数组中的0
​    var arr = [10, 20, 0, 30, 40, 0, 60, -5, 0, 6, 5, 0, 2];
​    var newArr = []; // 去掉了0之后的数组
​    // 一个一个地找arr中每一个元素,判断是不是为0,如果不等于0,就把它添加到newArr中.
​    for(var i=0;i<arr.length;i++){
​      if(arr[i]!==0){
​        // 把这个元素添加到newArr中:
​        newArr[newArr.length] = arr[i]
​      }
​    }
​    console.log(newArr);
```

## 18.字符串

##### 		1.str.split(" ")  

​		把字符串str按 " " 进行分割,分割成一个数组   以 什么字符进行 分割, 这个字符就会消失

```
	 var str = "hello world hello !"
​    var arr = str.split("e"); 
​    console.log(arr); // ["h", "llo world h", "llo!"]
```

​       **2.求用户所有数字的和**

```

​    var str = prompt("请输入一些数字,格式为:10,20,30,40");
​    // 1 分割字符串
​    console.log(str);
​    var arr = str.split(",");
​    console.log(arr);
​    var sum = 0;
​    for(var i=0;i<arr.length;i++){
​      // 做相加之前先转成数字,再加到sum中去
​      sum+=Number(arr[i])
​    }
​    console.log("和为:",sum);
```

​		**3.求最大值的索引值**

```
 var arr = [10,20,30,40,2,-5,30,50,45];
​    var max = arr[0]; // 保存最大值
​    var maxIndex = 0;  // 保存最大值的索引
​    for(var i=0;i<arr.length;i++){
​      // 如果数字中的这一项 arr[i] 大于max的话,就把arr[i]赋值给max
​      if(arr[i]>max){
​        max=arr[i]
​        // 如果数字中的这一项 arr[i] 大于max的话, 还需要更新maxIndex这个索引
​        maxIndex = i
​      }
​    }
​    console.log("最大值为:", max);
​    console.log("最大值的索引为:", maxIndex);
```



## 18.对象

###   	1.时间对象 Date()

```
	 var date = new Date();  // 创建一个日期对象(执行到这一行代码的时候的系统时间对象)
​    // 一个对象,具有很多功能
​    var y = date.getFullYear(); // 获取年份
​    var m = date.getMonth() + 1;  // 获取月份
​    var d = date.getDate(); // 获取几号
​    var h = date.getHours();  // 获取小时数
​    var m2 = date.getMinutes(); // 获取分钟数
​    var s = date.getSeconds(); // 获取秒数
​    var d2 = date.getDay(); // 获取星期数
​    console.log(y);
​    console.log(m);
​    console.log(d);
​    console.log(h);
​    console.log(m2);
​    console.log(s);
​    console.log(d2);
​    console.log("现在是: " + y + "-" + m + "-" + d + " " + h + ":" + m2 + ":" + s + ",星期" + d2);		
```

### 	2.Math()  数学对象

#### 		**2.1Math.random()随机数**

```
	// console.log(Math.random()); // 获取一个随机小数 , 取值范围 0到1 可以取0,取不到1
​    // [0,1)
​    // console.log(Math.random()*10); // 取值范围 0到10  取不到10  小数
​    // console.log(parseInt(Math.random()*10)); // 取值范围 0到10  取不到10  整数 0....9
​    // 以上是推导过程,可以不用记,只记下面这个结论:
​    // 【1】、取 0 ,1 , 2 .... n 中随机取一个整数, 公式:  parseInt(Math.random()*(n+1))
​    // 【2】、数组中随机取一个元素:  数组名[parseInt(Math.random()*数组名.length)]
​    var arr = ["张三", "李四", "王五", "赵六", "李七"];
​    console.log(arr[parseInt(Math.random()*arr.length)]);  // parseInt(Math.random()*arr.length)
```

## 19Function(函数)

​    **1.定义函数的格式**:  (准备好一个功能)

​      function 函数名(){

​        函数体 

​        这个功能涉及到的代码都写在这里 

​      }

​      如何使用功能:   功能名()     调用函数: 函数名()

​      特: 定义函数的时候,函数体里面的代码不会自动执行. 等到函数被调用的时候,才来执行里面的代码

​      函数名的命名规范跟变量名命名规范一致

​      初学者遵循 先定义后使用

​    */

​    // alert() // 使用alert这个功能   调用alert这个函数

```
    function myLog(){
​      console.log("hello 叩丁狼");
​    }
​    // 才能使用这个功能
​    myLog();
​    myLog();
​    // alert() 内置函数 浏览器提供的一个功能. (浏览器准备好给我们使用的)
```

​	**2.函数的作用:提高复用性**

```
	 function sum(num1,num2){
​      console.log(num1+num2);  
​    }
​    sum(10, 20)
​    sum(100, 200)
​    sum(1000, 3000)
​    sum(20, 40)
```

​	**3.函数的参数**

​			  定义函数的时候, 小括号里面的参数叫做形式参数,简称形参. 本质是一个变量

​    		调用函数的时候, 小括号里面的参数叫做实际参数,简称实参. 本质是一个确定值

```
 function sum(a, b){
​      console.log(a + b); // 注意:如果调用的时候没有传实参进来,就是undefined
​    }
​    sum(10);
​    sum(109,5780);
```

​	**4.函数的返回值**

​			  return 写在函数内部

​      作用1: return 可以把 return后面的结果返回到 函数调用的地方

​      作用2: return 可以终止函数的执行. 即函数内部return后面的代码不会执行 

​      一个函数,如果没有写return 它的调用结果是一个undefined

​      一个函数,如果只写return,后面没有返回值 它的调用结果也是一个undefined

 // 编写一个函数,实现相加的功能

```
    function sum(num1,num2){
​      var ret = num1+num2;
​      return ret
​      // console.log("12345789"); 不会打印了
​    }
​    console.log(sum(10,20));
​    console.log(ret1);
​    // console.log(typeof(a));
```

​	**5.函数的封装**

​		 **//1.圆的面积(圆的面积公式： 圆周率 * 半径的平方 )**

```
    function getYuan(r) {
​      var yuan = 3.14 * r * r
​      return yuan;
​    }
​    console.log(ret1);
​    var ret2 = getYuan(5);
​    console.log(ret2);
```

​		**2.   求两个数组中的最大值**

```
var arr1 = [10, 20, 30, 4, 2, 5, 1009];
​var arr2 = [100, 5, 4, 922, 2, 56, 4];
​    // 求arr1中的最大值
​    // 封装一个求最大值的函数
​    function getMax(arr){
​      var max = arr[0];
​      for(var i=0;i<arr.length;i++){
​        if(arr[i]>max){
​          max = arr[i]
​        }
​      }
​      return max
​    }
​    var ret1 = getMax(arr1); // 实参可以是一个数组
​    var ret2 = getMax(arr2);
​    // console.log(getMax(arr1));
​    // console.log(getMax(arr2));
​    console.log("两个数组中的最大值为:", ret1>ret2?ret1:ret2);
```

##### 6.函数的其他写法

```
   // function getSum(num1,num2){
​    //   return num1+num2
​    // }
​    // 定义函数的另外一种格式
​    // var getSum = function(num1,num2){
​    //   return num1 + num2
​    // }
​    // var ret1 = getSum(10,20);
  // console.log(ret1);
```

​     **匿名函数**

```
    odiv.onclick = function(num1,num2){
​      return num1 + num2
​     }
```

​     **自调用函数**

```
    ;(function(){
​      // 可以有自己的一个独立的作用域,可以避免命名的相同造成的变量覆盖
​      var a = 10;
​      console.log(a);
​    })();
​    ;(function(){
​      var a = 20;
​      console.log(a);
​    })();
```

#### 7函数的作用域

​		**全局作用域**: <u>script标签包围的这个作用域, 引入的js文件的作用域</u>

​    	 **局部作用域**: <u>各个函数内部的作用域</u>

​    	 (了解: ES6里面还有一种块级作用域  { })

```
  var a = 10; // 全局变量,在函数外面定义的变量,可以在函数内部和外部使用
​    function func(){
​      var b = 20; // 局部变量, 在函数内部定义的变量,只能再函数内部使用
​      console.log(a);
​      console.log(b);
​    }
​    func();
​    console.log(a);
​    console.log(b); // 报错
​      var b = 203; // 局部变量, 在函数内部定义的变量,只能再函数内部使用
​      console.log(a);
​      console.log(b);
​    }
```

​			1.有var和没有var的区别

​		**没有写var** 定义的是全局变量

​    	 **带var的 定义的变量**,是本作用域下能够使用的变量

```
  var b = 20;
​    function func(){
​      var a = 10;
​      console.log(a);//10
​    }
​    func();
​    console.log(a);//报错
```

#### 8函数的作用域链

 	**作用域链的产生:** 出现在函数嵌套的时候

 	 **作用域链的访问原理:**

​    如果当前作用没有这个变量, 往外面一层作用域去找数据.(就近原则)

​    如果一直找到全局,都没有这个变量就会报错.

```
  	var a = 10;
​    function func(){
​      // var a = 20;
​      function fn_in(){
​        // var a = 30;
​        console.log(a);
​      }
​      fn_in()
​    }
​    func()
```

#### 9函数的预解析

 **预解析:** 浏览器在执行js之前, 会把var 定义变量语法 和 function函数 提到当前作用域的最前面,但是没有赋值

​    浏览器的预解析过程包含哪些内容: (哪些代码会在预解析阶段被提前):

​    **带var 的定义变量**

​    **function 函数的定义**

```
    // console.log(a);
​    // var a = 10;
​    func()
​    function func(){
​      console.log("func");
​    }
​    
```

**预解析的练习**

```
  // 第1题

​    // console.log(a,b);  // undefined undefined
​    // var a=12;
​    // var b=13;

​    // sum(); // 1

​    // function sum(){

​    //   console.log(1);  

​    // }

​    // 以上代码预解析成:
​    
​    // var a;
​    // var b;
​    // function sum(){
​    //   console.log(1); 
​    // }

​    // a=12;

​    // b=13;

​    // sum(); // 1

​    


​    // 第2题

​    // console.log(a); // undefined
​    // var a=12;
​    // function fn(){
​      
​    //   console.log(a); // undefined 
​    //   var a=13;
​    // }
​    // fn();
​    // console.log(a); // 12
​    // 以上代码预解析成:
​    // var a
​    // function fn(){
​    //   var a
​    //   console.log(a);
​    //   a=13;
​    // }
​    // console.log(a); 
​    // a=12;
​    // fn();
​    // console.log(a);
​    //---------------------------------------------------------

​    // 第3题
​    console.log(a); // undefined
​    var a=12;
​    function fn(){
​      console.log(a); // 12
​      a=13; 
​    }
​    fn();
​    console.log(a) // 13
​    var a
​    function fn(){
​      console.log(a); 
​      a=13; 
​    }
​    console.log(a); // undefined
​    a=12;
​    fn();  // 12
​    console.log(a) // 13
```

