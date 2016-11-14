# web-code-standard

## HTML代码规范<br/>

### 一、标签嵌套规则
1、img 是内联标签；<br/><br/>
2、块级元素可以包含内联元素或某些块级元素，内联元素只能包含内联元素，不能包含块级元素；<br/><br/>
3、h1、h2、h3、h4、h5、h6、p、dt 这些块级标签只能包含内嵌元素，不能再包含块级元素；<br/><br/>
4、a 标签里不可以嵌套交互式元素(\<a>、\<button>、\<select>等)；<br/><br/>
5、列表元素 \<li>、\<dt>、\<dd> 等不可以插入非列表兄弟元素；<br/>

### 二、HTML5新语义标签使用
1、针对IE6，IE7，IE8 不支持 HTML5 新标签，需要在页面head中添加如下代码：<br/>
``` html
<!--[if lt IE 9]>
<script type="text/javascript" src="http://apps.bdimg.com/libs/html5shiv/3.7/html5shiv.min.js"></script>
<![endif]-->
```
<br/>
2、载入html5shiv.js文件后，初始化标签：<br/>
``` css
header,nav,section,article,aside,footer,dialog,figure,menu{display:block;}
```
<br/>

### 三、代码缩进
通常约定使用四个空格进行代码缩进，如果用 tab 来缩进，则可以设置 tab 的长度为四个空格的大小。
