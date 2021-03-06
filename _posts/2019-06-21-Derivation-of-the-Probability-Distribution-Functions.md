---
layout: post
title:  "Derivation of the Probability Distribution Functions"
date:   2019-06-21 23:00:00 +0900
author: Taeho Oh
tags: [ 오태호, 수학, 통계학, 확률분포 ]
---
안녕하세요. 오태호입니다.

통계학을 공부하다 보면 각종 확률분포함수(Probability Distribution Function)를 접하게 되는데 왜 이렇게 생긴 함수를 사용하는지 이해를 제대로 하지 못하고 사용하는 경우가 많이 있습니다. 통계를 잘 다루기 위해서는 각종 확률분포의 의미를 정확히 이해하는 것이 매우 중요합니다. 여기서는 각종 확률분포함수의 의미를 살펴보고 유도를 해 보도록 하겠습니다.

이해가 잘 되지 않는 확률분포함수가 있을 때 이 글을 읽어보면 이해하는데 도움을 줄 수 있을 것으로 생각합니다.

# Rademacher Distribution {#Rademacher}
* $-1$ 이 나올 확률이 $\frac{1}{2}$ 이고 $+1$ 이 나올 확률이 $\frac{1}{2}$ 입니다.
* $$
\begin{aligned}
&P_X(x) =
\begin{cases}
\frac{1}{2} & \text{ if } x=-1 \\
\frac{1}{2} & \text{ if } x=+1 \\
0 & \text{ otherwise }
\end{cases}
\end{aligned}
$$

# Bernoulli Distribution {#Bernoulli}
* $1$ 이 나올 확률이 $p$ 이고 $0$ 이 나올 확률이 $1-p$ 입니다.
* $X \sim Bernoulli(p)$
* $$
P_X(x)=
\begin{cases}
p & \text{ if } x=1 \\
1-p & \text{ if } x=0 \\
0 & \text{ otherwise }
\end{cases}
$$

# Geometric Distribution {#Geometric}
* $Bernoulli(p)$ 시도를 $x$ 번 할 때 $0$ 이 $x-1$ 번 나오고 $1$ 이 $x$ 번째에 나올 확률입니다.
* $X \sim Geometric(p)$
* $$
P_X(x)=
\begin{cases}
p(1-p)^{x-1} & \text{ if } x = 1, 2, 3, \cdots \\
0 & \text{ otherwise }
\end{cases}
$$

# Pascal Distribution {#Pascal}
* Negative Binomial Distribution이라고도 부릅니다.
* Pascal Distribution은 사용하는 사람마다 조금씩 다른 의미로 정의하는 경우가 많아서 주의가 필요합니다.
* Geometric Distribution의 일반형입니다.
* $Bernoulli(p)$ 시도를 $x$ 번 할 때 $x-1$ 번 시도할 때까지 $m-1$ 번 $1$ 이 나오고 $x$ 번째 시도에서 $m$ 번째 $1$ 이 나올 확률입니다.
* $X \sim Pascal(m,p)$
* $$
P_X(x)=
\begin{cases}
\binom{x-1}{m-1}p^m(1-p)^{x-m} & \text{ if } x = m, m+1, m+2, \cdots \\
0 & \text{ otherwise }
\end{cases}
$$

# Binomial Distribution {#Binomial}
* $Bernoulli(p)$ 시도를 $n$ 번 할 때 그중에 $1$ 이 $x$ 번 나올 확률입니다.
* $X \sim Binomial(n,p)$
* $$
P_X(x)=
\begin{cases}
\binom{n}{x}p^x(1-p)^{n-x} & \text{ if } x = 0, 1, 2, \cdots, n \\
0 & \text{ otherwise }
\end{cases}
$$

# Multinomial Distribution {#Multinomial}
* Binomial Distribution의 일반형입니다.
* $k$ 가지의 다른 색을 가지고 있는 공이 주머니에 있을 때 $1$ 번 색 공을 $x_1$ 개 뽑고, $2$ 번 색 공을 $x_2$ 개 뽑고, ..., $k$ 번 색 공을 $x_k$ 개 뽑을 확률입니다. 여기서 $i$ 번 색 공이 뽑힐 확률은 $p_i$ 이고, 총 뽑는 공의 갯수는 $n$ 개 이며, 공은 하나 뽑아서 색을 확인한 후 다시 주머니에 넣습니다.
* $(X_1, X_2, \cdots, X_k) \sim Multinomial(n, p_1, p_2, \cdots, p_k)$
* $$
P_{X_1, X_2, \cdots, X_k}(x_1, x_2, \cdots, x_k) =
\begin{cases}
\frac{n!}{x_1! x_2! \cdots x_k!}p_1^{x_1} p_2^{x_2} \cdots p_k^{x_k} & \text{ if } \sum_{i=1}^kx_i=n \\
0 & \text{ otherwise }
\end{cases}
$$

# Hypergeometric Distribution {#Hypergeometric}
* $b$ 개의 파란 공과 $r$ 개의 빨간 공이 주머니에 있을 때 $k$ 개의 공을 뽑았을 때 $x$ 개의 파란 공을 뽑을 확률입니다.
* $X \sim Hypergeometric(b,r,k)$
* $$
P_X(x)=
\begin{cases}
\frac{\binom{b}{x}\binom{r}{k-x}}{\binom{b+r}{k}} & \text{ if } \max(0, k-r) \leq x \leq \min(k, b) \\
0 & \text{ otherwise }
\end{cases}
$$

