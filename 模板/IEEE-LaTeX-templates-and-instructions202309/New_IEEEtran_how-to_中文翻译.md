# 如何使用 IEEEtran LaTeX 模板

> 原文件：`New_IEEEtran_how-to.tex`  
> 适用版本：IEEEtran 1.8b  
> 翻译说明：LaTeX 命令、环境名、标签、网址和参考文献书目信息保持原样；示例中的英文内容在不影响代码含义的前提下译为中文。

## 作者及许可说明

作者：IEEE 出版技术部。

稿件创建于 2020 年 10 月。本作品由 IEEE 出版技术部开发，依据 LaTeX Project Public License（LPPL）1.3 版发布。2003 年 12 月 1 日及以后发布的所有 LaTeX 发行版，其基础文档中均包含 LPPL 1.3 版副本。本文观点仅代表作者本人；本文不提供任何明示或默示担保，使用者自行承担全部风险。

## 摘要

本文介绍论文中最常见的组成要素，以及如何结合 LaTeX 使用 IEEEtran 文档类，生成适合向电气与电子工程师协会（IEEE）投稿的文件。通过选择适当的文档类选项，IEEEtran 可以生成会议论文、期刊论文和技术短文（通信类稿件）。

## 关键词

文档类、IEEEtran、LaTeX、论文、样式、模板、排版。

## 1. 引言

欢迎阅读这份经过更新和简化的 IEEEtran LaTeX 文档类使用指南。IEEE 审查了数百篇使用该宏包提交的作者稿件，并以此为基础编写了这份易于使用的指南。

本文介绍期刊论文中最常用的组成要素。较少使用的要素请参阅 `IEEEtran_HOWTO.pdf`。

本文适用于 IEEEtran 1.8b。

IEEEtran 模板包包含以下示例文件：

- `bare_jrnl.tex`
- `bare_conf.tex`
- `bare_jrnl_compsoc.tex`
- `bare_conf_compsoc.tex`
- `bare_jrnl_comsoc.tex`

这些都是便于快速理解文档结构的“最简模板”。

本文假定读者已具备 LaTeX 的基本使用知识。初学者可阅读 Tobias Oetiker 的《The Not So Short Introduction to LaTeX》：<http://tug.ctan.org/info/lshort/english/lshort.pdf>。

## 2. 模板的设计目的、使用意图与局限性

模板的作用是**近似呈现论文最终出版时的外观和篇幅**。因此，模板生成的文件**不是最终印刷版本，也不是 IEEE Xplore 上展示的最终成品**。

模板可帮助作者估算论文最终版本的页数。其 LaTeX 文件结构便于转换为 XML，供 IEEE 外包供应商的排版系统使用。XML 文件用于生成最终的印刷版/IEEE Xplore PDF，随后还会转换成 IEEE Xplore 使用的 HTML。

## 3. 从哪里获取 LaTeX 发行版

IEEE 建议使用 TeX Users Group（TUG）提供的发行版：<http://www.tug.org>。用户可以加入 TUG 并获取 DVD 发行版，也可以从其网站免费下载 TeX Live：<http://www.tug.org/texlive/>。

该发行版支持 Windows、macOS 和 Linux。

## 4. 从哪里获取 IEEEtran 模板

**IEEE Template Selector** 始终提供最新版本的 LaTeX 和 Microsoft Word 模板：<https://template-selector.ieee.org/>。

请按照页面步骤选择目标出版物对应的正确模板。许多 IEEE 出版物采用 IEEEtran LaTeX 模板，但部分出版物使用自己的专用模板。这些模板通常基于 IEEEtran，不过其具体要求可能与本文略有差异。

## 5. 从哪里获得 LaTeX 帮助——用户社区

以下在线社区对 LaTeX 初学者和有经验的用户都很有帮助。检索历史内容通常可以找到常见问题的答案：

- <http://www.latex-community.org/>
- <https://tex.stackexchange.com/>

## 6. IEEEtran 文档类选项

在 LaTeX 文件开头，必须确定计划采用的出版物样式。IEEEtran 常用文档类选项如下：

| 稿件类型 | 文档类声明 |
|---|---|
| 普通期刊论文 | `\documentclass[journal]{IEEEtran}` |
| 会议论文 | `\documentclass[conference]{IEEEtran}` |
| Computer Society 期刊论文 | `\documentclass[10pt,journal,compsoc]{IEEEtran}` |
| Computer Society 会议论文 | `\documentclass[conference,compsoc]{IEEEtran}` |
| Communications Society 期刊论文 | `\documentclass[journal,comsoc]{IEEEtran}` |
| 简报、通信或技术短文 | `\documentclass[9pt,technote]{IEEEtran}` |

