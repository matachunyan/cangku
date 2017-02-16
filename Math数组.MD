**Math任务**
**写一个函数，返回从min到max之间的随机整数，包括min不包括max**
```
function getRandInt(min,max) {
    return Math.floor(Math.random()*(max-min))+min
}
var str = getRandInt(3,5);
console.log(str);
```
**写一个函数，返回从min都max之间的随机整数，包括min包括max**
```
function getRandInt(min,max) {
    return Math.floor(Math.random()*(max-min+1))+min
}
var str = getRandInt(3,5);
console.log(str);
```
**写一个函数，生成一个长度为 n 的随机字符串，字符串字符的取值范围包括0到9，a到 z，A到Z**
```
function  getRandArr(len) {
    var dict ="0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    var ch,str = "";
    
    for (var i=0;i<len;i++){
       var  idx = Math.floor(Math.random()*62);
        ch = dict[idx]
        str+=ch;
    }
    return str;
}
var str1 = getRandArr(5);
console.log(str1);
```
**写一个函数，生成一个随机 IP 地址，一个合法的 IP 地址为 0.0.0.0~255.255.255.255**
```
function getRandIP(){
        var arr =[];
    for(var i=0;i<4;i++){
        var dict = Math.floor(Math.random()*256);
        arr.push(dict);

    }
     return  arr.join(".")

}
var ip = getRandIP()
console.log(ip) 
```
**写一个函数，生成一个随机颜色字符串，合法的颜色为#000000~ #ffffff**
```
function getRandColor(){
        var arr =[];
        var  strColor="0123456789abcdef";
    for(var i=0;i<6;i++){
        var dict = Math.floor(Math.random()*17);
        arr[i]=strColor[dict];
       

    }
     return  '#'+arr.join("")

}
var color = getRandColor()
console.log(color) 
```
**数组任务**
**数组方法里push、pop、shift、unshift、join、split分别是什么作用？用 splice函数分别实现push、pop、shift、unshift方法**
```
var arr =[1,2,3];
arr.push(4)//可向数组的末尾添加一个或多个元素,并返回新的长度
arr.splice(arr.length,0,5);
console.log(arr);//[1,2,3,4,5]

arr.pop();//删除数组的末尾最后一个元素,并返回新的长度
arr.splice(arr.length-1,1);
console.log(arr);//[1,2,3]

arr.shift();//删除数值首项
arr.splice(0,1);
console.log(arr)//[3]

arr.unshift(2);//数组的开头添加一个或更多元素
arr.splice(0,0,1);
console.log(arr)//[1,2,3]

var str=arr.join("");//把数组中的元素放入一个字符串中
console.log(str)//123

var arr2=str.split("");//把字符串拆分成一个数组
console.log(arr2)//["1", "2", "3"]

```
**写一个函数，操作数组，数组中的每一项变为原来的平方，在原数组上操作**
```
function squareArr(arr){
    for(var i = 0; i < arr.length; i++){
        arr[i] = arr[i] * arr[i];
    }
    return arr;
}
var arr = [3, 5, 7]
squareArr(arr)
console.log(arr) // [9, 25, 49]
```
**写一个函数，操作数组，返回一个新数组，新数组中只包含正数，原数组不变**
```
function getTrue(arr) {
        var arr2=[];
    for (var i=0;i<arr.length;i++) {
        if (typeof arr[i] ==="number"&&arr[i] > 0) {
            arr2.push(arr[i])
        }
    }
    return arr2

}
var ar=[-11,1,2,-3,"think"];
var ar3=getTrue(ar);
console.log(ar3);
```
**Date 任务**
**写一个函数getChIntv，获取从当前时间到指定日期的间隔时间**
```
function getChIntv(s) {
        var time = Math.abs(Date.parse(s) - Date.now());
        var day = parseInt(time/(1000*60*60*24));
        var hours = parseInt((time %(1000*60*60*24))/(1000*60*60));
        var minutes = parseInt(((time%(1000*60*60*24))%(1000*60*60))/(1000*60));
        var seconds = parseInt(((time%(1000*60*60*24))%(1000*60*60))%(1000*60)/1000);
        return day + "天" + hours + "小时" + minutes + "分钟" + seconds+ "秒"
    }
    var str = getChIntv("2018-01-27");
    console.log(str);  // 344天9小时15分钟40秒
```
**把hh-mm-dd格式数字日期改成中文日期**
```
    function getChsDate(s) {
        var arr = ["零","一","二","三","四","五","六","七","八","九","十","十一","十二","十三","十四","十五","十六","十七","十八","十九","二十","二十一","二十二","二十三","二十四","二十五","二十六","二十七","二十八","二十九","三十","三十一"]
        var time = s.split('-');
        var year = time[0].split('');
        var month = time[1];
        var day = time[2];
        var newYear = arr[year[0]]+arr[year[1]]+arr[year[2]]+arr[year[3]];
        var newMonth = arr[parseInt(month)];
        var newDay = arr[parseInt(day)];
        return newYear+"年"+newMonth+"月"+newDay+"日";
    }
    var str = getChsDate('2015-01-08');
    console.log(str);  // 二零一五年一月八日
```
**写一个函数，参数为时间对象毫秒数的字符串格式，返回值为字符串。假设参数为时间对象毫秒数t，根据t的时间分别返回如下字符串**
```
function friendlyDate(time){
    var nowTime = Date.now();
    var intTime = ( nowTime - time ) / 1000;
    var result;
    if(intTime < 60){
        return result = '刚刚';
    }else if(intTime < 60*60){
        return result = parseInt(intTime / 60) +'分钟前';
    }else if(intTime < 60*60*24){
        return result = parseInt(intTime / (60*60)) +'小时前';
    }else if(intTime < 60*60*24*30){
        return result = parseInt(intTime / (60*60*24)) +'天前';
    }else if(intTime < 60*60*24*30*12){
        return result = parseInt(intTime / (60*60*24*30)) +'个月前';
    }                       
    return result = parseInt(intTime / (60*60*24*30*12)) +'年前';
}
var str = friendlyDate( '1484286699422' ) //  1分钟前
var str2 = friendlyDate('1483941245793') //4天前
```