# Poisson Distribution {#Poisson}
* 한 달에 $\lambda$ 번의 고장이 평균적으로 발생하는 기계가 한 달 동안에 $x$ 번의 고장이 발생할 확률입니다.
* $X \sim Poisson(\lambda)$
* $$
P_X(x)=
\begin{cases}
\frac{e^{-\lambda}\lambda^x}{x!} & \text{ if } x=0,1,2,\cdots \\
0 & \text{ otherwise }
\end{cases}
$$

* 한 달을 $n$ 개의 구간으로 나누면 한 구간에 고장이 발생할 확률은 $\frac{\lambda}{n}$ 이 됩니다.
$X \sim Binomial(n, \frac{\lambda}{n})$ 에서 $n \to \infty$ 가 되면 $X \sim Poisson(\lambda)$ 이 됩니다.
    $$
\begin{aligned}
P_X(x)
&=\lim_{n \to \infty}\binom{n}{x}(\frac{\lambda}{n})^x(1-\frac{\lambda}{n})^{n-x} \\
&=\lambda^x\lim_{n \to \infty}\frac{n!}{x!(n-x)!}(\frac{1}{n^x})(1-\frac{\lambda}{n})^n(1-\frac{\lambda}{n})^{-x} \\
&=\frac{\lambda^x}{x!}\lim_{n \to \infty}\frac{n(n-1)\cdots(n-x+1)}{n^x}(1+(-\frac{\lambda}{n}))^{(-\frac{n}{\lambda})(-\lambda)}(1-\frac{\lambda}{n})^{-x} \\
&=\frac{\lambda^x}{x!} 1 \cdot e^{-\lambda} \cdot 1 \\
&=\frac{e^{-\lambda}\lambda^x}{x!}
\end{aligned}
$$

# Uniform Distribution {#Uniform}
* $a$ 와 $b$ 사이의 값이 균일한 확률로 $x$ 가 뽑힙니다.
* $X \sim Uniform(a,b)$
* $$
f_X(x)=
\begin{cases}
\frac{1}{b-a} & \text{ if } a \lt x \lt b \\
0 & \text{ otherwise }
\end{cases}
$$

# Exponential Distribution {#Exponential}
* 한 달에 $\lambda$ 번의 고장이 평균적으로 발생하는 기계가 $x$ 달 동안 기계가 고장이 나지 않았다가 $x$ 달 만에 기계가 고장이 날 확률밀도입니다.
* $X \sim Exponential(\lambda)$
* $$
f_X(x) =
\begin{cases}
\lambda e^{-\lambda x} & \text{ if } x \geq 0 \\
0 & \text{ if } x \lt 0
\end{cases}
$$
* $x$ 달 동안 기계가 고장이 나지 않을 확률은 Poisson Distribution을 이용해 계산해 보면 다음과 같습니다.
    $\frac{e^{-\lambda x}(\lambda x)^0}{0!}=e^{-\lambda x}$
* $x$ 달 동안 기계가 고장이 나지 않았다가 $x$ 달 이후에 기계가 고장이 날 확률은 다음과 같습니다.
    $F_X(x)=1-e^{-\lambda x}$
* $x$ 달 동안 기계가 고장이 나지 않았다가 $x$ 달 만에 기계가 고장이 날 확률밀도는 다음과 같습니다.
    $f_X(x)=\lambda e^{-\lambda x}$

# Laplace Distribution {#Laplace}
* Double Exponential Distribution이라고도 부릅니다.
한 달에 $\lambda$ 번의 고장이 평균적으로 발생하는 기계가 두 대 있을 때 첫 번째 기계가 고장나는데 걸리는 시간은 $X_1 \sim Exponential(\lambda)$ 달이고, 두 번째 기계가 고장나는데 걸리는 시간은 $X_2 \sim Exponential(\lambda)$ 달일 때, 두 기계가 고장나는데 걸리는 시간의 차는 $Y = X_1 - X_2 \sim Laplace(0, \frac{1}{\lambda})$ 가 됩니다.
* $X \sim Laplace(\mu, b)$
* $$f_X(x)=\frac{1}{2b}\exp(-\frac{\left | x - \mu \right |}{b})$$
* $X_1$ 과 $X_2$ 가 independent, $X_1 \sim Exponential(\lambda)$ , $X_2 \sim Exponential(\lambda)$ 이면 $Y=X_1-X_2 \sim Laplace(0, \frac{1}{\lambda})$ 임은 다음과 같이 증명합니다.
    $$
