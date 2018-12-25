1. javascript的typeof返回哪些数据类型.

答案：string,boolean,number,undefined,function,object

2. 例举3种强制类型转换和2种隐式类型转换?

答案：强制（parseInt,parseFloat,number）
隐式（==  ===）

3. split() join() 的区别

答案：前者是将字符串切割成数组的形式，后者是将数组转换成字符串

4. 数组方法pop() push() unshift() shift()
答案：push()尾部添加 pop()尾部删除
unshift()头部添加 shift()头部删除

5. IE和标准下有哪些兼容性的写法

答案：

var ev = ev || window.event

document.documentElement.clientWidth || document.body.clientWidth
Var target = ev.srcElement||ev.target

6. ajax请求的时候get 和post方式的区别

答案：

一个在url后面 ，一个放在虚拟载体里面
get有大小限制(只能提交少量参数)
安全问题
应用不同 ，请求数据和提交数据

7. call和apply的区别

答案：

Object.call(this,obj1,obj2,obj3)
Object.apply(this,arguments)

8. ajax请求时，如何解析json数据

答案：使用JSON.parse

9. 事件委托是什么

答案: 利用事件冒泡的原理，让自己的所触发的事件，让他的父元素代替执行！

10. 闭包是什么，有什么特性，对页面有什么影响

答案：闭包就是能够读取其他函数内部变量的函数,使得函数不被GC回收，如果过多使用闭包，容易导致内存泄露

11. 如何阻止事件冒泡

答案：ie:阻止冒泡ev.cancelBubble = true;非IE ev.stopPropagation();  

12. 如何阻止默认事件

答案：(1)return false；(2) ev.preventDefault();

13. 添加 删除 替换 插入到某个接点的方法

答案：

1）创建新节点
createElement()   //创建一个具体的元素
createTextNode()   //创建一个文本节点
 
2）添加、移除、替换、插入
appendChild()      //添加
removeChild()      //移除
replaceChild()      //替换
insertBefore()      //插入
 
3）查找
getElementsByTagName()    //通过标签名称
getElementsByName()     //通过元素的Name属性的值
getElementById()        //通过元素Id，唯一性

14. 解释jsonp的原理，以及为什么不是真正的ajax

答案：动态创建script标签，回调函数
Ajax是页面无刷新请求数据操作

15. document load 和document ready的区别

答案：document.onload 是在结构和样式,外部js以及图片加载完才执行js
document.ready是dom树创建完成就执行的方法，原生种没有这个方法，jquery中有 $().ready(function)

16. ”==”和“===”的不同

答案：前者会自动转换类型,再判断是否相等
后者不会自动类型转换，直接去比较

17. 函数声明与函数表达式的区别？

在Javscript中，解析器在向执行环境中加载数据时，对函数声明和函数表达式并非是一视同仁的，解析器会率先读取函数声明，并使其在执行任何代码之前可用（可以访问），至于函数表达式，则必须等到解析器执行到它所在的代码行，才会真正被解析执行。

18. 对作用域上下文和this的理解，看下列代码：

var User = {
 count: 1,
 getCount: function() {
  return this.count;
 }
};
console.log(User.getCount()); // what?
var func = User.getCount;
console.log(func()); // what?
问两处console输出什么？为什么？
答案:是1和undefined。
　　func是在window的上下文中被执行的，所以不会访问到count属性。
19. 看下面代码，给出输出结果。

for(var i = 1; i <= 3; i++){  //建议使用let 可正常输出i的值
  setTimeout(function(){
      console.log(i);   
  },0); 
};
答案：4 4 4。
原因：Javascript事件处理器在线程空闲之前不会运行。

20. 当一个DOM节点被点击时候，我们希望能够执行一个函数，应该怎么做?

box.onlick= function(){}

box.addEventListener("click",function(){},false);

 

<button onclick="xxx()"></button>

21. Javascript的事件流模型都有什么?

“事件冒泡”：事件开始由最具体的元素接受，然后逐级向上传播

“事件捕捉”：事件由最不具体的节点先接收，然后逐级向下，一直到最具体的

“DOM事件流”：三个阶段：事件捕捉，目标阶段，事件冒泡

