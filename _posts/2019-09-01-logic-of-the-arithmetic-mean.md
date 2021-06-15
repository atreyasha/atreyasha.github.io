---
layout: post
title:  "Alternative Formulation of the Arithmetic Mean"
description: Reformulating the derivation of the arithmetic mean formula
date:   2019-09-01 06:20:00 +0200
categories: [mathematics]
---

In the field of statistics, central tendency is a critical concept. Central tendency is basically a value or number around which quantitative data, or sets of data, tend to cluster. Central tendency can also be thought of as a number, or a set of numbers, that conveniently and accurately describes a set of data. There are many measures of central tendency. One simple and commonly used measure is the arithmetic mean. For a set of data (numbers) \\(a_1,a_2...a_n\\), the arithmetic mean \\((\overline{a})\\) is given by the following formula:

\\[
\begin{equation} 
  \overline{a} =\frac{a_1+a_2+...+a_n}{n}=\frac{\sum_{i=1}^{n}a_i}{n}
\end{equation}
\\]

A standard formulation of the arithmetic mean can result from expanding this formula. Here, the arithmetic mean can be defined as a weighted sum of the individual data instances, where each data instance receives an equal weight \\((\frac{1}{n})\\):

\\[
\begin{equation}
  \overline{a} =\frac{a_1+a_2+...+a_n}{n}=\frac{1}{n}\cdot{a_1}+\frac{1}{n}\cdot{a_2}+...+\frac{1}{n}\cdot{a_n}
\end{equation}
\\]

However, I believe that this formulation hides the actual concept of central tendency. For this reason, I want to present a reformulation of the arithmetic mean; one that clearly reflects the concept of central tendency. To start off, assume there exists some arbitrary sample of numerical data with natural number indices from \\(1\\) to \\(n\\):

<p align="center">
   <img src="/assets/img/arithmetic_mean_distribution.png" width="40%" />
</p>

Now, assume a central tendency value or an arithmetic mean for this sample exists, and it, being the central value, exists such that the absolute sum of the positive deviations and the sum of the negative deviations from it must be exactly the same. To put this more mathematically, the arbitrary data set will need some re-arrangement. The data that is greater than or equal to the arithmetic mean (assuming it exists) must be separated from the data that is less than the arithmetic mean in the following manner:

<div>
$$
\begin{align*}  
    &a_{1},a_{2},a_{3}...a_s\geq \overline{a} \\
    &a_{s+1},a_{s+2},a_{s+3}...a_n < \overline{a}
\end{align*}
$$
</div>

Now for the mathematical statement regarding the arithmetic mean:

<div>
$$
\begin{eqnarray} 
&\sum_{i=1}^{s}|a_i-\overline{a}|-\sum_{i=s+1}^{n}|a_i-\overline{a}| = 0 \\ \nonumber \\
&(a_1-\overline{a})+(a_2-\overline{a})+(a_3-\overline{a})+...+(a_s-\overline{a}) \\
&-(\overline{a}-a_{s+1})-(\overline{a}-a_{s+2})-(\overline{a}-a_{s+3})-...-(\overline{a}-a_n)=0 \nonumber
\end{eqnarray}
$$
</div>

Re-arranging the terms:

<div>
$$
\begin{align}
&a_1+a_2+...+a_n-n\cdot\overline{a}=0 \\\nonumber\\ 
&n\cdot\overline{a}=a_1+a_2+...+a_n \\\nonumber\\ 
&\overline{a} = \frac{a_1+a_2+...+a_n}{n} \quad \square
\end{align}
$$
</div>
