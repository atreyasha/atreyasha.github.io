---
layout: post
title:  "Derivation of the Cauchy-Riemann Equations"
description: Deriving Cauchy-Reimann Equations and proving limits via all complex paths for holomorphic functions
date:   2019-09-02 06:20:00 +0200
categories: [mathematics]
---

Recently, I had started exploring the concept of replacing the real-valued components of deep-learning networks with complex numbers instead. For this, the concept of holomorphic functions becomes important. It took me some time to find a complete and concise proof of complex-valued differentiability. Here I will summarize what holomorphic functions are, which will ultimately lead us to the `Cauchy-Riemann Equations`.

Firstly, in order for us to have a complete complex-differentiable function, we would need to show that a function $f(z)$ has a well-defined derivative $f'(z)$. We can define the derivate $f'(z)$ below:
 
\\[
f'(z)=\lim_{\delta z \rightarrow 0} \frac{f(z+\delta z)-f(z)}{\delta z}
\\]

In order for $f'(z)$ to be well-defined, the value of $f'(z)$ must be the same regardless of how we approach the limit. In this case, $\delta z$ can approach $0$ in many different ways. To investigate the different approaches, we can first redefine our complex function in terms of its real and "imaginary" parts:

<div>
$$
\begin{eqnarray}
&z \in \{x+iy~|~x,y \in \mathbb{R}, ~ i = \sqrt{-1}\} \\
\nonumber \\
&f(z)\in \{u(z)+iv(z)~|~ u,v \in \mathbb{R},~ i = \sqrt{-1}\} \\
\nonumber \\
&f(x,y) = u(x,y) + iv(x,y) \label{4}
\end{eqnarray}
$$
</div>

#### Approach 1: Via the real-axis

If we approach the limit via the real-axis, $\delta z \rightarrow 0$ will deform to $\delta x \rightarrow 0$.

<div>
$$
\begin{align}
f'(x,y)&=\lim_{\delta x \rightarrow 0} \frac{f(x+\delta x,y)-f(x,y)}{\delta x}\\
&=\lim_{\delta x \rightarrow 0} \frac{u(x+\delta x,y)+iv(x+\delta x,y)-u(x,y)-iv(x,y)}{\delta x} \nonumber\\
&=\lim_{\delta x \rightarrow 0} \frac{u(x+\delta x,y)-u(x,y)}{\delta x} + \lim_{\delta x \rightarrow 0} \frac{iv(x+\delta x,y)-iv(x,y)}{\delta x} \nonumber \\
&=\frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x} \nonumber
\end{align}
$$
</div>

#### Approach 2: Via the imaginary-axis

If we approach the limit via the imaginary-axis, $\delta z \rightarrow 0$ will deform to $\delta iy \rightarrow 0$.

<div>
$$
\begin{align}
f'(x,y)&=\lim_{\delta iy \rightarrow 0} \frac{f(x,y+\delta y)-f(x,y)}{\delta iy}\\
&=\lim_{\delta iy \rightarrow 0} \frac{u(x,y+\delta y)+iv(x,y+\delta y)-u(x,y)-iv(x,y)}{\delta iy} \nonumber\\
&=\lim_{\delta iy \rightarrow 0} \frac{u(x,y+\delta y)-u(x,y)}{\delta iy} + \lim_{\delta iy \rightarrow 0} \frac{iv(x,y+\delta y)-iv(x,y)}{\delta iy} \nonumber \\
&=\frac{1}{i}\frac{\partial u}{\partial y} + \frac{\partial v}{\partial y} \nonumber \\
&=-i\frac{\partial u}{\partial y} + \frac{\partial v}{\partial y} \nonumber \\
\end{align}
$$
</div>

#### Deductions

If the function $f$ is differentiable in complex space, both formulations of the differential (via the real and imaginary axes) must be the same. Therefore we apply the equality:

<div>
$$
\begin{align}
\frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x}
&= \frac{\partial v}{\partial y}-i\frac{\partial u}{\partial y}  \\
\nonumber \\
\frac{\partial u}{\partial x} =  \frac{\partial v}{\partial y},& \quad \frac{\partial v}{\partial x} = -\frac{\partial u}{\partial y} \quad \square
\end{align}
$$
</div>

And with that, we arrive at the `Cauchy-Riemann Equations`, which essentially define a natural constraint on the real and imaginary parts of complex functions in order for such a complex function to be complex-differentiable or `holomorphic`.

#### Additional investigation

One limitation of our proof is that we assumed that our only two approaches can be from the real or imaginary axes. But what about approaches from arbitrary diagonals or combinations of both axes?

To investigate such a possibility, we have to revisit our original definition in \eqref{4} and utilize what is called a complete differential. We also assume an arbitrary signal for $x$ and $y$ in $z$.

<div>
$$
\begin{eqnarray}
&f(x,y) = u(x,y) + iv(x,y) \\
\nonumber \\
&\delta u = \frac{\partial u}{\partial x} \delta x + \frac{\partial u}{\partial y}\delta y \\
\nonumber \\
&\delta v = \frac{\partial v}{\partial x} \delta x + \frac{\partial v}{\partial y}\delta y  \\
\nonumber \\
\end{eqnarray}
$$
</div>

With arbitrary proportions of $u$ and $v$, we can assume an arbitrary approach of $\delta z \rightarrow 0$.

<div>
$$
\begin{align}
\delta f = \delta u + i \delta v &= \frac{\partial u}{\partial x} \delta x + \frac{\partial u}{\partial y}\delta y + i \frac{\partial v}{\partial x} \delta x + i \frac{\partial v}{\partial y}\delta y \\
&= \Big(\frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} \Big)\delta x + \Big(\frac{\partial u}{\partial y} +  i \frac{\partial v}{\partial y}\Big) \delta y \nonumber \\ 
\text{Using CR-equations}:&= \Big(\frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} \Big)\delta x + \Big(-\frac{\partial v}{\partial x} +  i \frac{\partial u}{\partial x}\Big) \delta y \nonumber \\
&= \Big(\frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} \Big)\delta x + \Big(\frac{\partial u}{\partial x} + i\frac{\partial v}{\partial x}\Big) i\delta y \nonumber \\
&= \Big(\frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} \Big)\cdot(\delta x+i\delta y) \nonumber \\
&= \Big(\frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} \Big)\cdot \delta z \nonumber 
\end{align}
$$
</div>

Now, with the help of the CR-equations, we can find the derivative of $f$ with respect to an arbitrary $z$.

<div>
$$
\begin{align}
\lim_{\delta z \rightarrow 0} \frac{\delta f}{\delta z} &= \lim_{\delta z \rightarrow 0} \frac{\Big(\frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} \Big) \cdot \delta z }{\delta z} \label{13} \\
\nonumber\\
&= \frac{\partial u}{\partial x} + i \frac{\partial v}{\partial x} \nonumber \\
\text{Using CR-Equations}:&=\frac{\partial v}{\partial y}-i\frac{\partial u}{\partial y} \quad \blacksquare \nonumber 
\end{align}
$$
</div>

With \eqref{13}, we can show that as long as the `Cauchy-Riemann Equations` hold for a complex function, it will still be differentiable regardless of the complex path we take towards the specific limit. This would imply that investigating a complex function's differentiability via the real and imaginary axes individually is sufficient in proving complex differentiability everywhere (or through all paths).
