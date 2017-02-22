**题目1： dom对象的innerText和innerHTML有什么区别？**
innerText返回元素内的的 **文本内容**。
innerHTML返回元素内的 **HTML结构**（包含HTML标签）。

**题目2： elem.children和elem.childNodes的区别？**
elem.children 返回的是elem的所有标签子节点；
elem.childNodes 返回所有的文档元素节点,包含看不到的空白字符

**题目3：查询元素有几种常见的方法？ES5的元素选择方法是什么?**
查询元素的常见方法：
>getElementsByTagName()    方法返回所有指定标签的元素
getElementsByName()         方法选择拥有name属性的HTML元素
getElementById()      方法返回匹配指定ID属性的元素节点
getElementsByClassName()      方法返回一个包括了所有class名字符合指定条件的元素（类数组对象）

ES5的元素选择方法：

>querySelector()方法返回匹配指定的CSS选择器的元素节点
querySelectorAll()方法返回匹配指定的CSS选择器的所有节点


**题目4：如何创建一个元素？如何给元素设置属性？如何删除属性**



* 创建元素: createElement();
* 可以用createTextNode()创建文本内容。
* 元素设置属性： setAttribute() ;
* 删除属性: romoveAttribute();

**题目5：如何给页面元素添加子元素？如何删除页面元素下的子元素?**

* 添加子元素

 * appendChild()：在元素末尾添加元素
 * insertBefore()：在某个元素之前插入元素

* 删除子元素

  * removeChild()：删除元素


**题目6： element.classList有哪些方法？如何判断一个元素的 class 列表中是包含某个 class？如何添加一个class？如何删除一个class?**

* add()在元素中添加一个或多个类名。
* contains(class)返回布尔值，判断指定的类名是否存在。
* item(index)返回类名在元素中的索引值。索引值从 0 开始。
* remove(class1, class2, ...)移除元素中一个或多个类名。
* toggle(class, true|false)在元素中切换类名。
* 利用contans方法来判断class是否存在.
* 利用remove()和add来添加删除class.


**题目7： 如何选中如下代码所有的li元素？ 如何选中btn元素？**
```
<div class="mod-tabs">
   <ul>
       <li>list1<li>
       <li>list2<li>
       <li>list3<li>
   </ul>
   <button class="btn">点我</btn>
</div>
<script>
    var oLi  = document.getElementsByTagName("li");
    var oLi1 = document.getElementsByClassName("btn");
    var oLi2 = document.querySelectorAll(".mod-tabs li");
    var oLi3 = document.querySelectorAll(".btn");
</script>
```
