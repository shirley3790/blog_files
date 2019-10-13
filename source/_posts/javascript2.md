---
title: javascript超神之旅day2-程序结构
date: 2019-09-29 20:50:20
tags:
	- javascript
categories:
	- 前端知识
---

##### 程序的三大流程控制 

------

> 我们的计算机在执行一个程序的时候，最基本的方式是一条语句接一条语句的执行。但不可能所有的问题都能用顺序执行方式就能解决，总会有一些跳转。采用结构化的程序设计，可以大大提高开发程序的速度、提高程序的可读性、程序运行的速度和效率 

- 顺序：从上朝下执行的代码就是顺序
- 分支(选择)：根据不同的情况，执行对应代码
- 循环：重复做一件事情<!--more--> 

##### 程序流程-顺序（代码从上到下执行）

------

代码默认就是从上到下执行，所以前面的代码出错（有bug）后面的就不能再继续运行，利用这个我们可以检测代码出错的地方，方便修改bug，结合控制台打印到页面：

```
/*
        07检测代码
            * 控制台：console.log() 边做边检查
            * 断点
    */

    //代码块1
    console.log('111');//打印出来了，说明什么？证明上面的代码没有问题
    //代码块2
    console.log(222);//能打印出来，说明什么？问题出在代码块3这里
    //代码块3
    console.log(333);//没有打印出来：说明什么?说明上面代码有问题
```

##### 程序流程-分支-if语句

------

if语句可以实现单分支、双分支、多分支

- 单分支

  ```
  if(条件){
      //条件成立(返回true)时，执行这里的代码，否则不执行
  }
  ```

- 双分支：当if括号内的表达式结果成立，执行执行代码1，否则执行执行代码2 

  ```
  if(条件){
          //代码1
          //条件成立(返回true)时，执行这里的代码，忽略以下代码
      }else{
          //代码2
          //条件不成立(返回false)时，执行这里的代码
      }
  ```

  ###### 案例：判断一个数是偶数还是奇数，并输出判断结果；

- 多分支：从上往下，满足哪个条件就执行其相对应的语句，都不满足时，执行最后的else的语句

  ```
  if(条件1){
      //条件1成立(返回true)时，执行这里的代码，忽略以下代码
  }else if(条件2){
      //条件2成立(返回true)时，执行这里的代码，忽略以下代码
  }
  ...
  else{
      //以上条件都不成立(都返回false)时，执行这里的代码
  }
  ```

###### 案例：if语句的使用

```
//单分支：临界值判断
    var price = 49;
    if(price < 50) {
        console.log('符合我的需求，买买买！');
        document.write('符合我的需求，买买买！');
    }

    //双分支：if else
    var gender = '男';
    if(gender == '女') {
        document.write('<br>可以免费游玩乐满地一天！');
    }else {
        document.write('<br>你还是买票吧！');
    }

    //多分支：判断成绩
    //要有一个if；后面紧跟若干个else if；最后的else可以不写;条件表达式一定是写在if后的圆括号里面
    var score = 78;
    if(score >= 0 && score < 60) {
        document.write('<br>你留级吧');
    }else if(score >= 60 && score < 80) {
        document.write('<br>成绩良好，继续加油哦！');
    }else if(score >= 80 && score <= 100){
        document.write('<br>你真秀！');
    }else {
        document.write('<br>请输入100以内分数');
    }
```

##### 程序流程-分支-三元运算符（三目运算符）

------

格式：条件 ? 条件成立代码 : 条件不成立代码 

```
var a=20;
var b = 50;
var sum = a>b ? a-b : a+b;
```

###### 案例：求两个数的最大数 

##### 程序流程-分支-switch语句

```
switch(值) {
    case value1: //要求value1与值恒等
        //如果表达式的值恒等于value1，代码从这里开始执行
        break;
    case value2:
        //如果表达式的值恒等于value2，代码从这里开始执行
        break;
    case value3: 
        //如果表达式的值恒等于value3，代码从这里开始执行
        break;
    case value4: 
        //如果表达式的值恒等于value4，代码从这里开始执行
        break;
    default: 
        //如果以上条件都不成立，默认执行这里的代码
}
```

- switch语句在比较值时使用的是全等操作符，因此不会发生类型转换
- case: 当符合条件时，会从符合条件的那一条case语句开始，依次顺序向下执行，直到结束或遇到break
- break: 跳出switch语句
- default: 当所有的case都不满足的情况下会执行defalut下面的语句

###### 案例：今天星期几？

```
//利用switch判断今天星期几

    //日期对象

    var date = new Date();//获取完整的时间戳
    var year = date.getFullYear();//年
    var month = date.getMonth() + 1;//月 月份是从0开始的
    var day = date.getDate();//日
    var hours = date.getHours();//时
    var mins = date.getMinutes();//分
    var secs = date.getSeconds();//秒
    var week = date.getDay();//星期几 从0开始：星期天  0-6
    console.log(year, month, day, hours, mins, secs, week);

    //判断今天星期几
    switch (week) {
        case 0:
            document.write('今天星期天');
            break;
        case 1:
            document.write('今天星期一');
            break;
        case 2:
            document.write('今天星期二');
            break;
        case 3:
            document.write('今天星期三');
            break;
        case 4:
            document.write('今天星期四');
            break;
        case 5:
            document.write('今天星期五');
            break;
        case 6:
            document.write('今天星期六');
            break;
    }
```

###### 案例：用switch进行成绩判断