同行评审投稿和其他特殊要求还可以使用更多选项。IEEE 建议作者从一开始就在基础双栏格式下撰写论文，以确保所有公式、表格和图形都能适应最终的双栏版式。

如果主编（EIC）要求采用特定评审格式，请参阅 `IEEEtran_HOWTO.pdf` 中有关同行评审投稿设置的说明。

## 7. 如何创建常见的论文前置部分

下面介绍常见前置要素的一般写法。Computer Society 出版物和会议论文可能有特殊变体，应遵循相应出版物的具体说明。

### 7.1 论文标题

论文标题写为：

```latex
\title{论文标题}
```

如非必要，标题中应尽量避免使用数学公式或化学式。

### 7.2 作者姓名与单位

作者部分可按如下方式编写：

```latex
\author{Masahito Hayashi
\IEEEmembership{Fellow, IEEE}, Masaki Owari
\thanks{M. Hayashi 任职于名古屋大学数学研究科，
日本名古屋。}
\thanks{M. Owari 任职于静冈大学信息学部，
日本静冈县滨松市。}
}
```

请务必使用 `\IEEEmembership` 命令标明作者的 IEEE 会员等级。

会议论文和 Computer Society 出版物的作者编码方式可能不同，具体请参阅 `IEEEtran_HOWTO.pdf`。注意，作者组的右花括号应放在所有 `\thanks` 内容之后，这可以避免生成空白首页。

### 7.3 页眉短标题

使用 `\markboth` 命令声明页眉。该命令接收两个参数：第一个参数包含期刊名称等信息，第二个参数包含作者姓名和论文标题。

```latex
\markboth{Journal of Quantum Electronics,
Vol. 1, No. 1, January 2021}
{Author1, Author2,
\MakeLowercase{\textit{(et al.)}}:
Paper Title}
```

### 7.4 版权行

Transactions 和 Journals 稿件在投稿阶段不必添加版权行，IEEE 的出版流程会加入适当的版权信息。

如果撰写会议论文，请参阅 `IEEEtran_HOWTO.pdf`，了解“出版物标识”（Publication ID Marks）的具体写法。

### 7.5 摘要

调用 `\maketitle` 后，摘要是论文的第一个组成要素：

```latex
\begin{abstract}
摘要正文。
\end{abstract}
```

摘要中应尽量避免使用数学公式和化学式。

### 7.6 索引词

索引词有助于其他研究人员发现论文。不同学会可能拥有各自的关键词表，请联系目标出版物的主编获取相应列表。

```latex
\begin{IEEEkeywords}
宽带网络，服务质量
\end{IEEEkeywords}
```

## 8. 如何创建常见的正文要素

### 8.1 段首下沉大写字母

论文第一段通常使用下沉大写字母，且第一个单词的其余字母使用大写形式。可通过 `\IEEEPARstart` 实现：

```latex
\IEEEPARstart{T}{his} is the first paragraph
of your paper. . .
```

中文论文通常不需要强行套用这一英文首字母效果；英文投稿时按模板使用即可。

### 8.2 节与小节

章节标题使用标准 LaTeX 命令 `\section`、`\subsection` 和 `\subsubsection`。编号由 LaTeX 自动完成，并会根据出版物类型采用不同格式。

章节标题后的第一段通常不缩进，可使用：

```latex
\section{章节标题}
\noindent 段落正文……
```

### 8.3 文献引用

使用 LaTeX 的 `\cite` 命令进行文献引用，它会生成符合 IEEE 风格的方括号编号。文件导言区应包含：

```latex
\usepackage{cite}
```

单篇引用：

```latex
见 \cite{ams}
```

多篇引用：

```latex
\cite{ams,oxford,lacomp}
```

### 8.4 插图

插图使用标准 LaTeX 命令：

```latex
\begin{figure}[!t]
\centering
\includegraphics[width=2.5in]{fig1}
\caption{单幅图的图注。}
\label{fig1}
\end{figure}
```

参数 `[!t]` 使浮动对象优先放置在页面顶部，以符合 IEEE 风格。导言区必须加载：

```latex
\usepackage{graphicx}
```

正文中交叉引用插图：

```latex
见图 \ref{fig1}……
```

### 8.5 表格

表格使用标准 LaTeX 写法。简单示例如下：

