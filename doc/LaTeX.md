# LaTeX 教程

## 概述

LaTeX（读作/ˈlɑːtɛx/或/ˈleɪtɛx/）是一个让你的文档看起来更专业的排版系统，而不是文字处理器。它尤其适合处理篇幅较长、结构严谨的文档，并且十分擅长处理公式表达。它是免费的软件，对大多数操作系统都适用。

LaTeX 基于 TeX（Donald Knuth 在 1978 年为数字化排版设计的排版系统）。TeX 是一种电脑能够处理的低级语言，但大多数人发现它很难使用。LaTeX 正是为了让它变得更加易用而设计的。

LaTeX 秉承这样的理念：最好将文档设计留给文档设计者，让作者继续撰写文档。

一个 LaTeX 文档是一个以 `.tex` 结尾的文本文件，可以使用任意的文本编辑器编辑，比如 Notepad，但对于大多数人而言，使用一个合适的 LaTeX 编辑器会使得编辑的过程容易很多。在编辑的过程中你可以标记文档的结构。完成后你可以进行编译——这意味着将它转化为另一种格式的文档。它支持多种格式，但最常用的是 PDF 文档格式。

入门教程：https://oi-wiki.org/tools/latex/

在线使用：overleaf.com

## 1.文档

`\documentclass` 命令必须出现在每个 LaTeX 文档的开头。花括号内的文本指定了文档的类型。**article** 文档类型适合较短的文章，比如期刊文章和短篇报告。其他文档类型包括 **report**（适用于更长的多章节的文档，比如博士生论文），**proc**（会议论文集），**book** 和 **beamer**。方括号内的文本指定了一些选项——示例中它设置纸张大小为 A4，主要文字大小为 12pt。

`\begin{document}` 和 `\end{document}` 命令将你的文本内容包裹起来。任何在 `\begin{documnet}` 之前的文本都被视为前导命令，会影响整个文档。

任何在 `\end{document}` 之后的文本都会被忽视。

空行不是必要的，但它可以让长的文档更易读。文本指定了一些选项——示例中它设置纸张大小为 A4，主要文字大小为 12pt。

```latex
\documentclass[a4paper, 12pt]{article}
\title{Cartesian closed categories and the price of eggs}
\author{Jane Doe}
\date{September 1994}
\begin{document}
   \maketitle
   Hello world!
\end{document}
```

以上代码意味着：

- 本文档是一篇文章。
- 它的标题是笛卡尔闭范畴和鸡蛋的价格。
- 它的作者是 Jane Doe。
- 它写于 1994 年 9 月。
- 该文档由一个标题和后面的文本“Hello world!”组成。

多个连续空格在 LaTeX 中被视为一个空格。多个连续空行被视为一个空行。空行的主要功能是开始一个新的段落。通常来说，LaTeX 忽略空行和其他空白字符，两个反斜杠（`\\`）可以被用来换行。

![\rightarrow](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7) 尝试在你的文档中添加注释和空行。

如果你想要在你的文档中添加空格，你可以使用 `\vaspace{...}` 的命令。这样可以添加竖着的空格，高度可以指定。如 `\vspace{12pt}` 会产生一个空格，高度等于 12pt 的文字的高度。

### 1.1.列举和表格

```latex
% 无序列表
\begin{itemize}
\item Item 1. 
\item Item 2.
\item \ldots 
\item Item n. 
\end{list}
% 有序列表
\begin{enumerate}
\item Item 1. 
\item Item 2.
\item \ldots 
\item Item n. 
\end{list}
```

### 1.2.符号和公式

如果是在同一行用 \$expression\$；如果是另一起一行用 \\[expression\\] 或者 \$\$expression\$\$。

### 1.3.插入图片

```latex
\usepackage{graphicx}
\begin{document}
\includegraphics[scale=0.5]{tmp.png}
\end{document}
```

如果不在同一文件夹需要说明位置，scale 是原图尺寸的百分比，也可以指定图的大小，把 [scale=0.5] 换成 [width= cm, height= cm] 空白处填入你想要的图片大小。 

如果你需要为图片增加标题，那么需要放在figure的环境中，参考下面的例子。

