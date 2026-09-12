# 使用 IEEEtran.cls 撰写 IEEE 期刊与汇刊论文的示例

> 原文件：`bare_jrnl_new_sample4.tex`  
> 翻译说明：LaTeX 命令、公式、标签、网址及参考文献书目信息保持原样；原文中的伪拉丁占位段落没有实际语义，译文中予以标注而不作强行翻译。

## 作者与页眉示例

作者：IEEE 出版技术部（IEEE 工作人员）。

脚注说明：本文由 IEEE 出版技术组制作，该团队位于美国新泽西州皮斯卡塔韦。稿件于 2021 年 4 月 19 日收到，2021 年 8 月 16 日修订。

原文件使用 `\markboth` 设置论文页眉，并用 `\IEEEpubid` 设置出版物标识。若使用 `\IEEEpubid`，必须在第二栏调用 `\IEEEpubidadjcol`，避免正文与出版物标识重叠。

## 摘要

本文介绍论文中最常见的组成要素，以及如何结合 LaTeX 使用 IEEEtran 文档类，生成适合向 IEEE 投稿的文件。通过选择适当的文档类选项，IEEEtran 可以生成会议论文、期刊论文以及技术短文（通信类稿件）。

## 关键词

论文投稿、IEEE、IEEEtran、期刊、LaTeX、论文、模板、排版。

## 1. 引言

本文件旨在作为一个“示例论文文件”，适用于使用 IEEEtran.cls 1.8b 及更高版本、通过 LaTeX 编写的 IEEE 期刊论文。最常用的组成要素已在经过简化和更新的 `New_IEEEtran_how-to.pdf` 中介绍；较少使用的要素可参阅原始文档 `IEEEtran_HOWTO.pdf`。

本文假定读者已经具备 LaTeX 的基本使用知识。LaTeX 初学者可阅读 Tobias Oetiker 的《The Not So Short Introduction to LaTeX》：<http://tug.ctan.org/info/lshort/english/lshort.pdf>，其中系统概述了 LaTeX 的基本使用方法。

## 2. 模板的设计目的、使用意图与局限性

这些模板的用途是**近似呈现论文最终出版时的外观和篇幅**。它们**并不是最终印刷版本或 IEEE Xplore 上展示的最终成品**。

模板可以帮助作者估算最终版本的页数。LaTeX 文件采用的结构便于转换为 XML，以供 IEEE 的排版系统使用。XML 文件随后用于生成最终的印刷版/IEEE Xplore PDF，并进一步转换成 IEEE Xplore 使用的 HTML。

## 3. 从哪里获得 LaTeX 帮助——用户社区

下列在线社区对 LaTeX 初学者和有经验的用户都很有帮助。检索其历史内容通常可以找到许多常见问题的答案：

- <http://www.latex-community.org/>
- <https://tex.stackexchange.com/>

## 4. 其他资源

有关数学内容排版以及 LaTeX 使用方法的更多资料，请参见参考文献 `[1]`–`[5]`。

## 5. 正文

本示例后续部分使用无实际意义的占位文本填充段落，以免采用可能侵犯版权的真实文章内容。

> 原文此处的 `Itam, que ipiti...`、`Onseque...`、`Ibus...`、`Sedigent...`、`Rum rem...` 和 `Alis nime...` 等段落均为排版占位文本，不表达需要翻译的学术内容。其作用是展示双栏正文、引文、公式引用以及 `\IEEEpubidadjcol` 的实际版面效果。

占位段落中通过 `\eqref{deqn_ex1a}` 引用如下公式：

```latex
\begin{equation}
\label{deqn_ex1a}
x = \sum_{i=0}^{n} 2{i} Q.
\end{equation}
```

## 6. 一些常见组成要素

### 6.1 节与小节

建议对各级章节标题编号，但这不是强制要求。如果采用编号，则应在整篇论文中保持一致，即正文中的所有标题和各级标题都应编号。

- 一级标题使用罗马数字；
- 二级标题使用大写英文字母；
- 三级标题使用阿拉伯数字；
- 四级标题使用小写英文字母。

“参考文献”和“致谢”标题不同于正文中的其他章节标题：它们从不编号。无论论文中的其他标题是否编号，这两个标题都只是没有编号标识的一级标题。

### 6.2 文献引用

文献引用使用 LaTeX 的 `\cite` 命令。例如：

```latex
see \cite{ref1}
```

显示为“见 [1]”。

引用多篇文献时可写为：

```latex
\cite{ref1,ref2,ref3}
```

它将生成 `[1]–[3]`。若引用的编号并不连续，可写为：

```latex
\cite{ref1,ref2,ref3,ref9}
```