f_{X_1}(x_1)=\lambda e^{-\lambda x_1} \\
f_{X_2}(x_2)=\lambda e^{-\lambda x_2} \\
f_{X_1 X_2}(x_1, x_2)=\lambda^2 e^{-\lambda(x_1+x_2)} \\
\text{if } y \le 0 \\
\begin{aligned}
F_Y(y)
&=P(Y \le y) \\
&=P(X_1-X_2 \le y) \\
&=P(X_2 \ge X_1-y) \\
&=\int_0^\infty\int_{x_1-y}^\infty f_{X_1 X_2}(x_1,x_2)dx_2 dx_1 \\
&=\int_0^\infty\int_{x_1-y}^\infty \lambda^2 e^{-\lambda(x_1+x_2)}dx_2 dx_1 \\
&=\int_0^\infty \left [ \lambda^2 e^{-\lambda x_1}(-\frac{1}{\lambda}e^{-\lambda x_2}) \right ]_{x_1-y}^\infty dx_1 \\
&=\int_0^\infty \lambda e^{\lambda y}e^{-2\lambda x_1}dx_1 \\
&=\left [ \lambda e^{\lambda y}(-\frac{1}{2\lambda}e^{-2\lambda x_1}) \right ]_0^\infty \\
&=\lambda e^{\lambda y} \frac{1}{2 \lambda} \\
&=\frac{1}{2}e^{\lambda y}
\end{aligned} \\
f_Y(y)=\frac{1}{2}\lambda e^{\lambda y} \hspace{2em}(y \le 0) \\
\text{if } y > 0 \\
\begin{aligned}
F_Y(y)
&=P(Y \le y) \\
&=1-P(Y>y) \\
&=1-P(X_1-X_2>y) \\
&=1-P(X_2<X_1-y) \\
&=1-\int_y^\infty\int_0^{x_1-y} f_{X_1 X_2}(x_1,x_2)dx_2 dx_1 \\
&=1-\int_y^\infty\int_0^{x_1-y} \lambda^2 e^{-\lambda(x_1+x_2)}dx_2 dx_1 \\
&=1-\int_y^\infty \left [ \lambda^2 e^{-\lambda x_1}(-\frac{1}{\lambda}e^{-\lambda x_2}) \right ]_0^{x_1-y} dx_1 \\
&=1-\int_y^\infty(-\lambda e^{\lambda y}e^{-2\lambda x_1}+\lambda e^{-\lambda x_1})dx_1 \\
&=1-\left [ -\lambda e^{\lambda y}\frac{1}{-2 \lambda}e^{-2\lambda x_1}+\lambda\frac{1}{-\lambda}e^{-\lambda x_1}\right ]_y^\infty \\
&=1-\frac{1}{2}e^{-\lambda y}
\end{aligned} \\
f_Y(y)=\frac{1}{2}\lambda e^{-\lambda y} \hspace{2em}(y > 0) \\
f_Y(y)=\frac{1}{2}\lambda e^{-\lambda \left | y \right |}
$$

# Gamma Distribution {#Gamma}
* $\alpha$ 가 양의 정수인 경우 Erlang Distribution이라고도 부릅니다.
* Chi-squared Distribution, Exponential Distribution의 일반형입니다.
* 한 달에 $\lambda$ 번의 고장이 평균적으로 발생하는 기계가 $x$ 달 동안 기계가 $\alpha-1$ 번 고장이 나고 $x$ 달 만에 기계가 $\alpha$ 번째 고장이 날 확률밀도입니다.
* $X \sim Gamma(\alpha, \lambda)$
* $$
\Gamma(\alpha)=\int_0^\infty x^{\alpha-1}e^{-x}dx \\
f_X(x)=
\begin{cases}
\frac{\lambda^\alpha x^{\alpha-1}e^{-\lambda x}}{\Gamma(\alpha)} & \text{ if } x \gt 0 \\
0 & \text{ otherwise }
\end{cases}
$$

* $X_i$ 는 iid, $X_i \sim Exponential(\lambda)$ 일 때 $Y_\alpha = \sum_{i=1}^{\alpha}X_i \sim Gamma(\alpha, \lambda)$ 가 됨을 다음과 같이 증명합니다.
    $$
\begin{aligned}
M_{X_i}(s)
&=E(e^{sX_i})\\
&=\int_0^\infty \lambda e^{-\lambda x}e^{sx}dx \\
&=\int_0^\infty \lambda e^{-(\lambda-s)x}dx \\
&=\left[ -\frac{\lambda}{\lambda-s}e^{-(\lambda-s)x} \right]_0^\infty \\
&=\frac{\lambda}{\lambda-s}
\end{aligned} \\
\begin{aligned}
M_{Y_\alpha}(s)
&=(M_{X_i}(s))^\alpha \\
&=(\frac{\lambda}{\lambda-s})^\alpha
\end{aligned} \\
\begin{aligned}
\int_0^\infty f_{Y_\alpha}(x)e^{sx}dx
&=\int_0^\infty \frac{\lambda^\alpha x^{\alpha-1}e^{-\lambda x}e^{sx}}{\Gamma(\alpha)}dx \\
&=\frac{\lambda^\alpha}{\Gamma(\alpha)}\int_0^\infty x^{\alpha-1}e^{-(\lambda-s)x}dx \\
&=\frac{\lambda^\alpha}{\Gamma(\alpha)}\int_0^\infty x^{\alpha-1}e^{-tx}dx & \text{ } (t=\lambda-s) \\
&=\frac{\lambda^\alpha}{\Gamma(\alpha)}\frac{\Gamma(\alpha)}{t^\alpha} & \text{ } (\frac{\Gamma(\alpha)}{t^\alpha}=\int_0^\infty x^{\alpha-1}e^{-tx}dx) \\
&=(\frac{\lambda}{t})^\alpha \\
&=(\frac{\lambda}{\lambda-s})^\alpha \\
&=M_{Y_\alpha}(s)
\end{aligned}
$$

