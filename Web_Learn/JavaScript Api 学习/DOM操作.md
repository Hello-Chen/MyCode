# JavaScript Api 学习

[TOC]



##  1. getElementById 获取元素

```js
// 1. 因为我们文档页面从上往下加载，所以先得有标签 所以我们script写到标签的下面
// 2. get 获得 element 元素 by 通过 驼峰命名法
// 3. 参数 id是大小写敏感的字符串
// 4. 返回的是一个元素对象
	var timer = document.getElementById('time');
	console.log(timer);
	console.log(typeof timer);
// 5. console.dir 打印我们返回的元素对象 更好的查看里面的属性和方法
	console.dir(timer);
```

## 2. getElementById 获取可返回带有指定标签名的对象的集合

```js
<body>
    <ul>
        <li>1</li>
        <li>1</li>
        <li>1</li>
        <li>1</li>

    </ul>
    <ol id="ol">
        <li>2</li>
        <li>2</li>
        <li>2</li>
        <li>2</li>

    </ol>

    <script>
        // 1.返回的是 获取过来元素对象的集合 以伪数组的形式存储的
        var lis = document.getElementsByTagName('li');
        console.log(lis);
        console.log(lis[0]);
        // 2. 我们想要依次打印里面的元素对象我们可以采取遍历的方式
        for (var i = 0; i < lis.length; i++) {
            console.log(lis[i]);
        }
        // 3. 如果页面中只有一个li 返回的还是伪数组的形式
        // 4. 如果页面中没有这个元素 返回的是空的伪数组的形式
        // 5. element.getElementsByTagName('标签名'); 父元素必须是指定的单个元素
        // var ol = document.getElementsByTagName('ol'); // [ol]
        // console.log(ol[0].getElementsByTagName('li'));
        var ol = document.getElementById('ol');
        console.log(ol.getElementsByTagName('li'));
    </script>
</body>
```

## 3. getElementByClassName 根据类名获取元素

###　３.1 querySelector 返回指定选择器的第一个元素对象

### ３.2 querySelectorAll 返回指定选择器的的所有元素对象集合

```js
// 1. getElementsByClassName 根据类名获得某些元素集合
	var boxs = document.getElementsByClassName('box');
	console.log(boxs);
// 2. querySelector 返回指定选择器的第一个元素对象  切记 里面的选择器需要加符号 .box  #nav
	var firstBox = document.querySelector('.box');
	console.log(firstBox);
	var nav = document.querySelector('#nav');
	console.log(nav);
	var li = document.querySelector('li');
	console.log(li);
// 3. querySelectorAll()返回指定选择器的所有元素对象集合
    var allBox = document.querySelectorAll('.box');
    console.log(allBox);
    var lis = document.querySelectorAll('li');
    console.log(lis);
```

## 4. 获取\<body>和\<html>标签方法

```js
// 1.获取body 元素
	var bodyEle = document.body;
	console.log(bodyEle);
	console.dir(bodyEle);
// 2.获取html 元素
// var htmlEle = document.html;
	var htmlEle = document.documentElement;
	console.log(htmlEle);
```

## 5. 执行事件三要素

点击一个按钮，弹出对话框
 1. 事件是有三部分组成  ==事件源==  ==事件类型==  ==事件处理程序==   我们也称为事件三要素
    (1) 事件源 事件被触发的对象   谁  按钮

  `var btn = document.getElementById('btn');`

  (2) 事件类型  如何触发 什么事件 比如鼠标点击(onclick) 还是鼠标经过 还是键盘按下
  (3) 事件处理程序  通过一个函数赋值的方式 完成

  ```js
  btn.onclick = function() {
  alert('success!');
  }
  ```

[鼠标事件](https://www.w3cschool.cn/htmltags/ref-eventattributes.html)

## 6. innerText 和 innerHTML的区别

```js
// 1. innerText 不识别html标签 非标准  去除空格和换行
var div = document.querySelector('div');
// div.innerText = '<strong>今天是：</strong> 2019';
// 2. innerHTML 识别html标签 W3C标准 保留空格和换行的
div.innerHTML = '<strong>今天是：</strong> 2019';
// 这两个属性是可读写的  可以获取元素里面的内容
var p = document.querySelector('p');
console.log(p.innerText);
console.log(p.innerHTML);
```