它将生成 `[1]–[3], [9]`。

### 6.3 列表

本节介绍三种列表：普通无编号列表、编号列表和项目符号列表。IEEEtran 为创建列表提供了许多增强选项。如果列表比以下示例更复杂，请参阅原始 `IEEEtran_HOWTO.pdf`。

#### 普通无编号列表

```latex
\begin{list}{}{}
\item{bare_jrnl.tex}
\item{bare_conf.tex}
\item{bare_jrnl_compsoc.tex}
\item{bare_conf_compsoc.tex}
\item{bare_jrnl_comsoc.tex}
\end{list}
```

#### 简单编号列表

```latex
\begin{enumerate}
\item{bare_jrnl.tex}
\item{bare_conf.tex}
\item{bare_jrnl_compsoc.tex}
\item{bare_conf_compsoc.tex}
\item{bare_jrnl_comsoc.tex}
\end{enumerate}
```

#### 简单项目符号列表

```latex
\begin{itemize}
\item{bare_jrnl.tex}
\item{bare_conf.tex}
\item{bare_jrnl_compsoc.tex}
\item{bare_conf_compsoc.tex}
\item{bare_jrnl_comsoc.tex}
\end{itemize}
```

### 6.4 插图

图 1 展示了使用 `graphicx` 宏包创建浮动图形的示例。注意，`\label` 必须放在 `\caption` 之后或其内部。对于插图，`\caption` 应放在 `\includegraphics` 之后。

```latex
\begin{figure}[!t]
\centering
\includegraphics[width=2.5in]{fig1}
\caption{网络的仿真结果。}
\label{fig_1}
\end{figure}
```

图 2(a) 和图 2(b) 展示了由两个子图组成的跨双栏浮动图形。要使用该写法，必须加载 `subfig.sty`。

各子图的 `\label` 命令应放在对应的 `\subfloat` 命令内部；整幅图的 `\label` 必须放在 `\caption` 之后。`\hfil` 用作分隔符，以获得均匀间距。所有组成部分的总宽度不应超过正文宽度，否则会发生换行。

```latex
\begin{figure*}[!t]
\centering
\subfloat[]{\includegraphics[width=2.5in]{fig1}%
\label{fig_first_case}}
\hfil
\subfloat[]{\includegraphics[width=2.5in]{fig1}%
\label{fig_second_case}}
\caption{占位图注。（a）情形 I。（b）情形 II。}
\label{fig_sim}
\end{figure*}
```

IEEE 论文中的多子图通常不把 `(a)`、`(b)` 等标识直接放进图像，而是在总图注中统一引用和说明。要让 `subfig.sty` 生成 `(a)`、`(b)` 等子图标识，`\subfloat` 的可选参数必须存在。如果不需要子图标题，可将其内容留空，例如 `\subfloat[]`。

## 7. 表格

对于 IEEE 风格的表格，`\caption` 命令应放在表格内容之前。表题采用标题式大小写；冠词（a、an、the）、并列连词（and、but、for、or、nor）以及大多数较短的介词通常小写，除非它们位于表题的开头或结尾。

表格中的文字默认使用 `\footnotesize`，因为 IEEE 通常为表格采用较小字号。与其他交叉引用一样，`\label` 必须放在 `\caption` 之后。

```latex
\begin{table}[!t]
\caption{表格示例\label{tab:table1}}
\centering
\begin{tabular}{|c||c|}
\hline
一 & 二\\
\hline
三 & 四\\
\hline
\end{tabular}
\end{table}
```

## 8. 算法

算法应编号并包含简短标题。标题上方以及算法最后一行下方应使用横线，使算法与正文区分开来。

原示例算法标题 `Weighted Tanimoto ELM` 可译为“加权 Tanimoto 极限学习机”。算法中的主要步骤为：

- `TRAIN`：训练；
- `select randomly`：随机选择；
- `for`：对/循环；
- `return`：返回；
- `PREDICT`：预测。

公式、变量和矩阵运算应保持原样，避免改变算法含义。

> 算法后的 `Que sunt eum...` 段落同样是无实际语义的排版占位文本。

## 9. 数学排版及其重要性

数学公式的排版惯例旨在**保证不同数学文献之间表达形式的一致性与清晰度**，使读者既能理解作者的思想，也能迅速掌握新的概念。

LaTeX 和 MathType 等软件在正确使用时能够生成美观的数学公式，但误用这些工具也很容易导致错误的数学显示效果。

IEEE 希望为作者提供适当的数学排版规范，帮助其写出尽可能高质量的论文。因此，IEEE 汇集了一组正确与错误的数学排版示例，参见文献 `[1]`–`[5]`。更多示例见：