# Beta Distribution {#Beta}
* 은행에 가서 일을 처리하고 우체국에 가서 일을 처리할 때, 은행에서 앞에 기다리는 사람이 $a$ 명이고 우체국에서 앞에 기다리는 사람이 $b$ 명일 때 은행과 우체국에서 $1$ 시간당 평균 $\lambda$ 명을 처리하는 경우 은행에서 기다리는 시간은 $X \sim Gamma(a, \lambda)$ 이고 우체국에서 기다리는 시간은 $Y \sim Gamma(b, \lambda)$ 이 됩니다. 이때 총 기다린 시간은 $T=X+Y$ 가 되며 총 기다린 시간과 은행에서 기다린 시간의 비율은 $W=\frac{X}{X+Y}$ 가 됩니다. 이때 $T \sim Gamma(a+b, \lambda)$ 이고 $W \sim Beta(a, b)$ 가 됩니다.
* $X \sim Beta(a, b)$
* $$
\beta(a,b)=\frac{\Gamma(a)\Gamma(b)}{\Gamma(a+b)} \\
f_X(x)=\frac{x^{a-1}(1-x)^{b-1}}{\beta(a,b)}
$$
* $X \sim Gamma(a, \lambda)$ 이고 $Y \sim Gamma(b, \lambda)$ 일 때 $T=X+Y$ 과 $W=\frac{X}{X+Y}$ 의 Joint Distribution을 계산하여 $W \sim Beta(a, b)$ 임을 다음과 같이 증명합니다.
    $$
t=x+y \\
w=\frac{x}{x+y} \\
h_1(t,w)=x=tw \\
h_2(t,w)=y=t(1-w) \\
J
=\det
\begin{bmatrix}
\frac{\partial h_1}{\partial t} & \frac{\partial h_1}{\partial w} \\
\frac{\partial h_2}{\partial t} & \frac{\partial h_2}{\partial w}
\end{bmatrix}
=\det
\begin{bmatrix}
w & t \\
1-w & -t
\end{bmatrix}
=t \\
\begin{aligned}
f_{TW}(t,w)
&=f_{XY}(h_1(t,w),h_2(t,w)) \left | J \right | \\
&=f_X(x)f_Y(y)t \\
&=\frac{\lambda^a x^{a-1}e^{-\lambda x}}{\Gamma(a)}\frac{\lambda^b y^{b-1}e^{-\lambda y}}{\Gamma(b)}t \\
&=\frac{\lambda^a (tw)^{a-1}e^{-\lambda tw}}{\Gamma(a)}\frac{\lambda^b (t(1-w))^{b-1}e^{-\lambda t(1-w)}}{\Gamma(b)}t \\
&=\frac{w^{a-1}(1-w)^{b-1}\lambda^{a+b}t^{a+b-1}e^{-\lambda t}}{\Gamma(a)\Gamma(b)} \\
&=(\frac{\Gamma(a+b)}{\Gamma(a)\Gamma(b)}w^{a-1}(1-w)^{b-1})(\frac{1}{\Gamma(a+b)}\lambda^{a+b}t^{a+b-1}e^{-\lambda t}) \\
&=f_W(w)f_T(t)
\end{aligned} \\
T \sim Gamma(a+b, \lambda) \\
W \sim Beta(a, b)
$$

# Dirichlet Distribution {#Dirichlet}
* Multivariate Beta Distribution이라고도 부릅니다.
* Beta Distribution의 일반형입니다.
* $k$ 가지의 장소에 가서 각각 일을 처리할 때 $1$ 번 장소에서 $\alpha_1$ 명이 앞에서 기다리고 있고, $2$ 번 장소에서 $\alpha_2$ 명이 앞에서 기다리고 있고, ..., $k$ 번 장소에서 $\alpha_k$ 명이 앞에서 기다리고 있을 때 각각의 장소에서 $1$ 시간당 평균 $\lambda$ 명을 처리하는 경우 $1$ 번 장소에서 기다리는 시간은 $X_1 \sim Gamma(\alpha_1, \lambda)$ 이고, $2$ 번 장소에서 기다리는 시간은 $X_2 \sim Gamma(\alpha_2, \lambda)$ 이고, ..., $k$ 번 장소에서 기다리는 시간은 $X_k \sim Gamma(\alpha_k, \lambda)$ 이 됩니다. 이때 총 기다린 시간과 $1$ 번 장소에서 기다린 시간의 비율은 $Y_1=\frac{X_1}{\sum_{i=1}^k X_i}$ 이 되며, 총 기다린 시간과 $2$ 번 장소에서 기다린 시간의 비율은 $Y_2=\frac{X_2}{\sum_{i=1}^k X_i}$ 이 되며, ..., 총 기다린 시간과 $k$ 번 장소에서 기다린 시간의 비율은 $Y_k=\frac{X_k}{\sum_{i=1}^k X_i}$ 이 되며, $(Y_1, Y_2, \cdots, Y_k) \sim Dirichlet(\alpha_1, \alpha_2, \cdots, \alpha_k)$ 가 됩니다.
* $(X_1, X_2, \cdots, X_k) \sim Dirichlet(\alpha_1, \alpha_2, \cdots, \alpha_k)$
* $f_{X_1 X_2 \cdots X_k}(x_1, x_2, \cdots, x_k)=\frac{\Gamma(\sum_{i=1}^k \alpha_i)\prod_{i=1}^k x_i^{\alpha_i-1}}{\prod_{i=1}^k\Gamma(\alpha_i)}$

