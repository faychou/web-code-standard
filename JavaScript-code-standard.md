# web-code-standard
## JavaScript代码规范

### 一、JS代码书写规范
1、空格<br/>
    左花括号之前一个空格；<br/>
    操作符前后；<br/>
    匿名函数表达式之后。<br/>
<br/>
2、空行<br/>
通常一段代码的语义和另一段代码不相关，就应该用空行隔开，避免一大段的代码团在一起，比如：<br/>
    在方法之间；<br/>
    方法中的局部变量和第一条语句之间；<br/>
    注释之前;<br/>
    方法内的逻辑片段之间。
### 二、命名约定
通常情况下，变量与函数一般使用驼峰大小写命名法，其中变量命名前缀应当是名词，函数前缀应当是动词，避免使用没有意义的命名。

### 三、注释
针对每一个方法，某一个功能，编写好注释。

### 四、变量
1、减少全局变量，因为有可能造成：命名冲突、测试难度大、深耦合等等；<br/><br/>
2、变量必须申明，因为未经申明的变量也是全局变量；<br/><br/>
3、由于在javascript中，无论在函数哪里声明变量，都会被“提升”到函数顶部。所以统一把变量在函数顶部声明，既有利于可读性与可维护行，也不易出错；<br/><br/>
4、使用一个 var 来申明所有的变量，不仅可读性好，而且编码更少，如：<br/>
``` javascript
var a = 1,
    b = 1,
    c = 1;
```

### 五、UI松耦合
1、避免使用css表达式；<br/><br/>
2、避免直接使用javascript修改css样式，最佳的方法是操作className;<br/><br/>
3、尽量做到将所有的js代码都放入外置文件中，确保
html中不会有内联的js代码；<br/><br/>
4、避免在js中拼接html结构。<br/>

### 六、错误处理
主要是辨识代码中哪些部分在特定的情况下最后可能导致错误,可以帮助我们快速定位错误。<br/><br/>
1、使用try-catch：<br/>
将可能引发错误的代码放在try块中，处理错误的代码放在catch中，如：<br/>
``` javascript
try {
    someMethod();
} catch (e) {
    catchError(e);
}
```
2 、throw<br/>
当我们能清晰的捕捉到错误的时候，最好的做法就是抛出这个错误。这里需注意的是当遇到throw操作符时，代码会立即停止执行。<br/>
``` javascript
throw new Error("method(): descdescdesc");
```

### 七、使用对象字面量创建对象
``` javascript
// 不推荐
var obj = new Object();
// 推荐
var obj = {};
```

### 八、使用字面量语法创建数组
``` javascript
// 不推荐
var items = new Array();
// 推荐
var items = [];
```

### 九、函数
1、使用函数声明而不是函数表达式<br/>
函数声明拥有函数名，更方便调用。
``` javascript
// 不推荐
var foo = function () {
};
// 推荐
function foo() {
}
```
2、绝对不要在一个非函数块（if，while 等）里声明一个函数，而是把这个函数赋给一个变量：<br/>
``` javascript
// 不推荐
if (currentUser) {
  function foo() {
    console.log('a');
  }
}
// 推荐
var foo;
if (currentUser) {
  foo = function foo() {
    console.log('b');
  };
}
```