```
//成绩的判断
    var score = 88;
    switch (true) {
        case score >= 0 && score < 60:
            document.write('你需要留级啦！');
            break;
        case score >= 60 && score < 80:
            document.write('你的成绩良好');
            break;
        case score >= 80 && score <= 100:
            document.write('你好秀哦，秀儿');
            break;
        default :
            document.write('不是分数的范围');
            break;
    }
```

##### 程序流程-循环-while循环

------

- 循环就是重复做一件事, 在JS中指的是循环执行某部分代码.

- 循环结构是程序中一种很重要的结构，其特点是在给定条件成立时，反复执行某程序段，直到条件不成立为止

- 只要条件成立，就会不断地执行花括号里的语句 编写条件时，要避免出现死循环 

  ```
  //变量初始化
  while(条件){
      //条件成立就会不断地执行这里的代码，直到条件不成立
      //所以这里一般会伴随着条件的更新
  }
  ```

- 循环三要素：初始值、判断值、自增值（自减值）

  ###### 案例：为什么要循环，隔行变色的实现

  ```
  /*
          隔行变色
  
          知识点：
              * 获取集合的长度：集合.length
              * lis[0] :下标从0开始
              * 怎么添加属性和值：
                  节点.属性名 = 属性值；
      */
  
      var list = document.getElementById('list');//单个
      var lis = list.getElementsByTagName('li');//集合,通过下标的方式获取到某一个节点
      console.log(lis.length);//集合的长度 5
      console.log(lis[0].innerHTML);//找到第一个li并把里面的值打印出来
  
      //添加属性的方法
      // lis[0].title = '第一个节点';//添加title值
      // lis[0].style = 'width:200px;height:200px;';//添加行内样式：方式一
      // lis[0].style.background = 'red';//添加具体的行内样式:方式二，常用
      // console.log(lis[0].title);//获取title值
  
      //隔行变色
      // lis[0].style.background = '#58bc58';
      // lis[1].style.background = 'pink';
      // lis[2].style.background = '#58bc58';
      // lis[3].style.background = 'pink';
      // lis[4].style.background = '#58bc58';
      
      /*
          循环结构：
              * while
                  * 三个值缺一不可:初始值、判断值、自增值，合理的使用三个值，就可以构成循环，但是要避免死循环
                  * 执行路线：
                      1.初始值
                      2.判断while的表达式是否符合条件，如果符合条件就跳到第3步;如果不符合条件跳到第4步
                      3.执行花括号里面的语句块，自增,返回第2步
                      4.循环后面的语句块
              * do while
              * for
      */
  
      var i = 0;//初始值
      while(i < 8) {//i < 8 判断值
          document.write('<br>' + i);//0-7
          i++;//自增值
      }
      console.log('i' + i);//8
  
  
      //隔行变色
      var j = 0;//初始值
      while(j < lis.length) {//判断值
          if(j % 2 == 0) {
              lis[j].style.background = '#58bc58';
          }else {
              lis[j].style.background = 'pink';
          }  
          j++;//自增值
      }
  
      console.log(j);//?lis.length
  ```

###### 案例：和尚挑水

山上有一口缸可以装50升水，现在有15升水。老和尚叫小和尚下山挑水，每次可以挑5升。问：小和尚要挑几次水才可以把水缸挑满？通过编程解决这个问题。

```
/*
        山上有一口缸可以装50升水，现在有15升水。老和尚叫小和尚下山挑水，每次可以挑5升。问：小和尚要挑几次水才可以把水缸挑满？通过编程解决这个问题。

        需求：
            * 已经条件：缸：50 目前：15，每次：5
            * 求：多少次可以装满？
    */

    var water = 15;//目前15升水
    var num = 0;//记录次数
    while(water < 50) {//判断值
        num++;
        water += 5;//自增值
    }
    console.log('需要挑水' + num + '次');
```

##### 程序流程-循环-do while循环

------

do while循环特点：先执行后判断，所以至少会执行一次代码

```
/变量初始化
do {
    //不管条件是否成立，先执行一次这里的代码，再进行条件判断，如果条件依然成立，则再次执行这里的代码，依此类推
    //所以这里一般会伴随着条件的更新
} while(条件)
```



##### 作业

------

> 1.输入月份，显示当月的天数
>
> - 不考虑闰年
> - 利用case穿透简化代码
>
> 2.测试身材是否标准：
>
> - BMI指数（即身体质量指数，简称体质指数又称体重，英文为Body Mass Index，简称BMI），是用体重公斤数除以身高米数平方得出的数字，是目前国际上常用的衡量人体胖瘦程度以及是否健康的一个标准。主要用于统计用途，当我们需要比较及分析一个人的体重对于不同高度的人所带来的健康影响时，BMI值是一个中立而可靠的指标。 
>
> **成人的BMI数值：** 体质指数（BMI）= 体重（kg）÷身高^2（m） 如：70kg÷（1.75×1.75）=22.86 
>
> > 过轻：低于18.5
> >
> > 正常：18.5-24.99
> >
> > 过重：25-28
> >
> > 肥胖：28-32
> >
> > 非常肥胖, 高于32
>
> ![1569772141480](https://raw.githubusercontent.com/shirley3790/myblogs_imgs/master/1569772141480.png)
>
> 3.输入成绩，进行成绩判定(要求用if和switch两种写法)
>
> - 大于85 优秀
> - 大于等于75小于等于85 良好
> - 大于等于60小于75 及格
> - 小于60 不及格