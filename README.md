学无止境
==
2018.11.19
---
* ECMAScript 2017 有两个新的字符串方法：<br>
JavaScript 代码:<br>
```
'x'.padStart(5, 'ab') //'ababx'
```
```
'x'.padEnd(5, 'ab') //'xabab'
```
>数字位数不够，进行前补零的JS最简实现方案
>```
>function PrefixZero(num, n) {
>    return (Array(n).join(0) + num).slice(-n);
>}
>```
>       Array(5) => 创建了一个长度为5的空数组
>       console.log(Array(5));// [empty × 5]
>       Array(5).join(0) => 用0拼接将数组转换成字符串
>       console.log(Array(5).join(0));// 0000
>       Array(5).join(0)+91 => 通过+,实现字符串的拼接
>       console.log(Array(5).join(0)+91);// 000091
>       (Array(5).join(0) + 91).slice(-5) => slice(startIndex,endIndex)方法，用于截取
>       参数说明：
>       参数是起始位置，含头不含尾，
>       只有一个参数时，表示从该起始位置一直截取到最后。
>       参数值为负数时，表示从后往前数，如最后一位，索引是-1

* 面向对象<br>
`变量声明提升`<br>
变量搜索机制：先搜索局部变量，如果没找到，搜索全部变量。<br>
```
var v = "hello";
function test() {
  console.log(v); // undefined
  var v = "world";
}
```
>1.function作用域里的变量v遮盖了上层作用域变量v；<br>
>2.在function作用域内，变量v的声明被提升了。相当于：<br>
```
var v = "hello";
function test() {
  var v; //声明一个变量，声明提升，但是不会被赋值
  console.log(v);
  v = "world";
}
```

`短路表达式`<br>
true：1，function，object，字符串除了空字符串外都是true<br>
false：0，null，undefined<br>

`函数`<br>
函数--工具--封装性<br>
对象--工具包--把相类似的功能（工具），放在一起管理<br>
document-->getElementById(),getElementsByName(),...<br>
>工具包包含函数和属性。<br>
>>函数<br>
>>属性<br>
document-->title,bgColor,fgColor,...<br>
```
//对象内如何使用对象的属性和方法：this，对象外如何使用：先实例化，就用点语法
//抽象对象--类
function Product() {
  this.title = "";
  this.price = "";
  this.image = [];
  this.description = ""
}
//function Product(title,name) {
//  this.title = title;
//  this.price = name;
//  this.image = [];
//  this.description = ""
//}
//定义对象的两种方式
Product.prototype = {
  /*购买*/
  buy:function(){},
  /*获取详细信息*/
  getDetail:function(){},
  /*对代码进行分类管理*/
  bindDOM:function(){},
  bindEvents:function(){}
}
//Product.prototype.buy = function(){}
window.onload = function() {
  //对象实例化
  var iphone32 = new Product();
  iphone32.title = "apple 玫瑰金色";
  iphone32.price = 4988;
}

```
传统开发四要素：<br>
定义变量 保存数据 获取元素 绑定元素 绑定事件<br>

字符串，数组，日期，正则，Math => 都是对象<br>
```
timer(){
  var self = this;
  if(self.time > 0){
    self.time--;
    var timer = setTimeout(self.timer, 1000);
  }else if(self.time == 0){
    clearTimeout(timer);
  }
}
```
jQuery 学习：<br>
（js）<br>
入口函数：等待页面加载完成后才会执行。（script代码写在head里面，可以写在任意地方）<br>
        如果写两个，那么注册事件就会被覆盖，可以用addEventListener，但是存在兼容问题。<br>
        （可以省略）<br>
        ```window.onload = function(){};```
(jQuery)<br>
写法一：```$(document).ready(function(){});```
写法二：```$(function(){});```
js的入口函数执行的要比jQuery的晚一些<br>
jQuery的入口函数要等文档加载完才执行，但是不会等图片加载完成<br>
js的入口函数要等文档加载完，且图片加载完才执行<br?
使用jquer的步骤：引入jQuery文件，入口函数，功能实现 