```latex
\begin{table}
\begin{center}
\caption{滤波器设计方程……}
\label{tab1}
\begin{tabular}{|c|c|c|}
\hline
滤波器阶数 & 任意系数 $e_m$ & 系数 $b_{ij}$ \\
\hline
1 & $b_{ij}=\hat{e}.\hat{\beta}_{ij}$ & $b_{00}=0$ \\
\hline
2 & $\beta_{22}=(1,-1,-1,1,1,1)$ & \\
\hline
3 & $b_{ij}=\hat{e}.\hat{\beta}_{ij}$ & $b_{00}=0$ \\
\hline
\end{tabular}
\end{center}
\end{table}
```

正文中引用表格：

```latex
表~\ref{tab1} 列出了闭式表达式……
```

### 8.6 列表

本文介绍三种列表：普通无编号列表、编号列表和项目符号列表。IEEEtran 还提供了许多更复杂的列表选项，详见 `IEEEtran_HOWTO.pdf`。

普通无编号列表：

```latex
\begin{list}{}{}
\item{bare_jrnl.tex}
\item{bare_conf.tex}
\item{bare_jrnl_compsoc.tex}
\item{bare_conf_compsoc.tex}
\item{bare_jrnl_comsoc.tex}
\end{list}
```

编号列表：

```latex
\begin{enumerate}
\item{bare_jrnl.tex}
\item{bare_conf.tex}
\item{bare_jrnl_compsoc.tex}
\item{bare_conf_compsoc.tex}
\item{bare_jrnl_comsoc.tex}
\end{enumerate}
```

项目符号列表：

```latex
\begin{itemize}
\item{bare_jrnl.tex}
\item{bare_conf.tex}
\item{bare_jrnl_compsoc.tex}
\item{bare_conf_compsoc.tex}
\item{bare_jrnl_comsoc.tex}
\end{itemize}
```

### 8.7 其他要素

算法、定理、证明以及跨双栏表格、插图或公式等较少使用的要素，请参阅 `IEEEtran_HOWTO.pdf` 中的“双栏浮动对象”（Double Column Floats）部分。

## 9. 如何创建常见的论文后置部分

### 9.1 致谢

致谢应放在参考文献之前，用一个简洁段落感谢支持本文工作的个人和机构：

```latex
\section{Acknowledgments}
\noindent 在此说明对论文工作提供支持的人员或机构。
```

### 9.2 参考文献

#### 使用 `\bibitem` 手工编写

一种简单方法是使用 `\bibitem` 宏定义每条参考文献。例如：

```latex
\bibitem{Sira3}
H. Sira-Ramirez, ``On the sliding mode
control of nonlinear systems,''
\textit{Systems \& Control Letters},
vol. 19, pp. 303--312, 1992.
```

原文还给出了会议论文和多作者期刊论文的 `\bibitem` 示例。正式使用时应保留论文题名和书目信息的原始语言，并按 IEEE 引文格式填写作者、题名、刊物或会议名称、卷期、页码和年份。

### 9.3 参考文献中的重音字符

参考文献中出现带重音符号的字符时，应使用标准 LaTeX 重音命令，**不要使用数学模式来生成字符重音**。

```latex
\'e, \"o, \`a, \~e
```

### 9.4 使用 BibTeX

如需使用 BibTeX，请参阅 IEEEtran Bibliography 宏包附带的文档。

### 9.5 作者简介与照片

作者可以选择是否加入照片。照片应使用位图格式，如 `.tif` 或 `.jpg`，并调整到允许的空间范围内。

不含照片：

```latex
\begin{IEEEbiographynophoto}{Jane Doe}
此处填写不带照片的作者简介。
\end{IEEEbiographynophoto}
```

包含照片：

```latex
\begin{IEEEbiography}
[{\includegraphics[width=1in,height=1.25in,clip,
keepaspectratio]{fig1.png}}]
{IEEE Publications Technology Team}
此处可填写教育背景、职业经历、研究方向及其他兴趣。
\end{IEEEbiography}
```

## 10. 数学排版及其重要性

数学公式的排版惯例旨在**保证数学文献表达的一致性和清晰度**，使读者既能理解作者的思想，也能迅速掌握新的概念。

LaTeX 和 MathType 等软件在正确使用时可以生成美观的数学公式，但误用也很容易导致错误的数学显示效果。IEEE 希望通过规范指导帮助作者写出尽可能高质量的论文。

本节示例参考了以下资料：