```latex
\documentclass{report}
\usepackage{graphicx}
\begin{figure}
\includegraphics[scale=.5]{tmp.png}
\caption{fig: tmp}
\end{figure}
\end{document}
```

## 2.排版

可参考：

> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/dreaming_coder/article/details/115723681)

### 2.1 字体和字号

--------

LaTeX \LaTeX LATEX 根据文档的逻辑结构（章节、脚注等）来选择默认的字体样式以及字号. 需要更改字体样式或字号的话，可以使用下表中列出的命令：

<img src="https://img-blog.csdnimg.cn/20210415142639768.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RyZWFtaW5nX2NvZGVy,size_16,color_FFFFFF,t_70#pic_center" style="zoom:50%;" />

<img src="https://img-blog.csdnimg.cn/20210415142650552.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RyZWFtaW5nX2NvZGVy,size_16,color_FFFFFF,t_70#pic_center" style="zoom:50%;" />

```
{\small The small and
\textbf{bold} Romans ruled}
{\Large all of great big
{\itshape Italy}.}

```

<img src="https://img-blog.csdnimg.cn/20210415142658862.png#pic_center" style="zoom:50%;" />

> 字体的各种属性相互独立（“正交”），用户可以改变字体的大小，而仍然保留字体原有的粗体或者斜体的特.

#### 2.1.1 字体样式

LaTeX \LaTeX LATEX 提供了两组修改字体的命令，如前表所示，其中诸如 `\bfseries` 形式的命令将会影响之后所有的字符，如果想要让它在局部生效，需要用花括号分组，也就是写成 `{\bfseries ⟨sometext⟩}` 这样的形式；对应的 `\textbf` 形式带一个参数，只改变参数内部的字体，更为常用.

#### 2.1.2 字号

字号命令实际大小依赖于所使用的文档类及其选项，下表列出了这些命令在标准文档类中的绝对大小，单位为 **pt**.

使用字号命令的时候，通常也需要用花括号进行分组，如同 `\rmfamily` 那样.

<img src="https://img-blog.csdnimg.cn/20210415142712482.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RyZWFtaW5nX2NvZGVy,size_16,color_FFFFFF,t_70#pic_center" style="zoom:50%;" />

```
He likes {\LARGE large and
{\small small} letters}.

```

<img src="https://img-blog.csdnimg.cn/20210415142721672.png#pic_center" style="zoom:50%;" />

LaTeX \LaTeX LATEX 还提供了一个基础的命令 `\fontsize` 用于设定任意大小的字号：

```
\fontsize{⟨size⟩}{⟨base line-skip⟩}

```

`\fontsize` 用到两个参数，`⟨size⟩` 为字号，`⟨base line-skip⟩` 为基础行距. 上表中的命令也都各自设定了与字号对应的基础行距，大小为字号的 1.2 1.2 1.2 倍. 如果不是在导言区，`\fontsize` 的设定需要 `\selectfont` 命令才能立即生效，而前表中的 6 6 6 个命令的字号设定都是立即生效的.

#### 2.1.3 选用字体宏包

许多字体宏包为我们完成了整套配置，我们可以在调用宏包之后，照常使用 `\bfseries` 或 `\ttfamily` 等我们熟悉的命令：

<img src="https://img-blog.csdnimg.cn/20210415142729806.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RyZWFtaW5nX2NvZGVy,size_16,color_FFFFFF,t_70#pic_center" style="zoom: 33%;" />

#### 2.1.4 字体编码

切换字体编码要用到 **fontenc** 宏包：

```
\usepackage[T1]{fontenc}
```

**fontenc** 宏包是用来配合传统的 LaTeX \LaTeX LATEX 字体的，如上表中的一些传统字体宏包. 如果使用 **xelatex** 编译方式，并使用 **fontenc** 宏包调用 `ttf` 或 `otf` 格式字体，就不要再使用 **fontenc** 宏包. 使用上表中的字体宏包之前最好查看一下宏包的帮助文档，了解使用方法和注意事项.

#### 2.1.5 使用 fontspec 宏包更改字体

**xelatex** 和 **lualatex** 编译命令能够支持直接调用系统和 TeX \TeX TEX 发行版中的 `.ttf` 或 `.otf` 格式字体. 相比于前文介绍的字体宏包，我们有了更多自由修改字体的余地.

