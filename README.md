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
>Array(5) => 创建了一个长度为5的空数组
>console.log(Array(5));// [empty × 5]
>Array(5).join(0) => 用0拼接将数组转换成字符串
>       console.log(Array(5).join(0));// 0000
>       Array(5).join(0)+91 => 通过+,实现字符串的拼接
>       console.log(Array(5).join(0)+91);// 000091
>       (Array(5).join(0) + 91).slice(-5) => slice(startIndex,endIndex)方法，用于截取
>       参数说明：
>       参数是起始位置，含头不含尾，
>       只有一个参数时，表示从该起始位置一直截取到最后。
>       参数值为负数时，表示从后往前数，如最后一位，索引是-1