- American Mathematical Society 出版的 *Mathematics into Type*；
- Oxford University Press 出版的 *The Printing of Mathematics*；
- F. Mittelbach 与 M. Goossens 的 *The LaTeX Companion*；
- G. Grätzer 的 *More Math into LaTeX*；
- American Mathematical Society 发布的 *AMS-StyleGuide-online.pdf*。

更多示例见：<http://journals.ieeeauthorcenter.ieee.org/wp-content/uploads/sites/7/IEEE-Math-Typesetting-Guide.pdf>。

### 10.1 行间公式

简单的行间公式使用 `equation` 环境。使用 `\label` 为公式创建标识符，LaTeX 会自动编号：

```latex
\begin{equation}
\label{deqn_ex1}
x = \sum_{i=0}^{n} 2{i} Q.
\end{equation}
```

在正文中使用 `\ref` 引用：

```latex
请见式 (\ref{deqn_ex1})。
```

### 10.2 公式编号

**连续编号：** 论文中的公式应从头至尾连续编号，例如 `(1)`、`(2)`、`(3)`。不要用罗马数字或章节号为公式编号。

**附录公式：** 最好在附录中延续正文的连续编号，但也允许使用 `(A1)`、`(A2)` 等形式。

**连字符和句点：** 公式编号中不应使用连字符或句点。子公式应写成 `(1a)` 而不是 `(1-a)`，写成 `(2a)` 而不是 `(2.a)`。全文应保持一致。

### 10.3 多行公式与对齐

因长度需要换行、但无特定对齐点的单个公式使用 `multline`：

```latex
\begin{multline}
\text{示例的第一行}\\
\text{示例的第二行}\\
\text{示例的第三行}
\end{multline}
```

需要在等号处对齐时使用 `align`：

```latex
\begin{align}
a &= c+d \\
b &= e+f
\end{align}
```

`align` 也可以同时设置多个对齐点：

```latex
\begin{align}
x &= y & X & =Y & a &=bc\\
x' &= y' & X' &=Y' &a' &=bz
\end{align}
```

### 10.4 子公式编号

`amsmath` 宏包提供 `subequations` 环境，便于生成子公式编号：

```latex
\begin{subequations}\label{eq:2}
\begin{align}
f&=g \label{eq:2A}\\
f' &=g' \label{eq:2B}\\
\mathcal{L}f &= \mathcal{L}g \label{eq:2c}
\end{align}
\end{subequations}
```

### 10.5 矩阵

常用矩阵环境包括：

- `matrix`：无定界符；
- `pmatrix`：圆括号；
- `bmatrix`：方括号；
- `Bmatrix`：花括号；
- `vmatrix`：单竖线；
- `Vmatrix`：双竖线。

例如：

```latex
\begin{equation}
\begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix}
\end{equation}
```

其他矩阵只需将 `pmatrix` 替换为相应环境即可。

### 10.6 数组

`array` 环境可以排版类似矩阵的公式。定界符需要手动输入，但列对齐、水平线和竖直线可以灵活设置。`array` 的参数控制列对齐方式与竖线位置。

简单数组：

```latex
\begin{equation}
\left(
\begin{array}{cccc}
a+b+c & uv & x-y & 27\\
a+b & u+v & z & 134
\end{array}\right)
\end{equation}
```

将参数改为 `{cccr}` 可使最后一列右对齐；参数中加入 `|` 可指定竖线位置，使用 `\hline` 可加入横线：

```latex
\begin{equation}
\left(
\begin{array}{c|c|c|r}
a+b+c & uv & x-y & 27\\ \hline
a+b & u+v & z & 134
\end{array}\right)
\end{equation}
```

### 10.7 分段结构

分段公式经常被错误地使用 `array` 环境排版。`cases` 环境无需手动键入 `\left\lbrace`，并能自动提供正确的列对齐：

```latex
\begin{equation*}
{z_m(t)} =
\begin{cases}
1,&{\text{if}}\ {\beta}_m(t),\\
0,&{\text{otherwise.}}
\end{cases}
\end{equation*}
```

`&` 用于标记对齐位置。不要用 `\quad` 或其他固定空格强行对齐各列。`if`、`otherwise` 等文本应使用 `\text` 宏。

### 10.8 公式中的函数格式

大多数常见函数可通过在函数名前加反斜杠获得正确格式。如果没有相应命令，可使用 `\text` 宏：

```latex
\begin{equation*}
d_{R}^{KM} = \underset {d_{l}^{KM}}
{\text{arg min}} \{d_{1}^{KM},\ldots,d_{6}^{KM}\}.
\end{equation*}
```

### 10.9 公式中的文本缩写

