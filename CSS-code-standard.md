# web-code-standard
## CSS代码规范
### 一、选择器命名
1、面向功能的命名：

`class` 名字单词必须全字母小写，单词间以 `-` 分隔。

`class` 名字必须代表相应模块或部件的内容或功能，不得以样式信息进行命名。所有的css样式统一使用`class`选择器，尽量避免使用`ID`选择器；

不允许`class`只用于让`JavaScript`选择某些元素，`class`应该具有明确的语义和样式。否则容易导致 CSS`class`泛滥。

同一页面，应避免使用相同的`name`与`id`。IE 浏览器会混淆元素的`id`和`name`属性，`document.getElementById`可能获得不期望的元素。所以在对元素的`id`与`name`属性的命名需要非常小心。

2、常用的css命名建议：

    头部：header
    页面外围控制整体布局宽度：wrapper
    内容：content/container
    页面主体：main
    页脚：footer
    导航：nav
    子导航：subnav
    侧栏：sidebar
    栏目：column
    菜单：menu
    子菜单：submenu
    左右中：left right center
    注册：register
    登陆：login
    登录条：loginbar
    标志：logo
    图标: icon
    广告：banner
    热点：hot
    新闻：news
    下载：download
    搜索：search
    按钮：btn
    滚动：scroll
    内容：content
    标签页：tab
    文章列表：list
    提示信息：msg
    小技巧：tips
    栏目标题：title
    摘要: summary
    当前的: current
    加入：joinus
    指南：guide
    服务：service
    状态：status
    友情链接：friendlink(link)
    版权：copyright
    注释：note
    投票：vote
    合作伙伴：partner

### 二、避免使用 `!important`属性；
### 三、空格的使用
1、左括号与类名之间一个空格；

2、`属性名` 与之后的 `:` 之间不允许包含空格， `:` 与 `属性值` 之间必须包含空格。

3、 `>`、`+`、`~` 选择器的两边各保留一个空格。

### 四、多选择器规则之间（必须）换行
当一个 rule 包含多个 selector 时，每个选择器声明必须独占一行。

示例：

```css
/* good */
.post,
.page,
.comment {
    line-height: 1.5;
}

/* bad */
.post, .page, .comment {
    line-height: 1.5;
}
```

### 五、避免使用"`*`"来重置元素，而是用到哪些元素，重置哪些

### 六、属性书写顺序

 同一 rule set 下的属性在书写时，应按功能进行分组，并以 **Formatting Model（布局方式、位置） > Box Model（尺寸） > Typographic（文本相关） > Visual（视觉效果）** 的顺序书写，以提高代码的可读性。

解释：

- Formatting Model 相关属性包括：`position` / `top` / `right` / `bottom` / `left` / `float` / `display` / `overflow` 等
- Box Model 相关属性包括：`border` / `margin` / `padding` / `width` / `height` 等
- Typographic 相关属性包括：`font` / `line-height` / `text-align` / `word-wrap` 等
- Visual 相关属性包括：`background` / `color` / `transition` / `list-style` 等

另外，如果包含 `content` 属性，应放在最前面。


示例：

```css
.sidebar {
    /* formatting model: positioning schemes / offsets / z-indexes / display / ...  */
    position: absolute;
    top: 50px;
    left: 0;
    overflow-x: hidden;

    /* box model: sizes / margins / paddings / borders / ...  */
    width: 200px;
    padding: 5px;
    border: 1px solid #ddd;

    /* typographic: font / aligns / text styles / ... */
    font-size: 14px;
    line-height: 20px;

    /* visual: colors / shadows / gradients / ... */
    background: #f5f5f5;
    color: #333;
    -webkit-transition: color 1s;
       -moz-transition: color 1s;
            transition: color 1s;
}
```

### 七、格式
1、 当数值为 0 - 1 之间的小数时，省略整数部分的 0；长度为 0 时须省略单位。

2、 `url()` 函数中的路径不加引号；`url()` 函数中的绝对路径可省去协议名。

3、 `font-family` 属性中的字体族名称应使用字体的英文 `Family Name`，其中如有空格，须放置在引号中。

字体 | 操作系统 | Family Name
-----|----------|------------
宋体 (中易宋体) | Windows | SimSun
黑体 (中易黑体) | Windows | SimHei
微软雅黑 | Windows | Microsoft YaHei
微软正黑 | Windows | Microsoft JhengHei
华文黑体 | Mac/iOS | STHeiti
冬青黑体 | Mac/iOS | Hiragino Sans GB
文泉驿正黑 | Linux | WenQuanYi Zen Hei
文泉驿微米黑 | Linux | WenQuanYi Micro Hei
