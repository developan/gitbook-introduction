# Markdown语法 {#markdown语法}

Markdown是GitBook的默认解析器，本文档基本上都是Markdown语法编写的。当然，你也可以选择[AsciiDoc语法](http://gitbook.hushuang.me/syntax/asciidoc.html)来编写文档。

下面是Markdown语法的概述。

### 标题 {#headings}

在文本之前添加一到六个`＃`符号就可以创建一个标题。您使用的＃号将决定标题的大小。

# 这是1个\#号的标题 {#这是1个号的标题}

## 这是2个\#号的标题 {#这是2个号的标题}

### 这是3个\#号的标题 {#这是3个号的标题}

#### 这是4个\#号的标题 {#这是4个号的标题}

##### 这是5个\#号的标题 {#这是5个号的标题}

###### 这是6个\#号的标题 {#这是6个号的标题}

```
# 这是1个#号的标题
## 这是2个#号的标题
### 这是3个#号的标题
#### 这是4个#号的标题
##### 这是5个#号的标题
###### 这是6个#号的标题
```

GitBook支持一种显式方式设置头部ID。大括号中使用`#`号来设置ID值\(大括号前必须有一个空格\)，例如：

```
Hello {#id}
-----
# Hello {#id}
# Hello # {#id}
```

### 段落和换行符 {#paragraphs}

段落是一个或多个连续的文本行，由一个或多个空白行分隔。

```
这里是我们开始的一条线。

此行与上面的一行通过两个换行符分隔，因此它将是一个 
*单独的段落*
。

```

### 强调 {#emphasis}

_此文本将为斜体这也将是italic_

**此文本将是粗体这也将是bold**

~~这个文字会被划掉~~

_You**可以**组合them_

```
*此文本将为斜体*
_这也将是italic_
**此文本将是粗体**
__这也将是bold__


~~这个文字会被划掉~~


_You **可以**组合them_
```

### 列表 {#lists}

Markdown支持有序\(编号\)和无序\(项目符号\)列表。

##### 无序 {#无序}

无序列表使用星号，加号和连字符\(可互换\)作为列表标记：

* 项目1
* 项目2
  * 项目2 a
  * 项目2 b

```
* 
项目1

* 
项目2
  * 项目2a
  * 项目2b

```

##### 有序 {#有序}

有序列表使用数字后跟句点：

1. Item 1
2. Item 2
3. Item 3
   * Item 3a
   * Item 3b

```
1. 
Item 1

2. 
Item 2

3. 
Item 3
   * Item 3a
   * Item 3b

```

### 链接 {#links}

Markdown支持两种类型的链接：内联和引用。

使用方括号包围文本并使用括号括住链接网址来创建简单的链接：

这是[带标题的链接（鼠标停留后显示标题）](http://www.gibook.site/)与标题的内联链接。

[链接](http://www.gibook.site/)没有标题属性。

```
这是[
带标题的链接（鼠标停留后显示标题）
](
http://www.gibook.site/ "标题"
)与标题的内联链接。

[
链接
](
http://www.gibook.site/
)没有标题属性。

```

链接可以指向相对路径、页面定位或绝对网址。

##### 其他方式 {#其他方式}

还有另一种方式来创建链接。 标题使用引用名称定义，然后在方括号中使用此引用名称，而不是链接URL：

这是[一个示例](http://www.gibook.site/)参考样式链接。

```
这是[
一个示例
][
id
]参考样式链接。

```

然后，在文档中的任何位置（一般放在文件结尾），定义您的链接标签：

```
[
id
]:http://www.gibook.site/ "可选标题这里"
```

这样，所有用`[链接标题][id]`的链接都会引用`[id]:http://www.gibook.site/ "可选标题这里"`这个地址，一般我们将。

### 图片 {#images}

图像与链接创建的方式很类似：只需在方括号前使用感叹号即可：

图片:![](http://gitbook.hushuang.me/images/logo_200.png "这是图片")

```
图片:![
这是图片
](
../images/logo_200.png
)

```

### 引用块 {#blockquotes}

使用`>`标记符后跟一个空格开始：

Kanye West说：

> 我们生活在未来 现在是我们的过去。

```
Kanye West说：


>
 我们生活在未来
>
 现在是我们的过去。
```

### 表格 {#tables}

用连字符`-`\(第一行\)分隔，然后用管道符`|`分隔每个列来创建表格：

| 第一标题 | 第二标题 |
| :--- | :--- |
| 内容单元 | 内容单元 |
| 内容单元 | 内容单元 |

```
|第一标题|第二标题|
| ----- | ----- |
|内容单元|内容单元|
|内容单元|内容单元|

```

标题行的每一列中至少必须有三个连字符。

### 代码 {#code}

Markdown支持两种不同的代码块样式。 第一种方式是缩进四个空格或一个`tab`的行，而另一个种带小写波浪字符作为分隔符的行：

    ```markdown
    这是一个示例代码块。

        继续这里。

    ```


##### 受防护的代码块 {#受防护的代码块}

您可以通过在代码块之前和之后放置三个反引号```````````来创建围起来的代码块。 我们建议在代码块之前和之后放置空行，以使原始格式化更容易阅读。

```
function
test
(
)
{
      
console
.log(
"注意这个函数之前的空行？"
)
}

```

        ```javascript
        function test(){
              console.log("注意这个函数之前的空行？")
        }
        ```


##### 语法高亮 {#语法高亮}

您可以添加可选的语言标识符，以在受保护的代码块中启用语法突出显示。

例如，以语法高亮Ruby代码：

```
require
'redcarpet'

markdown = Redcarpet.new(
"Hello World!"
)
puts markdown.to_html

```

    ```ruby
    require 'redcarpet'
    markdown = Redcarpet.new("Hello World!")
    puts markdown.to_html
    ```


##### 内联代码 {#内联代码}

文本短语可以通过用反引号包围它们来标记为代码, 下面的`gitbook`和`text`就是个例子：

     使用`gitbook`在markdown中转换`text`
     语法到HTML。


### 脚注 {#footnotes}

GitBook支持简单的脚注语法。 脚注是对当前整个页面有效。

脚注参考前的文本。[a2](http://gitbook.hushuang.me/syntax/markdown.html#fn_a2)

```
脚注参考前的文本。[^2]

[
^2
]:评论要包括在脚注中。
```

### HTML {#html}

GitBook支持在您的文本中使用原始HTML，不处理HTML中的Markdown语法：

Markdown这里不会\*\*解析\*\*

```
<
div
>

Markdown这里不会**解析**

<
/div
>
```

### 分隔线 {#dividingLine}

使用三个或多个星号、中划线、下划线创建分隔线：

---

---

---

```
三个或更多...

--- ---

中划线


***


星号


___


下划线

```

### 忽略Markdown格式 {#忽略markdown格式}

如果需要忽略Markdown格式，也就是转义Markdown的关键字，只需要在Markdown关键字前使用反斜杠`\`即可。

```
Let's rename \*our-new-project\* to \*our-old-project\*.
```



