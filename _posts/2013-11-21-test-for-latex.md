---
layout: post
title: "用MathJax解决Markdown公式编辑问题"
description: ""
category: 软件技术
tags: [markdown, latex, github-pages]
---
{% include JB/setup %}

之前不知道Markdown怎么支持LaTex，因为一直没有贴过公式，今天要用到时才觉得困难，好在看到了"[Jekyll使用MathJax来显示数学式]"。感谢作者Yukang！

使用很方便，首先是修改html头部，在每个页面开头加上这么一句，在Jekyll下只要修改layouts的default.html就好了	
	
	<script type="text/javascript"
 	src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
	</script>

然后是安装kramdown，因为rdiscount和默认的markdown在解析带公式文件的时候都会出现一些问题
	
	$ gem install kramdown

修改_config.yml
	
	markdown: kramdown

使用的时候，只要用`$$`把公式括起来就好咯，例如
	
	$$a^2 + b^2 = c^2$$

下面是一些例子

###The Lorentz Equations###

$$
\begin{aligned}
\dot{x} = \sigma(y-x) \\
\dot{y} = \rho x - y - xz \\
\dot{z} = -\beta z + xy
\end{aligned}
$$

###The Cauchy-Schwarz Inequality###

$$
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
$$

###A Cross Product Formula###

$$
\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix}
\mathbf{i} \mathbf{j} \mathbf{k} \\
\frac{\partial X}{\partial u} \frac{\partial Y}{\partial u} 0 \\
\frac{\partial X}{\partial v} \frac{\partial Y}{\partial v} 0
\end{vmatrix}
$$

###The probability of getting k heads when flipping n coins is###

$$
P(E)   = {n \choose k} p^k (1-p)^{ n-k}
$$

###An Identity of Ramanujan###

$$
\frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} =
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}}
{1+\frac{e^{-8\pi}} {1+\ldots} } } }
$$

###A Rogers-Ramanujan Identity###

$$
1 +  \frac{q^2}{(1-q)}+\frac{q^6}{(1-q)(1-q^2)}+\cdots =
\prod_{j=0}^{\infty}\frac{1}{(1-q^{5j+2})(1-q^{5j+3})},
\quad\quad \text{for $|q|<1$}.
$$

###Maxwell&rsquo;s Equations###

$$
\begin{aligned}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} = \frac{4\pi}{c}\vec{\mathbf{j}} \\
\nabla \cdot \vec{\mathbf{E}}  = 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} = \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} = 0 \end{aligned}
$$

使用过程不知道会不会有bug，日后有碰到再补上。
再次感谢Yukang。

[Jekyll使用MathJax来显示数学式]: http://cyukang.com/2013/03/03/try-mathjax.html