# Normal Distribution {#Normal}
* Gaussian Distribution이라고도 부릅니다.
* $X_i$ 가 iid, $E(X_i)=\mu$ , $Var(X_i)=\sigma^2$ , $\bar{X}=\frac{1}{n}\sum^n_{i=1}X_i$ 라고 하면, $E(\bar{X})=\mu$ , $Var(\bar{X})=\frac{\sigma^2}{n}$ 이 된다. $Z=\frac{\bar{X}-\mu}{\frac{\sigma}{\sqrt{n}}}$ 가 $n \to \infty$ 일 때, $Z \sim N(0, 1)$ 이 됩니다.
* $X_i$ 가 $E(X_i)$ , $Var(X_i)$ 가 존재하는 경우 $n$ 이 클 때 $Z$ 가 Normal Distribution을 따릅니다. $Poisson(n)$ 은 $Poisson(1)$ 의 합으로 나타낼 수 있고, $Gamma(n,\lambda)$ 는 $Exponential(\lambda)$ 의 합으로 나타낼 수 있으며, $Binomial(n,p)$ 는 $Bernoulli(p)$ 의 합으로 나타낼 수 있기 때문에, $n \to \infty$ 이면 $Poisson(n)$ , $Gamma(n,\lambda)$ , $Binomial(n,p)$ 가 Normal Distribution을 따릅니다. 이런 특성으로 인해 주변에서 Normal Distribution이 빈번하게 관측됩니다.
* $X \sim N(\mu, \sigma^2)$
* $f_X(x)=\frac{1}{\sigma\sqrt{2\pi}}\exp(-\frac{(x-\mu)^2}{2\sigma^2})$
* $Z \sim N(0, 1)$ , $X_i$ 가 iid, $E(X_i)=0$ , $Var(X_i)=1$ , $\bar{X}=\frac{1}{n}\sum^n_{i=1}X_i$ , $n \to \infty$ 일 때 $\sqrt{n}\bar{X} \sim N(0, 1)$ 임을 다음과 같이 증명합니다.
$$
\begin{aligned}
\int_{-\infty}^{\infty}f_Z(x)dx
&=\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}}\exp(-\frac{x^2}{2})dx \\
&=\frac{2}{\sqrt{2\pi}}\int_{0}^{\infty}\exp(-\frac{x^2}{2})dx \\
&=\frac{2}{\sqrt{2\pi}}\int_{0}^{\infty}\exp(-t)\frac{1}{\sqrt{2t}}dt & \text{ } (t=\frac{x^2}{2}) \\
&=\frac{1}{\sqrt{\pi}}\int_{0}^{\infty}t^{-\frac{1}{2}}\exp(-t)dt \\
&=\frac{1}{\sqrt{\pi}}\Gamma(\frac{1}{2}) \\
&=\frac{1}{\sqrt{\pi}}\sqrt{\pi} & \text{ } (\Gamma(\frac{1}{2})=\sqrt \pi)\\
&=1
\end{aligned} \\
\begin{aligned}
M_Z(s)
&=\int_{-\infty}^{\infty}f_Z(x)\exp(sx)dx \\
&=\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}}\exp(-\frac{x^2}{2})\exp(sx)dx \\
&=\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}}\exp(-\frac{x^2-2sx+s^2-s^2}{2})dx \\
&=\exp(\frac{s^2}{2})\int_{-\infty}^{\infty}\frac{1}{\sqrt{2\pi}}\exp(-\frac{(x-s)^2}{2})dx \\
&=\exp(\frac{s^2}{2})
\end{aligned} \\
M_{X_i}(s)=E(\exp(sX_i)) \\
M_{X_i}(0)=1 \\
M_{X_i}'(0)=0 \\
M_{X_i}''(0)=1 \\
\begin{aligned}
M_{\sqrt n\bar{X}}(s)
&=E(\exp(s\sqrt n \bar{X})) \\
&=E(\exp(s\sqrt n \frac{X_1+X_2+\cdots+X_n}{n})) \\
&=E(\exp(s\frac{X_1}{\sqrt n}))E(\exp(s\frac{X_2}{\sqrt n}))\cdots E(\exp(s\frac{X_n}{\sqrt n})) \\
&=(E(\exp(s\frac{X_i}{\sqrt n})))^n \\
&=(M_{X_i}(\frac{s}{\sqrt n}))^n
\end{aligned} \\
\begin{aligned}
\lim_{n \to \infty}\ln(M_{\sqrt n\bar{X}}(s))
&=\lim_{n \to \infty}\ln(M_{X_i}(\frac{s}{\sqrt n}))^n \\
&=\lim_{n \to \infty}n\ln(M_{X_i}(\frac{s}{\sqrt n})) \\
&=\lim_{y \to 0}\frac{\ln(M_{X_i}(sy))}{y^2} & \text{ } (y=\frac{1}{\sqrt n}) \\
&=\lim_{y \to 0}\frac{\frac{1}{M_{X_i}(sy)}M_{X_i}'(sy)s}{2y} & \text{ }(\text{L'Hopital's rule}) \\
&=\lim_{y \to 0}\frac{M'_{X_i}(sy)s}{2y} & \text{ } (M_{X_i}(0)=1) \\
&=\lim_{y \to 0}\frac{M''_{X_i}(sy)ss}{2} & \text{ } (\text{L'Hopital's rule}) \\
&=\frac{s^2}{2} & \text{ } (M_{X_i}''(0)=1)
\end{aligned} \\
M_{\sqrt n\bar{X}}(s)=\exp(\frac{s^2}{2}) \\
M_Z(s)=M_{\sqrt n\bar{X}}(s) \\
\sqrt n\bar{X} \sim N(0,1)
$$

# Chi-squared Distribution {#Chi-squared}
* $X_i$ 가 iid, $X_i \sim N(0, 1)$ , $Y=\sum_{i=1}^{n}X_i^2$ 이면 $Y \sim \chi_n^2$ 이 됩니다. $n$ 은 degree of freedom이라고 부릅니다.
* $X \sim \chi_n^2$
* $f_X(x)=\frac{(\frac{1}{2})^{\frac{n}{2}} x^{\frac{n}{2}-1}e^{-\frac{x}{2}}}{\Gamma(\frac{n}{2})}$
* $Y=X_i^2$ , $X_i \sim N(0,1)$ 이면 $Y \sim Gamma(\frac{1}{2},\frac{1}{2})$ 임을 다음과 같이 증명합니다.
    $$
f_Y(y)=2f_X(g^{-1}(y))\left | \frac{dg^{-1}(y)}{dy} \right | \\
g^{-1}(y)=\sqrt y \\
\frac{dg^{-1}(y)}{dy}=\frac{1}{2\sqrt y} \\
\begin{aligned}
f_Y(y)
&=2\frac{1}{\sqrt{2\pi}}e^{-\frac{y}{2}}\frac{1}{2\sqrt y} \\
&=\frac{1}{\sqrt{2\pi y}}e^{-\frac{y}{2}} \\
&=\frac{(\frac{1}{2})^{\frac{1}{2}} y^{-\frac{1}{2}}e^{-\frac{y}{2}}}{\Gamma(\frac{1}{2})}
\end{aligned} \\
Y \sim Gamma(\frac{1}{2},\frac{1}{2})
$$
* $X_i$ 가 iid, $X_i \sim N(0, 1)$ 이면 $X_i^2 \sim Gamma(\frac{1}{2},\frac{1}{2})$ 이 되고, $Y=\sum_{i=1}^n X_i^2$ 이면 $Y \sim Gamma(\frac{n}{2},\frac{1}{2})$ 가 되고, $Y \sim \chi_n^2$ 이 됩니다.

# Cauchy Distribution {#Cauchy}
* Lorentz Distribution이라고도 부릅니다.
* $X_1$ 과 $X_2$ 가 independent이고, $X_1 \sim N(0,1)$ , $X_2 \sim N(0,1)$ 일 때 $Y=\frac{X_1}{X_2}$ 라면 $Y \sim Cauchy(0,1)$ 이 됩니다.
* $E(Y)$ , $Var(Y)$ 가 존재하지 않습니다.
* $X \sim Cauchy(\mu,\sigma)$
* $f_X(x)=\frac{1}{\pi \sigma(1+(\frac{x-\mu}{\sigma})^2)}$
* $X_1$ 과 $X_2$ 가 independent이고, $X_1 \sim N(0,1)$ , $X_2 \sim N(0,1)$ 일 때 $Y=\frac{X_1}{X_2}$ 라면 $Y \sim Cauchy(0,1)$ 이 됨은 다음과 같이 증명합니다.
    $$
f_{X_1}(x_1)=\frac{1}{\sqrt{2\pi}}\exp(-\frac{x_1^2}{2}) \\
f_{X_2}(x_2)=\frac{1}{\sqrt{2\pi}}\exp(-\frac{x_2^2}{2}) \\
f_{X_1 X_2}(x_1,x_2)=\frac{1}{2\pi}\exp(-\frac{x_1^2+x_2^2}{2}) \\
y_1=g_1(x_1,x_2)=\frac{x_1}{x_2} \\
y_2=g_2(x_1,x_2)=x_2 \\
x_1=g_1^{-1}(y_1,y_2)=y_1 y_2 \\
x_2=g_2^{-1}(y_1,y_2)=y_2 \\
J
=\det
\begin{bmatrix}
\frac{\partial x_1}{\partial y_1} & \frac{\partial x_1}{\partial y_2} \\
\frac{\partial x_2}{\partial y_1} & \frac{\partial x_2}{\partial y_2}
\end{bmatrix}
=\det
\begin{bmatrix}
y_2 & y_1 \\
0 & 1
\end{bmatrix}
=y_2 \\
\begin{aligned}
f_{Y_1 Y_2}(y_1,y_2)
&=f_{X_1 X_2}(g_1^{-1}(y_1,y_2),g_2^{-1}(y_1,y_2)) \left | J \right | \\
&=\frac{1}{2\pi}\exp(-\frac{y_1^2 y_2^2+y_2^2}{2})\left | y_2 \right | \\
&=\frac{1}{2\pi}\exp(-\frac{y_2^2(y_1^2+1)}{2})\left | y_2 \right |
\end{aligned} \\
t=\frac{y_2^2(y_1^2+1)}{2} \\
\frac{dt}{dy_2}=y_2(y_1^2+1) \\
dy_2=\frac{1}{y_2(y_1^2+1)}dt \\
\begin{aligned}
f_{Y_1}(y_1)
&=\int_{-\infty}^{\infty}f_{Y_1 Y_2}(y_1, y_2)dy_2 \\
&=2\int_{0}^{\infty}f_{Y_1 Y_2}(y_1, y_2)dy_2 \\
&=2\frac{1}{2\pi}\int_{0}^{\infty}y_2\exp(-\frac{y_2^2(y_1^2+1)}{2})dy_2 \\
&=\frac{1}{\pi}\int_0^\infty y_2\exp(-t)\frac{1}{y_2(y_1^2+1)}dt \\
&=\frac{1}{\pi}\frac{1}{y_1^2+1}\int_0^\infty \exp(-t)dt \\
&=\frac{1}{\pi(y_1^2+1)}
\end{aligned}
$$

# F Distribution {#F}
* Snedecor's F Distribution이라고도 부르며, Fisher–Snedecor Distribution이라고도 부릅니다.
* $X_1$ 과 $X_2$ 가 independent이고, $X_1 \sim \chi_n^2$ , $X_2 \sim \chi_m^2$ , $Y=\frac{\frac{X_1}{n}}{\frac{X_2}{m}}$ 일 때 $Y \sim F(n,m)$ 입니다.
* $X \sim F(n,m)$
* $f_X(x)=\frac{(\frac{n}{m})^{\frac{n}{2}}x^{\frac{n}{2}-1}}{\beta(\frac{n}{2},\frac{m}{2})(\frac{n}{m}x+1)^{\frac{n+m}{2}}}$
* $X_1$ 과 $X_2$ 가 independent이고, $X_1 \sim \chi_n^2$ , $X_2 \sim \chi_m^2$ , $Y=\frac{\frac{X_1}{n}}{\frac{X_2}{m}}$ 일 때 $Y \sim F(n,m)$ 이 됨은 다음과 같이 증명합니다.
    $$
f_{X_1}(x_1)=\frac{(\frac{1}{2})^{\frac{n}{2}} x_1^{\frac{n}{2}-1}e^{-\frac{x_1}{2}}}{\Gamma(\frac{n}{2})} \\
f_{X_2}(x_2)=\frac{(\frac{1}{2})^{\frac{m}{2}} x_2^{\frac{m}{2}-1}e^{-\frac{x_2}{2}}}{\Gamma(\frac{m}{2})} \\
f_{X_1 X_2}(x_1,x_2)=\frac{(\frac{1}{2})^{\frac{n+m}{2}} x_1^{\frac{n}{2}-1}x_2^{\frac{m}{2}-1}e^{-\frac{x_1+x_2}{2}}}{\Gamma(\frac{n}{2})\Gamma(\frac{m}{2})} \\
y_1=g_1(x_1,x_2)=\frac{x_1}{x_2} \\
y_2=g_2(x_1,x_2)=x_1 \\
x_1=g_1^{-1}(y_1,y_2)=y_1 y_2 \\
x_2=g_2^{-1}(y_1,y_2)=y_2 \\
J
=\det
\begin{bmatrix}
\frac{\partial x_1}{\partial y_1} & \frac{\partial x_1}{\partial y_2} \\
\frac{\partial x_2}{\partial y_1} & \frac{\partial x_2}{\partial y_2}
\end{bmatrix}
=\det
\begin{bmatrix}
y_2 & y_1 \\
0 & 1
\end{bmatrix}
=y_2 \\
\begin{aligned}
f_{Y_1 Y_2}(y_1,y_2)
&=f_{X_1 X_2}(g_1^{-1}(y_1,y_2),g_2^{-1}(y_1,y_2)) \left | J \right | \\
&=\frac{(\frac{1}{2})^{\frac{n+m}{2}} y_1^{\frac{n}{2}-1}y_2^{\frac{n}{2}-1}y_2^{\frac{m}{2}-1}e^{-\frac{y_1 y_2+y_2}{2}}}{\Gamma(\frac{n}{2})\Gamma(\frac{m}{2})}\left | y_2 \right | \\
&=\frac{(\frac{1}{2})^{\frac{n+m}{2}} y_1^{\frac{n}{2}-1}y_2^{\frac{n+m}{2}-1}e^{-\frac{y_2(y_1+1)}{2}}}{\Gamma(\frac{n}{2})\Gamma(\frac{m}{2})}
\end{aligned} \\
\begin{aligned}
f_{Y_1}(y_1)
&=\int_0^\infty \frac{(\frac{1}{2})^{\frac{n+m}{2}} y_1^{\frac{n}{2}-1}y_2^{\frac{n+m}{2}-1}e^{-\frac{y_2(y_1+1)}{2}}}{\Gamma(\frac{n}{2})\Gamma(\frac{m}{2})} dy_2 \\
&=\frac{(\frac{1}{2})^{\frac{n+m}{2}} y_1^{\frac{n}{2}-1}}{\Gamma(\frac{n}{2})\Gamma(\frac{m}{2})}\int_0^\infty (\frac{2t}{y_1+1})^{\frac{n+m}{2}-1}e^{-t}\frac{2}{y_1+1}dt & \text{ } (t=\frac{y_2(y_1+1)}{2}) \\
&=\frac{(\frac{1}{2})^{\frac{n+m}{2}} y_1^{\frac{n}{2}-1}}{\Gamma(\frac{n}{2})\Gamma(\frac{m}{2})}(\frac{2}{y_1+1})^{\frac{n+m}{2}}\int_0^\infty t^{\frac{n+m}{2}-1}e^{-t}dt \\
&=\frac{y_1^{\frac{n}{2}-1}}{\Gamma(\frac{n}{2})\Gamma(\frac{m}{2})(y_1+1)^{\frac{n+m}{2}}}\Gamma(\frac{n+m}{2}) \\
\end{aligned} \\
y=h(y_1)=\frac{m}{n}y_1 \\
y_1=h^{-1}(y)=\frac{n}{m}y \\
\begin{aligned}
f_Y(y)
&=f_{Y_1}(h^{-1}(y))\left | \frac{dy_1}{dy} \right | \\
&=f_{Y_1}(\frac{n}{m}y)\left | \frac{n}{m} \right | \\
&=\frac{\frac{n}{m}\Gamma(\frac{n+m}{2})(\frac{n}{m}y)^{\frac{n}{2}-1}}{\Gamma(\frac{n}{2})\Gamma(\frac{m}{2})(\frac{n}{m}y+1)^{\frac{n+m}{2}}} \\
&=\frac{(\frac{n}{m})^{\frac{n}{2}}y^{\frac{n}{2}-1}}{\beta(\frac{n}{2},\frac{m}{2})(\frac{n}{m}y+1)^{\frac{n+m}{2}}} \\
\end{aligned} \\
Y \sim F(n,m)
$$

# t Distribution {#t}
* Student's t Distribution이라고도 부릅니다.
$X_i$ 는 iid, $X_i \sim N(\mu,\sigma^2)$ , $\bar{X}=\frac{1}{n}\sum_{i=1}^n X_i$ , $s^2=\frac{1}{n-1}\sum_{i=1}^n(X_i-\bar{X})^2$ 일 때 $Z=\frac{\bar{X}-\mu}{\frac{\sigma}{\sqrt n}} \sim N(0,1)$ , $T=\frac{\bar{X}-\mu}{\frac{s}{\sqrt n}} \sim t_{n-1}$ 입니다. $n-1$ 은 degree of freedom이라고 부릅니다.
* 정확한 $\sigma^2$ 를 구하는 것이 불가능한 경우에 $s^2$ 로 근사를 하게 되는데, $n$ 이 충분히 크다면 $s^2$ 가 $\sigma^2$ 와 거의 비슷하게 근사가 돼서 Normal Distribution을 사용할 수 있지만, $n$ 이 충분히 크지 않다면 $s^2$ 가 $\sigma^2$ 와 차이가 크게 돼서 t Distribution을 사용해야 합니다.
* $X \sim t_n$
* $f_X(x)=\frac{\Gamma(\frac{n+1}{2})}{\sqrt {n\pi}\Gamma(\frac{n}{2})(\frac{x^2}{n}+1)^{\frac{n+1}{2}}}$
* $X_i$ 는 iid, $X_i \sim N(\mu,\sigma^2)$ , $\bar{X}=\frac{1}{n}\sum_{i=1}^n X_i$ , $s^2=\frac{1}{n-1}\sum_{i=1}^n(X_i-\bar{X})^2$ 일 때 $Z=\frac{\bar{X}-\mu}{\frac{\sigma}{\sqrt n}} \sim N(0,1)$ , $T=\frac{\bar{X}-\mu}{\frac{s}{\sqrt n}} \sim t_{n-1}$ 임은 다음과 같이 증명합니다.
    $$
\begin{aligned}
T^2
&=\frac{(\bar{X}-\mu)^2}{\frac{s^2}{n}} \\
&=\frac{(\bar{X}-\mu)^2\frac{n}{\sigma^2}}{\frac{s^2}{n}\frac{n}{\sigma^2}} \\
&=\frac{\frac{(\bar{X}-\mu)^2}{\frac{\sigma^2}{n}}}{\frac{s^2}{\sigma^2}\frac{n-1}{n-1}} \\
&=\frac{\frac{Z^2}{1}}{\frac{(n-1)\frac{s^2}{\sigma^2}}{n-1}}
\end{aligned} \\
Z^2 \sim \chi_1^2 \\
(n-1)\frac{s^2}{\sigma^2} \sim \chi_{n-1}^2 \\
T^2 \sim F(1,n-1) \\
\begin{aligned}
F_{T^2}(u)
&=P(T^2 \lt u) \\
&=P(-\sqrt u \lt T \lt \sqrt u) \\
&=F_T(\sqrt u) - F_T(-\sqrt u)
\end{aligned} \\
\begin{aligned}
f_{T^2}(u)
&=\frac{1}{2\sqrt u}(f_T(\sqrt u)+f_T(-\sqrt u)) \\
&=\frac{1}{\sqrt u}f_T(\sqrt u)
\end{aligned} \\
f_{T^2}(t^2)=\frac{1}{\left | t \right |}f_T(t) \hspace{2em} (u=t^2) \\
\begin{aligned}
f_T(t)
&=\left | t \right |f_{T^2}(t^2) \\
&=(t^2)^{\frac{1}{2}}\frac{(\frac{1}{n-1})^{\frac{1}{2}}(t^2)^{\frac{1}{2}-1}}{\beta(\frac{1}{2}, \frac{n-1}{2})(\frac{1}{n-1}t^2+1)^\frac{n}{2}} \\
&=(t^2)^{\frac{1}{2}}\frac{\Gamma(\frac{n}{2})(\frac{1}{n-1})^{\frac{1}{2}}(t^2)^{\frac{1}{2}-1}}{\Gamma(\frac{1}{2})\Gamma(\frac{n-1}{2})(\frac{1}{n-1}t^2+1)^\frac{n}{2}} \\
&=\frac{\Gamma(\frac{n}{2})}{\sqrt \pi \sqrt{n-1}\Gamma(\frac{n-1}{2})(\frac{t^2}{n-1}+1)^\frac{n}{2}}
\end{aligned}
$$
* $(n-1)\frac{s^2}{\sigma^2} \sim \chi_{n-1}^2$ 의 증명은 [Sample Mean and Sample Variance](/techblog/Sample-Mean-and-Sample-Variance#Sample-Variance-and-Normal-Distribution)를 참조하시기 바랍니다.