<http://journals.ieeeauthorcenter.ieee.org/wp-content/uploads/sites/7/IEEE-Math-Typesetting-Guide-for-LaTeX-Users.pdf>

### 9.1 行间公式

下面的简单行间公式使用 `equation` 环境。若要给公式编号，应使用 `\label` 宏为其创建标识符，LaTeX 会自动完成编号。

```latex
\begin{equation}
\label{deqn_ex1}
x = \sum_{i=0}^{n} 2{i} Q.
\end{equation}
```

在正文中引用该公式时使用 `\ref` 宏：

```latex
请见式 (\ref{deqn_ex1})。
```

### 9.2 公式编号

**连续编号：** 论文中的公式应从头到尾连续编号，例如 `(1)`、`(2)`、`(3)`、`(4)`、`(5)` 等。公式编号不要使用罗马数字，也不要包含章节编号。

**附录公式：** 最好在附录中继续沿用正文的连续编号，但也允许使用 `(A1)`、`(A2)` 等形式。

**连字符与句点：** 公式编号中不应使用连字符或句点。子公式应写成 `(1a)` 而不是 `(1-a)`，写成 `(2a)` 而不是 `(2.a)`。整篇论文应保持一致。

### 9.3 多行公式与对齐

下面给出若干多行公式及其正确对齐方式。

#### 因长度原因需要换行、但没有特定对齐点的单个公式

```latex
\begin{multline}
\text{本示例的第一行}\\
\text{本示例的第二行}\\
\text{本示例的第三行}
\end{multline}
```

#### 在等号处对齐的多行公式

```latex
\begin{align}
a &= c+d \\
b &= e+f
\end{align}
```

`align` 环境也可以同时在多个位置对齐：

```latex
\begin{align}
x &= y & X & =Y & a &=bc\\
x' &= y' & X' &=Y' &a' &=bz
\end{align}
```

### 9.4 子公式编号

`amsmath` 宏包提供 `subequations` 环境，以便为一组公式设置子编号。例如：

```latex
\begin{subequations}\label{eq:2}
\begin{align}
f&=g \label{eq:2A}\\
f' &=g' \label{eq:2B}\\
\mathcal{L}f &= \mathcal{L}g \label{eq:2c}
\end{align}
\end{subequations}
```

### 9.5 矩阵

LaTeX 提供了多种实用的矩阵环境，可以减少输入工作量：

- `matrix`：无定界符矩阵；
- `pmatrix`：圆括号矩阵；
- `bmatrix`：方括号矩阵；
- `Bmatrix`：花括号矩阵；
- `vmatrix`：单竖线矩阵，常用于行列式；
- `Vmatrix`：双竖线矩阵，常用于范数。

示例：

```latex
\begin{equation}
\begin{pmatrix}
0 & -i \\
i & 0
\end{pmatrix}
\end{equation}
```

将 `pmatrix` 分别替换成 `matrix`、`bmatrix`、`Bmatrix`、`vmatrix` 或 `Vmatrix`，即可获得原文展示的其他边界形式。

### 9.6 数组

`array` 环境可用于排版类似矩阵的公式。用户需要手动输入定界符，但可以灵活控制列对齐方式以及水平线和竖直线。`array` 的参数决定各列的对齐方式和竖线位置。

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

若要使最后一列数字右对齐，可把参数改为 `{cccr}`。若要加入竖线和横线，可使用：

```latex
\begin{equation}
\left(
\begin{array}{c|c|c|r}
a+b+c & uv & x-y & 27\\ \hline
a+b & u+v & z & 134
\end{array}\right)
\end{equation}
```

参数中的竖线符号 `|` 指定竖直分隔线的位置。

### 9.7 分段结构

分段公式经常被误用 `array` 环境排版。使用 `cases` 环境可以减少输入量——无需手动键入 `\left\lbrace`——并能自动给出正确的列对齐方式。

```latex
\begin{equation*}
{z_m(t)} =
\begin{cases}
1,&{\text{if}}\ {\beta}_m(t),\\
0,&{\text{otherwise.}}
\end{cases}
\end{equation*}
```

其中 `&` 用于标记表格式对齐位置，这对于正确的列对齐非常重要。不要试图使用 `\quad` 或其他固定空格来对齐各列。对于 `if`、`otherwise` 等文本元素，应使用 `\text` 宏。

### 9.8 公式中的函数格式

对大多数常见函数，只需在函数名之前加反斜杠，通常就能获得正确格式。如果这种方法不适用，可以像下面这样使用 `\text` 宏：

```latex
\begin{equation*}
d_{R}^{KM} = \underset {d_{l}^{KM}}
{\text{arg min}} \{d_{1}^{KM},\ldots,d_{6}^{KM}\}.
\end{equation*}
```