22. 看下列代码,输出什么?解释原因。

var a = null;
alert(typeof a);
答案：object
解释：null是一个只有一个值的数据类型，这个值就是null。表示一个空指针对象，所以用typeof检测会返回”object”。
23. 判断字符串以字母开头，后面可以是数字，下划线，字母，长度为6-30

var reg=/^[a-zA-Z]\w{5,29}$/;

24. 回答以下代码，alert的值分别是多少？

<script>
     var a = 100;  
     function test(){  
    	alert(a);  
   	 a = 10;  //去掉了var 就变成定义了全局变量了
    	alert(a);  
}  
test();
alert(a);
</script>
正确答案是： 100， 10， 10
25. javaScript的2种变量范围有什么不同？

全局变量：当前页面内有效

局部变量：函数方法内有效

26. null和undefined的区别？

null是一个表示"无"的对象，转为数值时为0；undefined是一个表示"无"的原始值，转为数值时为NaN。

当声明的变量还未被初始化时，变量的默认值为undefined。 null用来表示尚未存在的对象

undefined表示"缺少值"，就是此处应该有一个值，但是还没有定义。典型用法是：

（1）变量被声明了，但没有赋值时，就等于undefined。

（2）调用函数时，应该提供的参数没有提供，该参数等于undefined。

（3）对象没有赋值的属性，该属性的值为undefined。

（4）函数没有返回值时，默认返回undefined。

null表示"没有对象"，即该处不应该有值。典型用法是：

（1） 作为函数的参数，表示该函数的参数不是对象。

（2） 作为对象原型链的终点。

27. new操作符具体干了什么呢?

1、创建一个空对象，并且 this 变量引用该对象，同时还继承了该函数的原型。

2、属性和方法被加入到 this 引用的对象中。

3、新创建的对象由 this 所引用，并且最后隐式的返回 this 。

28. js延迟加载的方式有哪些？

defer和async、动态创建DOM方式（创建script，插入到DOM中，加载完毕后callBack）、按需异步载入js

29. Flash、Ajax各自的优缺点，在使用中如何取舍？

Flash ajax对比

(1)Flash适合处理多媒体、矢量图形、访问机器；对CSS、处理文本上不足，不容易被搜索。

(2)ajax对CSS、文本支持很好，支持搜索；多媒体、矢量图形、机器访问不足。

    共同点：与服务器的无刷新传递消息、用户离线和在线状态、操作DOM

30. 写一个获取非行间样式的函数

function getStyle(obj,attr) {

 

if(obj.currentStyle) {

return obj.currentStyle[attr];

}else{

getComputedStyle(obi,false)[attr] 

}

}

31. 希望获取到页面中所有的checkbox怎么做？(不使用第三方框架)

var inputs = document.getElementsByTagName("input");//获取所有的input标签对象
var checkboxArray = [];//初始化空数组，用来存放checkbox对象。
for(var i=0;i<inputs.length;i++){
  var obj = inputs[i];
  if(obj.type=='checkbox'){
     checkboxArray.push(obj);
  }
}
32. 写一个function，清除字符串前后的空格。（兼容所有浏览器）

String.prototype.trim= function(){

return this.replace(/^\s+/,"").replace(/\s+$/,"");

}

33. javascript语言特性中，有很多方面和我们接触的其他编程语言不太一样,请举例

javascript语言实现继承机制的核心就是  1  (原型)，而不是Java语言那样的类式继承。Javascript解析引擎在读取一个Object的属性的值时，会沿着  2  (原型链)向上寻找，如果最终没有找到，则该属性值为  3  undefined；如果最终找到该属性的值，则返回结果。与这个过程不同的是，当javascript解析引擎执行“给一个Object的某个属性赋值”的时候，如果当前Object存在该属性，则改写该属性的值，如果当前的Object本身并不存在该属性，则赋值该属性的值。

34. Cookie在客户机上是如何存储的

Cookies就是服务器暂存放在你的电脑里的文本文件，好让服务器用来辨认你的计算机。当你在浏览网站的时候，Web服务器会先送一小小资料放在你的计算机上，Cookies 会帮你在网站上所打的文字或是一些选择都记录下来。当下次你再访问同一个网站，Web服务器会先看看有没有它上次留下的Cookies资料，有的话，就会依据Cookie里的内容来判断使用者，送出特定的网页内容给你。