**xelatex** 和 **lualatex** 命令下支持用户调用字体的宏包是 **fontenc**， 宏包提供了几个设置全局字体的命令，设置 `\rmfamily` 等对应命令的默认字体：

```
\setmainfont{⟨font name⟩}[⟨font features⟩]
\setsansfont{⟨font name⟩}[⟨font features⟩]
\setmonofont{⟨font name⟩}[⟨font features⟩]

```

其中 `⟨font name⟩` 使用字体的文件名（**带扩展名**）或者字体的英文名称. `⟨font features⟩` 用来手动配置对应的粗体或斜体，比如为 Windows 下的无衬线字体 **Arial** 配置粗体和斜体（通常情况下自动检测并设置对应的粗体和斜体，无需手动指定）：

```
\setsansfont[BoldFont={Arial Bold}, ItalicFont={Arial Italic}]{Arial}

```

`⟨font features⟩` 还能配置字体本身的各种特性，这里不再赘述，感兴趣的读者请参考 **fontenc** 宏包的帮助文档.

需要注意的是：**fontenc** 宏包会覆盖数学字体设置。需要调用表上表中列出的一些数学字体宏包时，应当在调用 **fontenc** 宏包时指定 `no-math` 选项. **fontenc** 宏包可能被其它宏包或文档类（如 **ctex** 文档类）自动调用时，则在文档开头的 `\documentclass` 命令里指定 `no-math` 选项.

#### 2.1.6 在 ctex 宏包或文档类中更改中文字体

**ctex** 宏包或文档类提供了和 `fontspec` 宏包非常类似的语法设置中文字体：

```
\setCJKmainfont{⟨font name⟩}[⟨font features⟩]  % 衬线字体
\setCJKsansfont{⟨font name⟩}[⟨font features⟩]  % 无衬线字体
\setCJKmonofont{⟨font name⟩}[⟨font features⟩]  % 等宽字体，一般是打印机字体

% 一般论文中设置字体
% 如果不是 ctex 文档类，要 \RequirePackage{xeCJK}
\setmainfont{Times New Roman}  % 设置默认英文字体 Times
\setCJKmainfont[AutoFakeBold=2,AutoFakeSlant=true]{SimSun}  % 设置默认中文字体 宋体

```

由于中文字体少有对应的粗体或斜体，`⟨font features⟩` 里多用其他字体来配置，比如在 Windows 中设定基本字体为宋体，并设定对应的 `BoldFont` 为黑体，`ItalicFont` 为楷体：

```
\setCJKmainfont{SimSun}[BoldFont=SimHei, ItalicFont=KaiTi]
```

### 2.2 文字装饰和强调

----------

强调文字的方法，或者是添加下划线等装饰物，或者是改变文字的字体.

LaTeX \LaTeX LATEX 定义了 `\underline` 命令用来为文字添加下划线：

```
An \underline{underlined} text.

```

<img src="https://img-blog.csdnimg.cn/20210415142754777.png#pic_center" style="zoom: 50%;" />

`\underline` 命令生成下划线的样式不够灵活，不同的单词可能生成高低各异的下划线，并且无法换行. **ulem** 宏包提供了更灵活的解决方案，它提供的 `\uline` 命令能够轻松生成自动换行的下划线：

```
An example of \uline{somelong and \\ 
underlined words.}

```

<img src="https://img-blog.csdnimg.cn/20210415142808927.png#pic_center" style="zoom:50%;" />

前一节介绍了 `\emph` 命令，它将文字变为斜体以示强调，而如果在已强调的文字中嵌套使用 `\emph` 命令，命令内则使用直立体文字：

```
Some \emph{emphasized words,
including \emph{double-emphasized}
words}, are shown here.

```

