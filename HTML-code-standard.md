# web-code-standard

## HTML代码规范<br/>

### 一、标签嵌套规则
1、img 是内联标签；

2、块级元素可以包含内联元素或某些块级元素，内联元素只能包含内联元素，不能包含块级元素；

3、h1、h2、h3、h4、h5、h6、p、dt 这些块级标签只能包含内嵌元素，不能再包含块级元素；

4、a 标签里不可以嵌套交互式元素(`<a>、\<button>、\<select> `等)；

5、列表元素 `<li>、<dt>、<dd> `等不可以插入非列表兄弟元素；

### 二、HTML5新语义标签使用
1、针对IE6，IE7，IE8 不支持 HTML5 新标签，需要在页面head中添加如下代码：
``` html
<!--[if lt IE 9]>
<script type="text/javascript" src="http://apps.bdimg.com/libs/html5shiv/3.7/html5shiv.min.js"></script>
<![endif]-->
```

2、载入html5shiv.js文件后，初始化标签：
``` css
header,nav,section,article,aside,footer,dialog,figure,menu{display:block;}
```

### 三、代码缩进
通常约定使用4个空格进行代码缩进，如果用 tab 来缩进，则可以设置 tab 的长度为四个空格的大小。

### 四、标签格式
1、 标签名必须使用小写字母。

2、 对于无需自闭合的标签，不允许自闭合。

示例：

```html
<!-- good -->
<input type="text" name="title">

<!-- bad -->
<input type="text" name="title" />
```
3、 属性名必须使用小写字母。

4、 属性值必须用双引号包围。

5、 自定义属性建议使用`data-`为前缀。

6、 使用 `HTML5` 的 `doctype` 来启用标准模式，建议使用大写的 `DOCTYPE`。

示例：

``` html
<!DOCTYPE html>
```

7、 启用 IE Edge 模式。

示例：

``` html
<meta http-equiv="X-UA-Compatible" content="IE=Edge">
```

8、 在 `html` 标签上设置正确的 `lang` 属性。

解释：

有助于提高页面的可访问性，如：让语音合成工具确定其所应该采用的发音，令翻译工具确定其翻译语言等。


示例：

``` html
<html lang="zh-cmn-Hans">
```

9、 页面必须使用精简形式，明确指定字符编码。指定字符编码的 `meta` 必须是 `head` 的第一个直接子元素。

```html
    <head>
        <meta charset="UTF-8">
        ......
    </head>
```

10、 引入 `CSS` 和 `JavaScript` 时无须指明 `type` 属性；同时`CSS` 必须指明 `rel="stylesheet"`；。

11、 在 `head` 中引入页面需要的所有 `CSS` 资源。`JavaScript` 应当放在页面末尾，或采用异步加载。

12、 页面必须包含 `title` 标签声明标题，并紧随 `charset` 声明之后。

13、 保证 `favicon` 可访问。

在未指定 favicon 时，大多数浏览器会请求 Web Server 根目录下的 `favicon.ico` 。为了保证 favicon 可访问，避免 404，必须遵循以下两种方法之一：

1. 在 Web Server 根目录放置 `favicon.ico` 文件。
2. 使用 `link` 指定 favicon。


```html
<link rel="shortcut icon" href="path/to/favicon.ico">
```

### 五、图片
1、 禁止 img 的 src 取值为空。延迟加载的图片也要增加默认的 src。

2、 避免为 img 添加不必要的 title 属性；为重要图片添加 alt 属性。

解释：

多余的 title 影响看图体验，并且增加了页面尺寸。

3、有下载需求的图片采用 img 标签实现，无下载需求的图片尽量采用 CSS 背景图实现。

### 六、表单
1、 有文本标题的控件必须使用 `label` 标签将其与其标题相关联。

有两种方式：

a. 将控件置于 `label` 内。  
b. `label` 的 `for` 属性指向控件的 `id`。

推荐使用第一种，减少不必要的 `id`。如果 DOM 结构不允许直接嵌套，则应使用第二种。
