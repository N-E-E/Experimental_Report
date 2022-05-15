## 这是模板使用的一些说明。

### Order,Order! 本模板由陈加忠老师完成。为了方便同学赶完ddl特此做了一个二创版本。还是希望同学们认真学latex，少走捷径。

### 一些基础知识

1. 我们可以跳至“使用步骤“部分直接开始写作，碰到需要一点latex知识的地方再返回这里。

2. 基本的书写

   1. 文字书写：直接打字就完事了。但是注意，段前打空格是没有办法缩进的。如何缩进？每个section的第一段是自动缩进的，想要它不缩进，就在这段第一个字前输入`\noindent`；想要下一行缩进，就在本段结束出打上`\par`；想要下一段不缩进，打一个`\\`就可以(当然你也可以用`\noindent`)。建议自己摸索
   2. 图片书写：首先，图片存放位置很重要，建议直接放在images文件夹中并且按顺序起名。然后，为了方便我们的图片书写，可以直接调用命令：`\InsertSingleFigure{文件路径}{图片缩放尺寸，一般取0.5}{图名}`；如果想插入并排两张图片，使用命令`\ResultDoubleFigure{左边图片文件路径}{右边图片路径}{图名}`；想插入上下两张并排图，使用命令`\InsertDoubleFigure{上方图片路径}{下方图片路径}{图名}`。

3. 花里胡哨的部分：

   1. 伪代码：陈老师其实已经给出了，给个模板自己仿照写吧：

      ```latex
      \begin{shaded*}\begin{alg}{一个复杂算法}
      		\label{alg:1}
      		\begin{algorithmic}
      			\Input Two numbers $a$ and $b$
      			\Output The sum of $a$ and $b$
      			\Procedure{A-Plus-B}{$a, b$}
      			\If $a = 0$
      			\State \Return $b$
      			\EndIf
      			\State $res \gets 0$
      			\While{$b \neq 0$}
      			\State Increase $res$ by $1$
      			\State $b \gets b - 1$
      			\EndWhile
      			\State \Return $res$
      			\EndProcedure
      		\end{algorithmic}
      \end{alg}\end{shaded*}
      ```

      或者用这种:

      ```latex
      \begin{algorithm}[h] 
      	\caption{一个更复杂算法}
      	\begin{algorithmic}[1]
      		\State Initialization: $I_{xy}$, $z_{f}=Zeros(128, 128)$; 
      		\For{$0\leq n \textless N$}
      		\State $i=\lfloor x_n \rfloor+64$, $j=\lfloor y_n \rfloor + 64$
      		\If{$z_n<0$ and $|z_n|>|z_{f}(i,j)|$};
      		\State $z_{f}(i,j)=z_n$;
      		\EndIf
      		\State $I_{xy}(i,j)=z_{f}(i,j)$;
      		\EndFor 
      	\end{algorithmic}\label{alg:2}
      \end{algorithm}
      ```

   2. 交叉引用：当我们想写“如图xx”或者“如算法xx”的时候，xx处可以直接用交叉引用做到。方式就是在适当位置加上一个标签`\label{给这个标签取个名字}`，然后要引用的时候使用`\ref{你取的名字}`举个例子：

      ```latex
      如图\ref{fig:1},易证...
      \begin{figure}
      \centering
      \includegraphics{d:/高光时刻/五杀.jpg}
      \caption{五杀}
      \label{fig:1}
      \end{figure}
      ```

      这样就可以生成引用了。

4. 有啥不会问百度。

### 模板使用步骤

1. 首先打开文件”Experimental_Report.tex",找到源码中的`begin{document}`，从这里开始是正文环境。正文结束的地方会有一个`end{document}`。这个begin和end构成一个“环境”（latex有很多种环境，后面也提到几种常用到的环境）。我们只需要修改正文环境的内容就可以了。

1. 我们主要看源码，找到命令section{基于链式存储...}，哪里应该放什么东西我都写的很清楚了。如果没有说明，直接输入文字即可(基本的latex输入可以看基础知识的2部分）。
2. 往下看出现了一个enumerate环境，找猫画虎继续列出几个item即可。
3. 上面描述过程需要加其他一些花里胡哨的东西可以看基础知识3部分。
4. 跳到“系统测试”部分，这里涉及一个插入表格的问题，使用命令`TestTable{函数名}{正常数据}{是否通过}{异常数据}{是否通过}`就可以插入想我那样的一个表格。为了防止撞车，我稍微修改了样式。
5. 这样一个章节的报告就完成了。下面讲一下最后的部分
6. 文献引用我已经写好了，不用动。
7. 到了附录部分，打开"charpter1.tex",在我提示的地方放上代码就可以了。
8. 编译及运行：每写一部分就运行一下，看看有没有报错
9. 左边的那个符号是编译+构建。![image-20220515210538458](C:\Users\Mr.K\AppData\Roaming\Typora\typora-user-images\image-20220515210538458.png)

10. 给出了我的实验报告模板，可以对照一下。