公式中的文本缩写应使用 `\text{}`，使其外观与正文一致：

```latex
\begin{equation*}
\text{MSE} = \frac{1}{n}\sum_{i=1}^{n}
(Y_i-\hat{Y_i})^2
\end{equation*}
```

### 10.10 过时写法

不要使用过时的 `eqnarray` 环境，也不要使用 `$$ ... $$` 作为行间公式定界符。`$$ ... $$` 源自 Plain TeX，不应在 LaTeX 中使用，否则可能导致不良的垂直间距。

### 10.11 为行间公式使用适当的定界符

**单行、不编号：**

```latex
\[ ... \]
```

或：

```latex
\begin{equation*} ... \end{equation*}
```

环境名中的星号关闭公式编号。

**多行、不编号且需要对齐：**

```latex
\begin{align*} ... \end{align*}
```

**单行、编号：**

```latex
\begin{equation} ... \end{equation}
```

**多行、编号：**

```latex
\begin{align} ... \end{align}
```

## 11. LaTeX 宏包建议

宏包声明应紧接在文件开头的文档类声明之后。本文使用了：

```latex
\usepackage{amsmath,amsfonts}
\usepackage{algorithmic}
\usepackage{array}
\usepackage[caption=false,font=normalsize,
   labelfont=sf,textfont=sf]{subfig}
\usepackage{textcomp}
\usepackage{stfloats}
\usepackage{url}
\usepackage{verbatim}
\usepackage{graphicx}
\usepackage{balance}
```

## 12. 补充建议

请使用“软”交叉引用，例如 `\eqref{Eq}` 或 `(\ref{Eq})`，不要在正文中直接写死 `(1)`。这样，在合并章节、增加公式或调整图形与引文顺序时，不必逐行修改编号。

`subequations` 环境即使没有显示任何公式编号，也会递增主公式计数器。忽略这一点可能导致编号从 `(17)` 跳到 `(20)`。

BibTeX 不会自动凭空获得书目信息，它从 `.bib` 文件读取数据。如果使用 BibTeX 生成参考文献，投稿时必须同时提交相应的 `.bib` 文件。

不要把同一个 `\label` 同时用于小小节和表格等不同对象，否则交叉引用可能指向错误编号。

`\label` 必须放在更新相应计数器的命令之后。尤其是图和表的 `\label` 不应放在 `\caption` 之前。

不要在 `array` 环境内部使用 `\nonumber` 或 `\notag`。`array` 本身不会生成公式编号，这些命令反而可能错误地取消外层公式环境本应显示的编号。

## 13. 最终检查清单

投稿前应确认：

1. 所有公式均按顺序编号，没有缺号或重复编号。公式编号不要包含连字符或句点。正文使用 `(1)`、`(2)`、`(3)`，子公式使用 `(1a)`、`(1b)`，附录公式可使用 `(A1)`、`(A2)`。
2. 所有公式均采用正确格式，包括公式中的文本、函数名称以及 `cases` 和 `array` 的对齐点。
3. 所有图形文件均已包含并能正常加载。
4. 所有参考文献均已包含在主 LaTeX 文件中；如果调用外部书目数据库，则相应 `.bib` 文件必须一并提供。

## 参考资料

为保证检索和引用准确性，题名及书目信息保留原文：

1. *Mathematics into Type*, American Mathematical Society.
2. T. W. Chaundy, P. R. Barrett and C. Batey, *The Printing of Mathematics*, Oxford University Press, London, 1954.
3. F. Mittelbach and M. Goossens, *The LaTeX Companion*.
4. G. Grätzer, *More Math into LaTeX*.
5. *AMS-StyleGuide-online.pdf*, American Mathematical Society.
6. H. Sira-Ramirez, “On the sliding mode control of nonlinear systems,” *Systems & Control Letters*, vol. 19, pp. 303–312, 1992.
7. A. Levant, “Exact differentiation of signals with unbounded higher derivatives,” in *Proceedings of the 45th IEEE Conference on Decision and Control*, San Diego, California, USA, pp. 5585–5590, 2006.
8. M. Fliess, C. Join, and H. Sira-Ramirez, “Non-linear estimation is easy,” *International Journal of Modelling, Identification and Control*, vol. 4, no. 1, pp. 12–27, 2008.
9. R. Ortega, A. Astolfi, G. Bastin, and H. Rodriguez, “Stabilization of food-chain systems using a port-controlled Hamiltonian description,” in *Proceedings of the American Control Conference*, Chicago, Illinois, USA, pp. 2245–2249, 2000.

