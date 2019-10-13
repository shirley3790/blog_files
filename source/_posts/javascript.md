---
title: javascript超神之旅day1-js基础了解
date: 2019-08-28 12:43:25
tags:
	- javascript
categories:
	- 前端知识
---

##### JavaScript的诞生

------

​	javaScript 诞生于 1995 年。由Netscape(网景公司)的程序员Brendan Eich(布兰登)与Sun公司联手开发一门脚本语言, 最初名字叫做Mocha，1995年9月改为LiveScript。12月，Netscape公司与Sun公司（Java语言的发明者）达成协议，后者允许将这种语言叫做JavaScript。这样一来，Netscape公司可以借助Java语言的声势（趁热度）。<!--more--> 

​	1996年3月， Netscape公司的浏览器Navigator2.0浏览器正式内置了JavaScript脚本语言. 此后其他主流浏览器逐渐开始支持JavaScript。能够实现网页特效和数据交互。 

​	那什么是脚本？脚本的意思就是这门语言不能独立运行，需要嵌入到其他语言才能执行，js需要嵌入在html里面才能运行产生效果。

##### js的作用

------



###### 用户交互

![用户交互](https://raw.githubusercontent.com/shirley3790/myblogs_imgs/master/1567412499021.png)

###### 表单验证

![表单验证](https://raw.githubusercontent.com/shirley3790/myblogs_imgs/master/1567412561710.png)

###### 网页特效

![网页特效](https://raw.githubusercontent.com/shirley3790/myblogs_imgs/master/1567412629910.png)

用途：使用它的主要目的是，验证发往服务器端的数据、增加 Web互动、加强用户体验度等。可用于开发网站、游戏、移动端app等 。

##### js版本

------



> JavaScript这种语言的基本语法结构是由ECMAScript来标准化的, 所以我们说的JavaScript版本一般指的是ECMAScript版本. 

- 1997年7月，ECMAScript 1.0发布。
- 1998年6月，ECMAScript 2.0版发布。
- 1999年12月，ECMAScript 3.0版发布。
- 2007年10月，ECMAScript 4.0版草案想要提交ECMA组织, 但由于4.0版的目标过于激进, 改动太大, 并且微软,谷歌等大公司极力反对；一直到2008年7月ECMA开会决定，中止ECMAScript 4.0的开发（即废除了这个版本）
- 2009年12月，ECMAScript 5.0版正式发布
- 2011年6月，ECMAscript 5.1版发布
- 2015年6月，ECMAScript 6正式发布，并且更名为“ECMAScript 2015”。

##### js优势

------

目前苹果公司的Safari, 谷歌的Chrome,微软的IE等几乎全部浏览器都支持JavaScript, 基于JavaScript开发的库和框架数不胜数, 例如: jQuery,Angular, React等…

JavaScript将在前端和服务器端(Node.js)有更好的发展。

##### js组成

------



> javascript = ECMAScript + BOM + DOM 

1. 核心(ECMAScript)：标准、规则
2. 浏览器对象模型(BOM) ：js赋予我们操控窗口的能力，比如：弹窗、复制、粘贴、历史管理、刷新页面……
3. 文档对象模型(DOM)：节点的增删改查、属性的设置和获取……

##### JS和H5的关系

------

h5全称html5,不是单纯的html的第5个版本，而是一项最新的web标准，是html、css、javascript等技术的集合；你也可以称之为“大前端”，就是前端后端都要会，但是偏向于前端。

全栈：精通前端+后端技术。



##### js代码的编写位置

------



- script标签 

```
<script type="text/javascript">
    alert('你好')
</script>
```

- js文件 ：独立的js文件需要引入页面才能执行 （js是脚本语言）

```
<script type="text/javascript" src="js/common.js"><script>
```

- script标签属性
  - type:类型
  - src :js文件路径
    带src属性的script标签内不能写js代码

###### 案例：js的引入

```
<script src="js.js">
        /*
            知识点：
                * js引入的方式两种：
                    - 通过src属性引入js文件
                    - 写在页面内
                * 注意事项：如果已经写了src属性，在里面写的js代码就无效
                * js的组成：
                    * ECMAScript：标准，语法规定  我：01011101，编译器
                    * DOM：文档对象模型，节点的操作，查找、删除、创建、复制、插入节点，js赋予我们操控节点的能力
                    * BOM:浏览器对象模型。复制、粘贴，js赋予我们操控窗口的能力
                * h5：大前端，前后端都需要会，精通前端，html、css、js、部分后端技术：php、nodejs
        */
        // alert('999');写在这里的代码无效，因为已经引入了js文件
    </script>
<script>
    //推荐把js放到末尾，不然js过大，放在前面，会造成页面空白，用户体验不好
    alert('我的第一个js');
</script>
```

##### 变量的定义

------



- 变量定义(使用var关键字)：变量是存储数据的容器
  `var age; //var 是关键字，age是变量名，这句话叫做声明变量，也可以叫定义了一个变量`
- 赋值：
  `age = 20;//这个写法是没有写var的，但是也可以定义一个变量，并且马上赋值，=在计算机里面叫做赋值符号，就是把右边的内容放到左边的容器里面。虽然不写var也可以定义变量，但是不推荐这样写，因为不写var的时候实际上这个变量就变成了全局变量（后面讲到作用域的时候会说明为什么不好）。`
- 定义的同时赋值：（推荐写法：声明就马上赋值）
  `var age=20;`
- 可以一次定义多个变量：
  `var name="薛之谦", age=18, weight=108;`

##### JS代码规范

------



- JS变量的命名规范
  - 变量名必须是数字,字母,下划线`_`和美元符`$`组成;

  - 第一个字符不能为数字

  - 不能使用关键字或保留字

    - 关键字：这些单词在计算机中有特殊的含义，就不能用这些单词来作为变量名、参数名和函数名。
    - 保留字：有些单词，在js中准备用于扩展使用，备用单词也不允许作为变量名、参数名和函数名。

| break    | do       | instanceof | typeof  |
| -------- | -------- | ---------- | ------- |
| case     | else     | new        | var     |
| catch    | finally  | return     | void    |
| continue | for      | switch     | while   |
| debugger | function | this       | with    |
| default  | if       | try        | delete  |
| throw    | in       | class      | extends |
| const    | let      | export     | import  |

> 关键字保留字参考：<https://www.runoob.com/js/js-reserved.html> 

- 代码可读性
  - 标识符区分大小写，如：age和Age是不同的变量。但强烈不建议用同一个单词的大小写区分两个变量。

  - 变量命名尽量遵守驼峰原则: myStudentScore（第二个单词开始首字母大写）

  - 变量命名尽量见名知意（建议下载有道，查单词）

  - 保持代码缩进（遇到花括号要换行缩进）

  - JS语句的末尾尽量写上分号;（其实不写没错，但是建议写，增加代码可读性）

  - 运算符两边都留一个空格, 如 `var n = 1 + 2`;（细节要注意）

  - 注释

    - 单行注释：//注释内容

    - 多行注释（和CSS注释一样）： `/*注释内容*/`多行注释里面不能嵌套

###### 案例：代码规范

```
<script>
    /*

        js是世界上最灵活的语言：不严谨

        变量的定义：
            * 变量名必须是数字,字母,下划线_和美元符$组成;
            * 第一个字符不能为数字
            * 不能使用关键字或保留字
    */

    var num = 666;//var 关键字，意思定义一个变量，num就是变量名，把右边的内容存到左边的变量里面
    num = '韭菜一汤';//一个变量只能存一个值，如果再存值，会被覆盖
    var str1 = str2 = '婧婧';
    // alert(num);//?拿到的是最新的num的值，建议不要alert检测代码，会阻塞后面代码的运行

    var box = document.getElementById('box');//通过id查找节点
    box.innerHTML = '我喜欢旅游';//设置内容
    var divLogin;
    var fruits;
    //打印到控制台
    console.log(num, str1, str2);//?

    var a = 6;
    var b = 7;
    var c = a * b;
    console.log(c);//?

    //建议声明马上就赋值
    var age = 0;//如果不确定这个值，先初始化给个默认值，防止undefined
    console.log(age);//undefined 声明未赋值就会报这个错误
    age = 18;//覆盖

    /*  
        变量的规范
            $this 合法
            _this 合法
            var 不合法，关键字
            class 不合法,关键字
            6str 不合法，数字开头
            -num%ss 不合法，出现特殊符号
            for 不合法，关键字
    */

    var studentInf;//学员信息
    var username;
    var psw;

    /*
        符号： 数学            程序
            <> 大于号小于号    尖括号
            [] 中括号         方括号
            {} 大括号         花括号
            () 小括号         圆括号

            遇到花括号就要换行缩进
    */

    //函数
    function show() {
        console.log(123);
        console.log(123);
        console.log(123);
        console.log(123);
        console.log(123);
    }

    show();//加分号

</script>
```

##### JS数据类型

------



- 基本数据类型
  - Number：数字
    - NaN：是一个特殊的值，即非数值(Not a Number)。数学运算无法得到数字时，就会返回NaN
      - 不代表任何值，也不等于任何值，甚至自己都不等于自己
      - 任何数据与它运算都返回NaN
      - isNaN(a)：用来判断a到底是不是非数字,返回布尔值
  - Boolean: 布尔类型
    Boolean 类型有两个值：true和false
  - String：字符串
    - 用引号（单/双引号）括起来的内容

- 特殊数据类型
  - Null
    Null 类型是一个只有一个值的数据类型，即特殊的值 null。它表示一个空对象引用(指针)，而 typeof 操作符检测 null 会返回 object

  - Undefined

    Undefined类型只有一个值，即特殊的 undefined，在使用 var 声明变量，但没有对其初始化时，这个变量的值就是 undefined

    - 与not defined的区别(not defined:未声明)

- 引用数据类型 
  - Array：数组
  - Object：对象

- 数据类型判断 ：typeof 

```
typeof 'html5'; //=>string
typeof 100; //=>number
typeof true //=>boolean
typeof null //=>object
```

- 数据类型转换 
  - 隐式类型转换 ：如果运算不能进行下去，内部就会尝试进行数据类型的转换 支持隐式转换的运算：逻辑运算、关系运算、算术运算 

  - 强制类型转换：利用内置函数进行转换 

    | 值(a)     | 转换为 | 字符串String(a) | 数字Number(a) | 布尔值Boolean(a) |
    | --------- | ------ | --------------- | ------------- | ---------------- |
    | undefined | =>     | "undefined"     | NaN           | false            |
    | null      | =>     | "null"          | 0             | false            |
    | true      | =>     | "true"          | 1             |                  |
    | false     | =>     | "false"         | 0             |                  |
    | ""        | =>     |                 | 0             | false            |
    | "1.2"     | =>     |                 | 1.2           | true             |
    | "one"     | =>     |                 | NaN           | true             |
    | 0         | =>     | "0"             |               | false            |
    | -0        | =>     | "0"             |               | false            |
    | NaN       | =>     | "NaN"           |               | false            |
    | 1         | =>     | "1"             |               | true             |

###### 案例：隐式类型转换

```
<script>

    /*
        数据类型：
            * 基本数据类型：
                * 值类型：string/number/boolean
                * 特殊类型：null/undefined
            * 复合数据类型(引用类型):array数组、对象 object{}
            * 检测数据类型：typeof(数据)，返回数据类型
    */

    //值类型
    var str = '鸡你太美';//可以单引号可以双引号，有引号装起来的就是字符串类型
    console.log(str);
    console.log(typeof(str));//string
    
    var num = 88;
    console.log(num);
    console.log(typeof(num));//nubmer

    //数学运算无法运行的时候，就是显示NaN
    var n1 = 12;
    var n2 = '10';
    var n3 = n1 + n2;
    console.log(n3);//1210 ? +在程序里面有两个功能，如果两边都是数字，就是纯粹的数学运算相加；如果其中一边是字符串，就是字符串拼接(得到一个字符串)

    var m1 = 12;
    var m2 = '10';
    var m3 = m1 - m2;//隐式类型转换：系统帮你偷偷的转换了数据类型再相减
    console.log(m3);//2

    var k1 = 12;
    var k2 = 'good';
    var k3 = k1 - k2;
    console.log(k3);//NaN 
    console.log('数据类型是' + typeof(k3));

    var isok = true;//布尔值  真
    console.log(typeof(isok));//boolean
    console.log(NaN == NaN);//false

    //isNaN() 这不是一个数字，返回true：这不是数字； false：真是数字
    console.log('k3是数字吗?' + isNaN(k3));
    console.log('k2是数字吗?' + isNaN(k2));
    
    //特殊类型
    var price;
    console.log(price);//price is not defined 还没有定义这个变量;undefined 声明未赋值

    //验证null
    var usn = document.getElementById('usn');
    if(usn.value) {
        //非空验证-正则验证-ajax传给后端
        console.log('非空');
    }else{
        //空
        console.log('空');
    }

</script>基本数据类型转换：利用内置函数进行转换
```

###### 案例:强制类型转换

```
<script>
    /*
        04数据类型的转换:
            * 强制类型转换：系统提供一些方法，让你强制的把某个数据类型转成另外一种
                * String(要转的数据) ：得到字符串(重点)
                * Number(要转的数据) ： 得到的数字(重点)
                * Boolean(要转的数据) :得到布尔值
                * parseInt() : 把字符串转成数字类型，整型，整数(重点)
                * parseFloat() :把字符串转成数字类型,但是可以保留小数部分，float 浮点数，小数
            * 隐式类型转换：系统会自动帮你转换数据类型，转不了就返回NaN
                
    */

    var num = 123;
    var str = String(num);//数字转成字符串
    console.log(num,str);//?

    //字符串转成数字
    var price = '88';
    var priceNum = Number(price);
    console.log(priceNum);

    var box = document.getElementById('box');
    var ele = null;
    //什么是真和假？
    //真：true、非零数字、表达式为真的、非空字符串、非空对象 box
    //假：false、数字0、表达式为假的、空字符串、空对象 ele、undefined

    // 5>3
    // if(表达式) {//在if语句后面的条件表达式里面，会自动的转换成布尔值
    //     //返回真，执行这里的代码
    // }else{
    //     //返回假：执行这里的代码
    // }


    //parseInt()

    var all = '999';
    var newAll = parseInt(all);//1.把字符串转成数字类型
    console.log(all,newAll);

    var n1 = '32num';
    var n2 = parseInt(n1);//2.提前字符串中数字开头的数字部分，并转成数字
    console.log(n1,n2);

    var n3 = 67.8;
    var n4 = parseInt(n3);//3.取整
    console.log(n3,n4);

    //隐式类型转换:- * / % ==
    var n1 = 4;
    var n2 = '4';
    console.log(n1 + n2);//24,+ 不会进行隐式转换
    console.log(n1 - n2);
    console.log(n1 * n2);
    console.log(n1 == n2);//?true  == 进行隐式转换,等于
    console.log(n1 === n2);//false 恒等，全等,不能隐式转换，直接比较


    //需求：把字符串转成数字
    var num = '90';
    console.log(Number(num));
    console.log(num - 0);
    console.log(num * 1);
    console.log(num / 1);
    console.log(parseInt(num));
    console.log(parseFloat(num));
</script>
```

##### 

##### 运算符--算数运算符

------

+, -, *, /, %:加,减,乘,除,取余(取模) 

- +号用途一：当加号两边都是数字类型的时候，实现数学运算相加
- +号用途二：只要加号一边是字符串的时候，实现的是字符串的拼接

###### 案例：算数运算符的运用

```
<script>
    /*
        运算符：
            * 算术运算符：+ - * / %(取余，求模)
            * 逻辑运算符：&& 与 、|| 或 、! 非
            * 比较运算符：< > >= <= == === != !==,经过比较运算符后得到的是真和假
            * 三目运算符：明天再见  ?:
            * 赋值运算符：=  += -= *= /= %=
            * 一元运算符:-- ++ 自增、自减 i++  ++i
    */
    //算术运算符: + 可以做加法运算；可以拼接字符串
    var n1 = 88;
    var n2 = '90';
    var n3 = n1 + n2;//8890

    //取余： %
    var num = 9 % 2;
    console.log(num);//余数 1
</script>
```

###### 案例：战士作战

```
<script>
    /*
        为抵抗洪水，战士连续作战89小时，编程计算共多少天零多少小时？

        需求：给你89小时=转成  xx天xx小时
    */

    var hours = 89;
    var day = parseInt(hours / 24);//天数
    var hour = hours % 24;
    console.log(day,hour);
    console.log('89小时：' + day + '天' + hour + '小时');

    //秒：789秒：xx分xx秒
    var secs = 789;
    var mins = parseInt(secs / 60);//分
    var sec = secs % 60;
    console.log(mins,sec);
    
</script>
```

###### 案例：一个引号引发的公司倒闭

```
/*
        一个引号引发的公司倒闭

        知识点：打印数据
            * 弹窗类：都会阻塞代码的执行，所以要少用
                * alert() 弹窗
                * confirm() 能够确定和取消
                * prompt() 接收前端的数据
            * document.write(all); 打印内容到页面
            * 打印到控制台：console.log()
    */
    var jingjing = '20000';
    var laoxie = '1999';
    var linjie = 2999;
    var laoyao = 999;
    var yongge = '3999';
    var all = jingjing + laoxie + linjie + laoyao + yongge;//拼接功能
    console.log(all);
    document.write(all);

    var res = confirm('你帅吗？');
    console.log(res);

    var con = prompt('你今年多大？');
    console.log(con);
```

##### 运算符--逻辑运算符（返回布尔值）

------

- &&: 逻辑与 （这里注意：与的优先级比或要高）
  - 特性一：两边为真才为真
  - 特性二：左边为假，不再运行右侧
- ||：逻辑或
  - 特性一：两边为假才为假
  - 特性二：左边为真，不再运行右侧
- !: 逻辑非 （取反，用于做开关）

```
!true //=> false
!false //=> true
```

###### 案例：逻辑运算符和判断语句的使用

```

    //逻辑运算符：&& 与 、|| 或 、! 非

    //与：两边都为真才为真；或：只要有真则真；!非，取反

    //桂林：乐满地,3.7女生节，女生穿短裙免费

    var gender = '男';
    var cloth = '短裙';
    //判断语句
    if(gender == '女' || cloth == '短裙') {
        //满足条件：女生穿短裙
        console.log('恭喜你可以免费游玩乐满地！');
    }else {
        console.log('对不起,你还是买票吧！');
    }

    // if(gender == '女') {
    //     //女生
    //     if(cloth == '短裙') {
    //         //女生，短裙
    //         console.log('恭喜你可以免费游玩乐满地！');
    //     }else {
    //         console.log('请换短裙吧！');
    //     }
    // }else {
    //     //非女生
    //     console.log('你还是去买票吧！');//poy
    // }
```

###### 案例：非！（取反）的应用-下拉菜单的实现

html结构和样式：按钮和一个盒子，盒子先隐藏，一会点击一次就出现，再点击又隐藏，来回切换

```
<style>
        #box{
            width: 200px;
            height: 200px;
            background: red;
            display: none;
        }
    </style>
</head>
<body>
    <input type="button" value="下拉菜单" id="btn">
    <div id="box"></div>
</body>
```

js代码实现：开关的应用

```
<script>
    /*
        怎么让一个盒子隐藏：
            * display :none;
            * height:0
            * width:0
            * opacity:0
            * div遮罩
            * left
            * top
    */

    /*
        需求：实现一个下拉菜单效果，点击就出现，再点击又隐藏
            * 找到两个节点:btn box
            * 给btn绑定点击事件，功能就是控制box的显示和隐藏
    */

    var btn = document.getElementById('btn');
    var box = document.getElementById('box');
    var isok = true;//开关
    //绑定事件: 节点.事件名 = function() { 功能 }
    btn.onclick = function() {//函数
        // alert(123);
        //节点名.style.属性名 = 属性值
        if(isok) {//true
            box.style.display = 'block';
        }else{
            box.style.display = 'none';
        }
        isok = !isok;
    }

</script>
```

##### 运算符--关系运算符（返回布尔值）

------



- ==(等于), !=(不等于)
- <(小于)、>(大于)、<=(小于等于)、>=(大于等于)
- ===、恒等于/全等于，比较的时候要求值和类型都相等（不会进行类型隐式转换）
- !==、不全等于
- 关系运算符的比较规则: 
  \1. 数字和数字比较, 直接比较大小
  \2. 数字和字符串比较, 字符串转换为数字后再比较
  \3. 字符串和字符串比较, 进行字符的ASCII码值比较

```
/*
        关系运算符的比较规则: 
        1. 数字和数字比较, 直接比较大小
        2. 数字和字符串比较, 字符串转换为数字后再比较
        3. 字符串和字符串比较, 进行字符的ASCII码值比较
    */
   var num1 = '23';
   var num2 = 34;
   console.log(num1 < num2);

   var str1 = 7;
   var str2 = 'b';//98
   console.log(str1 > str2);
```

##### 运算符--赋值运算符

------

- =
  `var num1=10;//表示把10赋值给num1变量`
- +=：在原来的内容基础上追加内容
  `str += 'test' <==> str = str + 'test'`
- -=：
  `var n=10; n -= 2 <==> n = n - 2`
- *=,/=,%=

赋值符号里面+=是用得比较多的，后期经常用于拼接字符串，比如我要得到下面结构的字符串：

```
<div>
        <ul>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
        </ul>
    </div>
```

我可以一段段的拼接出来：

```
<script>

    //赋值运算符：=  += -= *= /= %=

    var num = 7;
    // num = num + 8;可以换成下面的写法
    num += 8;
    console.log(num);//15

    //拼接数据：熟悉拼接，以后会经常用
    var html = '<div><ul>';
        html += '<li></li><li></li><li></li><li></li><li></li><li></li>';
        html += '</ul></div>';
        console.log(html);
</script>
```

##### 运算符--一元运算符

------

- ++: 自增1（在原来的数值基础上加1）
- –：自减1（在原来的数值基础上加1）

前置： 

```
var num = 10;
++num;--num;
```

后置：

```
var num = 10;
num++;num--
```

总结：

- 针对自身都会加一（减一）；
- 针对返回值： 
  - 前置：返回加（减）之后的值
  - 后置：返回加（减）之前的值

```
//一元运算符
    var num = 2;
    // num = num + 1;
    // num += 1;
    var r1 = num++;
    console.log(num);//3 自身会加一
    console.log(r1);//2 后置返回值是返回加之前的值，还是2

    /*
        ++: 自增1（在原来的数值基础上加1）
        --：自减1（在原来的数值基础上加1）
            前置：++num
            后置：num++
                * 自身：都加1
                * 返回值：
                    前置，返回加之后的值；
                    后置：返回加之前的值；
    
    */
    var m = 1;
    var res = m++ + ++m + m + m-- + m + m++;
    //   m  = 2      3    3   2     2   3  自身
    //   res= 1  +  3  +  3 + 3 + 2 + 2  返回值
    //m? res?
    console.log(m,res);
```

##### 操作符优先级

------

| 运算符                                 | 描述                                     |
| -------------------------------------- | ---------------------------------------- |
| ., [], ()                              | 对象成员存取、数组下标、函数调用、分组等 |
| ++, –, ~, !, delete, new, typeof, void | 一元运算符                               |
| *, /, %                                | 乘法、除法、取模                         |
| +, -                                   | 加法、减法、字符串连接                   |
| <, <=, >, >=, instanceof               | 关系比较、检测类实例                     |
| ==, !=, ===, !==                       | 等于、恒等(全等)                         |
| &&                                     | 逻辑与                                   |
| `||`                                   | 逻辑或                                   |
| ?:                                     | 三元运算条件                             |
| =, +=, -=, *=, /=, %=                  | 赋值、运算赋值                           |

##### 作业

------



> 1.给你6789秒，你转成：xx时xx分xx秒；
>
> 2.小米首页切图布局：https://www.mi.com/,相同模块保留一个即可
>
> 3.给定一个三位数，分别把这个数字的百位、十位、个位算出来并显示。
>
> 4.判断输入框输入的年份是否为闰年 （能被4整除但不能被100整除，或者能被400整除的才叫闰年 ）
>
> 拓展：
>
> 1.计算商品价格 ：总价=数量*单价