35. 如何获取javascript三个数中的最大值和最小值？

Math.max(a,b,c);//最大值

Math.min(a,b,c)//最小值

36. javascript是面向对象的，怎么体现javascript的继承关系？
使用prototype原型来实现。

37. .form中的input可以设置为readonly和disable，请问2者有什么区别？
readonly不可编辑，但可以选择和复制；值可以传递到后台
disabled不能编辑，不能复制，不能选择；值不可以传递到后台

38. 列举javaScript的3种主要数据类型，2种复合数据类型和2种特殊数据类型。

主要数据类型：string, boolean, number

复合数据类型：function, object

特殊类型：undefined，null

39. 程序中捕获异常的方法？

try{
 
}catch(e){
 
}finally{
 
}
40. Ajax原理

(1)创建对象

var xhr = new XMLHttpRequest();

(2)打开请求

xhr.open('GET', 'example.txt', true);

(3)发送请求

xhr.send(); 发送请求到服务器

(4)接收响应

xhr.onreadystatechange =function(){}

(1)当readystate值从一个值变为另一个值时，都会触发readystatechange事件。

(2)当readystate==4时，表示已经接收到全部响应数据。

(3)当status ==200时，表示服务器成功返回页面和数据。

(4)如果(2)和(3)内容同时满足，则可以通过xhr.responseText，获得服务器返回的内容。

41. 解释什么是Json:

(1)JSON 是一种轻量级的数据交换格式。

(2)JSON 独立于语言和平台，JSON 解析器和 JSON 库支持许多不同的编程语言。

(3)JSON的语法表示三种类型值，简单值(字符串，数值，布尔值，null),数组，对象

42. js中的3种弹出式消息提醒（警告窗口，确认窗口，信息输入窗口）的命令式什么？
alert
confirm
prompt

43. 以下代码执行结果

var uname = 'jack'
function change() {
    alert(uname) // ?
    var uname = 'lily'
    alert(uname)  //?
}
change()
分别alert出 undefined，lily，（变量声明提前问题）
44. 浏览器的滚动距离：

可视区域距离页面顶部的距离

scrollTop=document.documentElement.scrollTop||document.body.scrollTop

45. 可视区的大小：

(1)innerXXX（不兼容ie）

window.innerHeight 可视区高度，包含滚动条宽度

window.innerWidth  可视区宽度，包含滚动条宽度

(2)document.documentElement.clientXXX(兼容ie)

document.documentElement.clientWidth可视区宽度，不包含滚动条宽度

document.documentElement.clientHeight可视区高度，不包含滚动条宽度

46. 节点的种类有几种，分别是什么？

(1)元素节点：nodeType ===1;

(2)文本节点：nodeType ===3;

(3)属性节点：nodeType ===2;

47. innerHTML和outerHTML的区别

innerHTML(元素内包含的内容）

outerHTML(自己以及元素内的内容）

48. offsetWidth offsetHeight和clientWidth clientHeight的区别

(1)offsetWidth （content宽度+padding宽度+border宽度）

(2)offsetHeight（content高度+padding高度+border高度）

(3)clientWidth（content宽度+padding宽度）

(4)clientHeight（content高度+padding高度）

49. 闭包的好处

(1)希望一个变量长期驻扎在内存当中(不被垃圾回收机制回收)

(2)避免全局变量的污染

(3)私有成员的存在

(4)安全性提高

50. 冒泡排序算法

冒泡排序

var array = [5, 4, 3, 2, 1];
var temp = 0;
for (var i = 0; i <array.length; i++){
for (var j = 0; j <array.length - i; j++){
if (array[j] > array[j + 1]){
temp = array[j + 1];
array[j + 1] = array[j];
array[j] = temp;
 }
}
}

--------------------- 
作者：曲小强 
来源：CSDN 
原文：https://blog.csdn.net/quhongqiang/article/details/80388401 
版权声明：本文为博主原创文章，转载请附上博文链接！
