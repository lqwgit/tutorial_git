README.md的后缀md，是一种文件格式markdown的缩写。
纯文本的Markdown文件可以转换被成html标签，然后显示在网页上。

参考文献：http://wowubuntu.com/markdown/

# 概述
## 宗旨
Markdown 的目标是实现「易读易写」，最大灵感来源其实是纯文本电子邮件的格式。

## 兼容 HTML
Markdown 语法的目标是：成为一种适用于网络的书写语言。Markdown专注于内容而非样式，样式方面不如HTML，比如使用\<img>标签，还可以指定图片的宽和高，而使用Markdown的话就不能指定宽和高。但是一些常用的功能都是有的，而且用起来很方便。

不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。不需要额外标注这是 HTML 或是 Markdown；只要直接加标签就可以了。
比如，你输入：
>这是一段文本，  
回车不能换行，\<br>  
要使用\\\<br>

你会得到  
>这是一段文本，
回车不能换行，<br>
要使用\<br>

要制约的只有一些 HTML 区块元素――比如 &lt;div>、&lt;table>、&lt;pre>、&lt;p> 等标签。必须在前后加上空行与其它内容区隔开，还要求它们的开始标签与结尾标签不能用制表符或空格来缩进。

例子如下，在 Markdown 文件里加上一段 HTML 表格,要这样写：
> 这是一个普通段落。  
> &lt;table>  
&nbsp;&nbsp;&nbsp;&nbsp;&lt;tr>  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;td>Foo&lt;/td>  
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/tr>  
&lt;/table>  
> 这是另一个普通段落。

HTML 的区段（行内）标签如 \<span>、\<cite>、\<del> 可以在 Markdown 的段落、列表或是标题里随意使用。依照个人习惯，甚至可以不用 Markdown 格式，而直接采用 HTML 标签来格式化。举例说明：如果比较喜欢 HTML 的 <a> 或 <img> 标签，可以直接使用这些标签，而不用 Markdown 提供的链接或是图像标签语法。

## 特殊字符自动转换
在 HTML 文件中，有两个字符需要特殊处理： < 和 & 。 < 符号用于起始标签，& 符号则用于标记 HTML 实体，如果你只是想要显示这些字符的原型，你必须要使用实体的形式，像是 \&lt; 和 \&amp;。

& 字符尤其让网络文档编写者受折磨，如果你要打「AT&T」 ，你必须要写成「AT\&amp;T」。

如果你使用的 & 字符是 HTML 字符实体的一部分，它会保留原状，否则它会被转换成 \&amp;。
比如，你写：  
> 4 < 5

Markdown 将会把它转换为：  
> 4 \&lt; 5

而你写：  
> 4 \&lt; 5

Markdown 不会处理它

# 区块元素
## 段落和换行
如果你在markdown文件里连续敲两个换行，那么就会形成段落间距。如果只敲一个换行，那就等于连续的文本，这点和html一样。

如果你想换行，请使用两个空格加一个换行，或者加上一个\<br>标签。

如果你想在段落的开头打出空格，请使用多个\&nbsp;来实现。

## 标题
Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。

类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题），例如：  
>This is an H1  
\=============  
This is an H2  
\-------------

任何数量的 = 和 - 都可以有效果。

类 Atx 形式则是在行首插入 1 到 6 个 #并紧跟一个空格 ，对应到标题 1 到 6 阶。如果不打空格，那么就会把#显示出来，没有标题的样式。例如：  
>\# 这是 H1  
\## 这是 H2  
\###### 这是 H6

你可以选择性地「闭合」类 atx 样式的标题，这纯粹只是美观用的，若是觉得这样看起来比较舒适，你就可以在行尾加上 #，而行尾的 # 数量也不用和开头一样（行首的井字符数量决定标题的阶数）：  
>\# 这是 H1 #    
\## 这是 H2 ##    
\### 这是 H3 ######  

## 区块引用 Blockquotes

Markdown 标记区块引用是使用类似 email 中用 > 的引用方式。例如：  
> &gt;This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,  
&gt;consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.  
&gt;Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.  
&gt;  
&gt;Donec sit amet nisl. Aliqua

会显示为
>This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
>consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
>Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>
>Donec sit amet nisl. Aliqua

Markdown 也允许你偷懒只在整个段落的第一行最前面加上 >，例如 ：

> &gt;This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,  
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.  
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
>  
> &gt;Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.

区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 > ：  
> &gt;This is the first level of quoting.  
&gt;  
&gt;&gt; This is nested blockquote.  
&gt;  
&gt;Back to the first level.

会显示为。 
>This is the first level of quoting.
>  
>>This is nested blockquote.  
>  
> Back to the first level. 

引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：  
> &gt;\## 这是一个标题。  
&gt;  
&gt;1\.   这是第一行列表项。  
&gt;2\.   这是第二行列表项。  
&gt;  
&gt;给出一些例子代码：  
&gt;  
&gt;      return shell_exec("echo $input | $markdown_script");

会显示为
> ## 这是一个标题。
> 
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
> 
> 给出一些例子代码：
> 
>     return shell_exec("echo $input | $markdown_script");

# 列表
Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记：

*   Red
*   Green
*   Blue
等同于：

+   Red
+   Green
+   Blue
也等同于：

-   Red
-   Green
-   Blue
有序列表则使用数字接着一个英文句点：

1.  Bird
2.  McHale
3.  Parish
很重要的一点是，你在列表标记上使用的数字并不会影响输出的 HTML 结果，上面的列表所产生的 HTML 标记为：

<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>
如果你的列表标记写成：

1.  Bird
1.  McHale
1.  Parish
或甚至是：

3. Bird
1. McHale
8. Parish
你都会得到完全相同的 HTML 输出。重点在于，你可以让 Markdown 文件的列表数字和输出的结果相同，或是你懒一点，你可以完全不用在意数字的正确性。

如果你使用懒惰的写法，建议第一个项目最好还是从 1. 开始，因为 Markdown 未来可能会支持有序列表的 start 属性。

如果列表项目间用空行分开，在输出 HTML 时 Markdown 就会将项目内容用 <p> 标签包起来，举例来说：

*   Bird
*   Magic
会被转换为：

<ul>
<li>Bird</li>
<li>Magic</li>
</ul>
但是这个：

*   Bird

*   Magic
会被转换为：

<ul>
<li><p>Bird</p></li>
<li><p>Magic</p></li>
</ul>

当然，项目列表很可能会不小心产生，像是下面这样的写法：

1986. What a great season.
换句话说，也就是在行首出现数字-句点-空白，要避免这样的状况，你可以在句点前面加上反斜杠。

1986\. What a great season.

##代码区块

和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用 <pre> 和 <code> 标签来把代码区块包起来。

要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如，下面的输入：

##反斜杠
Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：
>\   反斜线
>`   反引号
>*   星号
>_   底线
>{}  花括号
>[]  方括号
>()  括弧
>#   井字号
>+   加号
>-   减号
>.   英文句点
>!   惊叹号