![](https://img-blog.csdnimg.cn/20210415142817272.png#pic_center)

### 2.3 段落格式和间距

----------

#### 2.3.1 长度和长度变量

在前面的一些章节，我们已经见到一些长度和长度变量的用法，这里首先统一介绍长度和长度变量.

长度的数值 `⟨length⟩` 由数字和单位组成，常用的单位见下表：

<img src="https://img-blog.csdnimg.cn/20210415142825445.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RyZWFtaW5nX2NvZGVy,size_16,color_FFFFFF,t_70#pic_center" style="zoom:50%;" />

在一些情况下还会用到可伸缩的 “弹性长度”，如 `12pt plus 2pt minus 3pt` 表示基础长度为 `12pt`，可以伸展到 `14pt`，也可以收缩到 `9pt`. 也可只定义 `plus` 或者 `minus` 的部分，如 `0pt plus 5pt`.

长度的数值还可以用长度变量本身或其倍数来表达，如 `2.5\parindent` 等.

LaTeX \LaTeX LATEX 预定义了大量的长度变量用于控制版面格式，如页面宽度和高度、首行缩进、段落间距等. 如果需要**自定义长度变量**，需使用如下命令：

```
\newlength{\⟨length command⟩}

```

长度变量可以用 `\setlength` 赋值，或用 `\addtolength` 增加长度：

```
\setlength{\⟨length command⟩}{⟨length⟩}
\addtolength{\⟨length command⟩}{⟨length⟩}

```

#### 2.3.2 行距

前文中我们提到过 `\fontsize` 命令可以为字号设定对应的行距，但我们很少那么用，更常用的办法是在导言区使用 `\linespread` 命令：

```
\linespread{⟨factor⟩}

```

其中 `⟨factor⟩` 作用于基础行距而不是字号，缺省的基础行距是 1.2 1.2 1.2 倍字号大小（参考 `\fontsize` 命令），因此使用 `\linespread{1.5}` 意味着最终行距为 1.8 1.8 1.8 倍的字号大小.

如果不是在导言区全局修改，而想要局部地改变某个段落的行距，需要用 `\selectfont` 命令使 `\linespread` 命令的改动立即生效：

```
{\linespread{2.0}\selectfont
The baseline skip is set to be
twice the normal baseline skip.
Pay attention to the \verb|\par|
command at the end. \par}

In comparison, after the
curly brace has been closed,
everything is back to normal.

```

<img src="https://img-blog.csdnimg.cn/20210415142837165.png#pic_center" style="zoom:50%;" />

字号的改变是即时生效的，而行距的改变直到文字分段时才生效，如果需要改变某一部分文字的行距，那么不能简单地将文字包含在花括号内. 注意下面两个例子中 `\par` 命令的位置，包括上一个例子的写法：

```
{\Large Don't read this!
It is not true.
You can believe me!\par}

```

<img src="https://img-blog.csdnimg.cn/20210415142849376.png#pic_center" style="zoom:50%;" />

```
{\Large This is not true either.
But remember I am a liar.}\par

```

<img src="https://img-blog.csdnimg.cn/20210415142857517.png#pic_center" style="zoom:50%;" />

#### 2.3.3 段落格式

以下长度分别为段落的左缩进、右缩进和首行缩进：

```
\setlength{\leftskip}{⟨length⟩}
\setlength{\rightskip}{⟨length⟩}
\setlength{\parindent}{⟨length⟩}

```

它们和设置行距的命令一样，在分段时生效.  
控制段落缩进的命令为：

```
\indent
\noindent

```

LaTeX \LaTeX LATEX 默认在段落开始时缩进，长度为用上述命令设置的 `\parindent`. 如果需要在某一段不缩进，可在段落开头使用 `\noindent` 命令. 相反地，`\indent` 命令强制开启一段首行缩进的段落，在段落开头使用多个 `\indent` 命令可以累加缩进量.

LaTeX \LaTeX LATEX 还默认在 `\chapter`、`\section` 等章节标题命令之后的第一段不缩进，如果不习惯这种设定，可以调用 **indentfirst** 宏包，令第一段的首行缩进照常.

段落间的垂直间距为 `\parskip`，如设置段落间距在 `0.8ex` 到 `1.5ex` 变动：

```
\setlength{\parskip}{1ex plus 0.5ex minus 0.2ex}

```

#### 2.3.4 水平间距

LaTeX \LaTeX LATEX 默认为将单词之间的 “空格” 转化为水平间距，如果需要在文中手动插入额外的水平间距，可使用 `\hspace` 命令：

```
This\hspace{1.5cm}is a space of 1.5 cm.

```

<img src="https://img-blog.csdnimg.cn/20210415142908350.png#pic_center" style="zoom:50%;" />

`\hspace` 命令生成的水平间距如果位于一行的开头或末尾，则有可能因为断行而被舍弃，可使用 `\hspace*` 命令代替 `\hspace` 命令得到不会因断行而消失的水平间距.

命令 `\stretch{⟨n⟩}` 生成一个特殊弹性长度，参数 `⟨n⟩` 为权重，它的基础长度为 `0pt`，但可以无限延伸，直到占满可用的空间. 如果同一行内出现多个 `\stretch{⟨n⟩}`，这一行的所有可用空间将按每个 `\stretch` 命令给定的权重 `⟨n⟩` 进行分配.

命令 `\fill` 相当于 `\stretch{1}`：

```
x\hspace{\stretch{1}}
x\hspace{\stretch{3}}
x\hspace{\fill}x

```

<img src="https://img-blog.csdnimg.cn/20210415142918185.png#pic_center" style="zoom:50%;" />

在正文中用 `\hspace` 命令生成水平间距时，往往使用 `em` 作为单位，生成的间距随字号大小而变. 我们在数学公式中见过 `\quad` 和 `\qquad` 命令，它们也可以用于文本中，分别相当于 `\hspace{1em}` 和 `\hspace{2em}`：

```
{\Large big\hspace{1em}y}\\
{\Large big\quad y}\\
nor\hspace{2em}mal\\
nor\qquad mal\\
{\tiny tin\hspace{1em}y}\\
{\tiny tin\quad y}

```

<img src="https://img-blog.csdnimg.cn/20210415142932464.png#pic_center" style="zoom:50%;" />

#### 2.3.5 垂直间距

在页面中，段落、章节标题、行间公式、列表、浮动体等元素之间的间距是 LaTeX \LaTeX LATEX 预设的，比如 `\parskip`，默认设置为 `0pt plus 1pt`.

如果我们想要人为地增加段落之间的垂直间距，可以在两个段落之间的位置使用 `\vspace` 命令：

```
A paragraph.

\vspace{2ex}
Another paragraph.

```

<img src="https://img-blog.csdnimg.cn/20210415142942741.png#pic_center" style="zoom:50%;" />

`\vspace` 命令生成的垂直间距在一页的顶端或底端可能被 “吞掉”，类似 `\hspace` 在一行的开头和末尾那样. 对应地，`\vspace*` 命令产生不会因断页而消失的垂直间距. `\vspace` 也可用`\stretch` 设置无限延伸的垂直长度.

在段落内的两行之间增加垂直间距，一般通过给断行命令 `\\` 加可选参数，如 `\\[6pt]` 或 `\\*[6pt]`. `\vspace` 也可以在段落内使用，区别在于 `\vspace` 只引入垂直间距而不断行：

```
Use command \verb|\vspace{12pt}|
to add \vspace{12pt} some spaces
between lines in a paragraph.

Or you can use \verb|\\[12pt]|
to \\[12pt] add vertical space,
but it also breaks the line.

```

<img src="https://img-blog.csdnimg.cn/20210415142952344.png#pic_center" style="zoom:50%;" />

另外 LaTeX \LaTeX LATEX 还提供了 `\bigskip`, `\medskip`, `\smallskip` 来增加预定义长度的垂直间距.

```
\parbox[t]{3em}{TeX\par TeX}
\parbox[t]{3em}{TeX\par\smallskip TeX}
\parbox[t]{3em}{TeX\par\medskip TeX}
\parbox[t]{3em}{TeX\par\bigskip TeX}

```

<img src="https://img-blog.csdnimg.cn/20210415143000718.png#pic_center" style="zoom:50%;" />

### 2.4 页面和分栏

--------

控制页边距的参数由下图（奇数页）中给出的各种长度变量控制.

<img src="https://img-blog.csdnimg.cn/20210415143009840.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RyZWFtaW5nX2NvZGVy,size_16,color_FFFFFF,t_70#pic_center" style="zoom:50%;" />

可以用 `\setlength` 命令修改这些长度变量，以达到调节页面尺寸和边距的作用；反之也可以利用这些长度变量来决定排版内容的尺寸，如在 `tabularx` 环境或 `\includegraphics` 命令的参数里，设置图片或表格的宽度为 `0.8\textwidth` .

页边距等比较直观的参数则必须间接设置。我们根据上图将各个方向的页边距计算公式给出（以奇数页为例）：

```
⟨left-margin⟩ = 1in + \hoffset + \oddsidemargin
⟨right-margin⟩ = \paperwidth − ⟨left-margin⟩ − \textwidth
⟨top-margin⟩ = 1in + \voffset + \topmargin + \headheight + \headsep
⟨bottom-margin⟩ = \paperheight − ⟨top-margin⟩ − \textheight

```

如果需要设置合适的 `⟨left-margin⟩` 和 `⟨right-margin⟩`，就要通过上述方程组把 `\oddsidemargin` 和 `\textwidth` 等参数解出来！

幸好 **geometry** 宏包提供了设置页边距等参数的简便方法，能够帮我们完成背后繁杂的计算.

#### 2.4.1 利用 geometry 宏包设置页面参数

**geometry** 宏包的调用方式类似于 `graphicx`，你既可以调用 **geometry** 宏包然后用其提供的 `\geometry` 命令设置页面参数：

```
\usepackage{geometry}
\geometry{⟨geometry-settings⟩}

```

也可以将参数指定为宏包的选项：

```
\usepackage[⟨geometry-settings⟩]{geometry}

```

其中 `⟨geometry-settings⟩` 多以`⟨key⟩=⟨value⟩` 的形式组织.

比如，符合 Microsoft Word 习惯的页面设定是 A4 纸张，上下边距 1 英寸，左右边距 1.25 英寸，于是我们可以通过如下两种等效的方式之一设定页边距：

```
\usepackage[left=1.25in,right=1.25in,top=1in,bottom=1in]{geometry}
% or like this:
\usepackage[hmargin=1.25in,vmargin=1in]{geometry}

```

又比如，需要设定周围的边距一致为 1.25 英寸，可以用更简单的语法：

```
\usepackage[margin=1.25in]{geometry}

```

对于书籍等双面文档，习惯上奇数页右边、偶数页左边留出较多的页边距，而书脊一侧的奇数页左边、偶数页右边页边距较少. 我们可以这样设定：

```
\usepackage[inner=1in,outer=1.25in]{geometry}

```

更详细的用法可查阅 **geometry** 宏包的帮助文档.

#### 2.4.2 页面内容的垂直对齐

LaTeX \LaTeX LATEX 默认将页面内容在垂直方向分散对齐. 对于有大量图表的文档，许多时候想要做到排版匀称的页面很困难，垂直分散对齐会造成某些页面的垂直间距过宽，还可能报大量的  
`Underfull \vbox` 消息。 LaTeX \LaTeX LATEX 还提供了另一种策略：将页面内容向顶部对齐，给底部留出高度不一的空白.

以下命令分别令页面在垂直方向向顶部对齐 / 分散对齐：

```
\raggedbottom
\flushbottom

```

#### 2.4.3 分栏

LaTeX \LaTeX LATEX 支持简单的单栏或双栏排版.

标准文档类的全局选项 `onecolumn`、`twocolumn` 可控制全文分单栏或双栏排版。 LaTeX \LaTeX LATEX 也提供了切换单 / 双栏排版的命令：

```
\onecolumn
\twocolumn[⟨one-column top material⟩]

```

`\twocolumn` 支持带一个可选参数，用于排版双栏之上的一部分单栏内容.

切换单 / 双栏排版时总是会另起一页（`\clearpage`）。在双栏模式下使用 `\newpage` 会换栏而不是换页；`\clearpage` 则能够换页.

双栏排版时每一栏的宽度为 `\columnwidth`，它由 `\textwidth` 减去 `\columnsep` 的差除以 2 得到. 两栏之间还有一道竖线，宽度为 `\columnseprule`，默认为零，也就是看不到竖线.

### 2.5 页眉页脚

-------

#### 2.5.1 基本的页眉页脚样式

LaTeX \LaTeX LATEX 中提供了命令 `\pagestyle` 来修改页眉页脚的样式：

```
\pagestyle{⟨page-style⟩}

```

命令 `\thispagestyle` 只影响当页的页眉页脚样式：

```
\thispagestyle{⟨page-style⟩}

```

`⟨page-style⟩` 参数为样式的名称，在 LaTeX \LaTeX LATEX 里预定义了四类样式：

<img src="https://img-blog.csdnimg.cn/20210415143028405.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RyZWFtaW5nX2NvZGVy,size_16,color_FFFFFF,t_70#pic_center" style="zoom:50%;" />

其中 `headings` 的情况较为复杂：

*   article 文档类，`twoside` 选项偶数页为页码和节标题，奇数页为小节标题和页码
*   article 文档类，`oneside` 选项页眉为节标题和页码
*   report / book 文档类，`twoside` 选项偶数页为页码和章标题，奇数页为节标题和页码
*   report / book 文档类，`oneside` 选项页眉为章标题和页码

`\pagenumbering` 命令令我们能够改变页眉页脚中的页码样式：

```
\pagenumbering{⟨style⟩}

```

`⟨style⟩` 为页码样式，默认为 `arabic`（阿拉伯数字），还可修改为 `roman`（小写罗马数字）、`Roman`（大写罗马数字）等. 注意使用 `\pagenumbering` 命令后会将页码重置为 1 1 1. book 文档类的 `\frontmatter` 和 `\mainmatter` 内部就使用了 `\pagenumbering` 命令切换页码样式.

#### 2.5.2 手动更改页眉页脚的内容

对于 `headings` 或者 `myheadings` 样式， LaTeX \LaTeX LATEX 允许用户使用命令手动修改页眉上面的内容，特别是因为使用了 `\chapter*` 等命令而无法自动生成页眉页脚的情况：

```
\markright{⟨right-mark⟩}
\markboth{⟨left-mark⟩}{⟨right-mark⟩}

```

在双面排版、`headings` /`myheadings` 页眉页脚样式下，`⟨left-mark⟩` 和 `⟨right-mark⟩` 的内容分别预期出现在左页（偶数页）和右页（奇数页）. 事实上 `\chapter` 和 `\section` 等章节命令内部也使用 `\markboth` 或者 `\markright` 生成页眉.

#### 2.5.3 fancyhdr 宏包

**fancyhdr** 宏包改善了页眉页脚样式的定义方式，允许我们将内容自由安置在页眉和页脚的左、中、右三个位置，还为页眉和页脚各加了一条横线.

**fancyhdr** 自定义了样式名称 `fancy`. 使用 **fancyhdr** 宏包定义页眉页脚之前，通常先用 `\pagestyle{fancy}` 调用这个样式. 在 **fancyhdr** 中定义页眉页脚的命令为：

```
\fancyhf[⟨position⟩]{…}
\fancyhead[⟨position⟩]{…}
\fancyfoot[⟨position⟩]{…}

```

> *   其中 `⟨position⟩` 为 `L`（左）/ `C`（中）/ `R`（右）以及与 `O`（奇数页）/ `E`（偶数页）字母的组合
>
> *   `\fancyhf` 用于同时定义页眉和页脚，习惯上使用 `\fancyhf{}` 来清空页眉页脚的设置
>

下面给出了 **fancyhdr** 基础用法的一个示例，效果为将章节标题放在和 `headings` 一致的位置，但使用加粗格式；页码都放在页脚正中；修改横线宽度，“去掉” 页脚的横线.

```
% 在导言区使用此代码
\usepackage{fancyhdr}
\pagestyle{fancy}
\renewcommand{\chaptermark}[1]{\markboth{#1}{}}
\renewcommand{\sectionmark}[1]{\markright{\thesection\ #1}}
\fancyhf{}
\fancyfoot[C]{\bfseries\thepage}
\fancyhead[LO]{\bfseries\rightmark}
\fancyhead[RE]{\bfseries\leftmark}
\renewcommand{\headrulewidth}{0.4pt} % 注意不用\setlength
\renewcommand{\footrulewidth}{0pt}

```

**fancyhdr** 还支持用 `\fancypagestyle` 为自定义的页眉页脚样式命名，或者重新定义已有的样式如 `plain`等：

```
% 自定义myfancy 样式
\fancypagestyle{myfancy}{%
\fancyhf{}
\fancyhead{...}
\fancyfoot{...}
}
% 使用样式
\pagestyle{myfancy}

```