### 9.9 公式中的文本缩写

下面的示例使用 `\text{}` 排版缩写 `MSE`，使其外观与正文中的写法一致：

```latex
\begin{equation*}
\text{MSE} = \frac{1}{n}\sum_{i=1}^{n}
(Y_i-\hat{Y_i})^2
\end{equation*}
```

## 10. 结论

在此处撰写结论。

## 致谢

致谢应放在参考文献之前，并以一个简洁段落感谢为本文提供支持的个人和机构。

## 附录

原示例附录标题为“Zonklar 方程的证明”。附录命令的使用规则如下：

- 只有一个附录时使用 `\appendix`；
- 调用 `\appendix` 后不要再使用 `\section`，只使用 `\section*`；
- 有多个附录时使用 `\appendices`，随后使用 `\section` 开始每个附录；
- 在使用任何 `\subsection` 或 `\label` 之前，必须先声明一个 `\section`，因为单独的 `\appendices` 会启动一个编号为 0 的章节；
- 若不希望附录显示标题，可以把标题参数留空。

## 11. 参考文献部分

可以将 BibTeX 生成的参考文献作为 `.bbl` 文件使用。BibTeX 文档可从以下地址获取：

<http://mirror.ctan.org/biblio/bibtex/contrib/doc/>

IEEEtran 的 BibTeX 样式支持页面为：

<http://www.michaelshell.org/tex/ieeetran/bibtex/>

原文件给出的调用形式为：

```latex
% 参数为 BibTeX 字符串定义和参考文献数据库
\bibliography{IEEEabrv,../bib/paper}
```

## 12. 手工参考文献

也可以把生成的 `.bbl` 内容手动复制到主文件中。`thebibliography` 环境的参数用于为参考文献编号标签框预留空间，应根据参考文献编号的位数设置。

原文列出的参考资料如下。为保证可检索性和引文准确性，题名及出版信息保留原文：

1. *Mathematics Into Type*. American Mathematical Society. [Online]. Available: <https://www.ams.org/arc/styleguide/mit-2.pdf>
2. T. W. Chaundy, P. R. Barrett and C. Batey, *The Printing of Mathematics*. London, U.K.: Oxford Univ. Press, 1954.
3. F. Mittelbach and M. Goossens, *The LaTeX Companion*, 2nd ed. Boston, MA, USA: Pearson, 2004.
4. G. Grätzer, *More Math Into LaTeX*. New York, NY, USA: Springer, 2007.
5. M. Letourneau and J. W. Sharp, *AMS-StyleGuide-online.pdf*. American Mathematical Society, Providence, RI, USA. [Online]. Available: <http://www.ams.org/arc/styleguide/index.html>
6. H. Sira-Ramirez, “On the sliding mode control of nonlinear systems,” *Syst. Control Lett.*, vol. 19, pp. 303–312, 1992.
7. A. Levant, “Exact differentiation of signals with unbounded higher derivatives,” in *Proc. 45th IEEE Conf. Decis. Control*, San Diego, CA, USA, 2006, pp. 5585–5590. DOI: 10.1109/CDC.2006.377165.
8. M. Fliess, C. Join, and H. Sira-Ramirez, “Non-linear estimation is easy,” *Int. J. Model., Ident. Control*, vol. 4, no. 1, pp. 12–27, 2008.
9. R. Ortega, A. Astolfi, G. Bastin, and H. Rodriguez, “Stabilization of food-chain systems using a port-controlled Hamiltonian description,” in *Proc. Amer. Control Conf.*, Chicago, IL, USA, 2000, pp. 2245–2249.

## 13. 作者简介部分

如果作者照片为 EPS/PDF 格式，需要加载 `graphicx` 宏包。由于可选参数中的 `\includegraphics` 命令结构较复杂，必须在 biography 环境的可选参数内容外再加一层花括号，以免 LaTeX 解析器发生混淆。也可以自定义一个包含 `\includegraphics` 的宏，使这里的写法更简洁。

### 包含作者照片

```latex
\begin{IEEEbiography}
[{\includegraphics[width=1in,height=1.25in,clip,
keepaspectratio]{fig1}}]
{Michael Shell}
作者简介正文。
\end{IEEEbiography}
```

使用 `\begin{IEEEbiography}`。可选参数通过 `\includegraphics` 声明并链接作者照片，随后给出作者姓名和简介正文。

### 不包含作者照片

```latex
\begin{IEEEbiographynophoto}{John Doe}
作者简介正文。
\end{IEEEbiographynophoto}
```

使用 `\begin{IEEEbiographynophoto}`，将作者姓名作为参数，后面填写简介正文。

