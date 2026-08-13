# 不定积分
##### 8.13
## 两个基本概念

原函数： $F'(x)=f(x)$

不定积分：$\int f(x)\,dx=F(x)+C$

## 原函数的存在性

若$f(x)在I$上连续，则$f(x)$在区间$I$上必有原函数

若$f(x)$在区间$I$上有第一类间断点，则$f(x)$在区间$I$上没有原函数

## 不定积分的性质

$(\int f(x)\,dx)'=f(x),\quad d\int f(x)dx=f(x)dx$

$\int f'(x)\,dx=f(x)+C,\quad \int d\,f(x)=f(x)+C$

$\int kf(x)\,dx=k\int f(x)dx$

$\int[f(x)±g(x)]dx=\int f(x)dx ± \int g(x)dx$

## 基本积分公式

![[基本积分公式]]

## 三种主要积分法

### 第一类换元法（凑微分法）

若$\int f(u)du=F(u)+C$，且$\varphi(x)$可导，则$\int f(\varphi(x))\varphi'(x)dx=\int f(\varphi(x))d\varphi(x)=F(\varphi(x))+C$

### 第二类换元法

设函数$x=\varphi(t)$可导，且$\varphi'(t)\neq0$，又设$\int f(\varphi(t))\varphi'(t)dt=F(t)+C$则
$$
\int f(x)dx=\int f(\varphi(t))\varphi'(t))dt=F(\varphi^{-1}(x))+C
$$
常用代换：
 1. $\sqrt{a^2 -x^2},x=a\sin t(a\cos t)$
 2. $\sqrt{a^2 +x^2},x=a\tan t$
 3. $\sqrt{x^2 -a^2},x=a\sec t$

### 分部积分法

设$u(x),v(x)$都有一阶连续导数，则
$$
\int udv=uv-\int vdu
$$
**注**：
 1. 适用于**两类不同函数相乘**
 2. 适用于$\int vdu比\int udv$好积
     - 多项式×指数，先把指数凑进去；三角×多项式，先把三角凑进去
     - 多项式×$\ln x,\arctan x,\arcsin x$，先把多项式凑进去
     - 指数×三角，凑谁都行，但是需要做两次，还原

注：$\int e^{-x^2}dx,\int \dfrac{\sin x}{x},\int \dfrac{\cos x}{x}$，积不出

## 三类常见可积函数积分

**有理函数积分**： $\int R(x)\,dx$ 
 - 一般法（部分分式法）
 - 特殊方法（加项减项或凑微分降幂）

**三角有理式积分**：$\int R(\sin x,\cos x)dx$
 - 一般方法（万能代换） 令$\tan\dfrac{x}{2}=t$
    - 这样原积分变为：$\int R(\sin x,\cos x)dx=\int R(\dfrac{2t}{1+t^2},\dfrac{1-t^2}{1+t^2})\dfrac{2}{1+t^2}dt$
 - 特殊方法（三角变形，换元，分布）
    1. 若$R(-\sin x,\cos x)=-R(\sin x,\cos x)$，则令$u=\cos x$
    2. 若$R(\sin x,-\cos x)=-R(\sin x,\cos x)$，则令$u=\sin x$
    3. 若$R(-\sin x,-\cos x)=R(\sin x,\cos x)$，则令$u=\tan x$

**简单无理函数积分**：$\int R(x,\sqrt[n]{\frac{ax+b}{cx+d}})$
 - 令$\sqrt[n]{\frac{ax+b}{cx+d}}=t$换元

# 不定积分常考题型方法

## 题型1 计算不定积分


## 题型2 不定积分杂例

# 定积分

## 概念

分、匀、和、精
$$
\int^b_af(x)\,dx=^\Delta \lim_{\lambda\to0}\sum_{k=1}^nf(\xi_k)\Delta x_k
$$
注：
 1. 定积分是一个数，所以与积分变量无关，即$\int^b_af(x)dx=\int^b_af(t)dt$
 2. 若$\int^1_0f(x)\,dx= \lim_{\lambda\to0}\sum_{i=1}^nf(\xi_i)\Delta x_i=\lim_{n\to\infty}\frac{1}{n}\sum^n_{i=1}f(\dfrac{i}{n})$

## 几何意义

若$f(x)\geq 0,\int^b_af(x)dx$的值等于以曲线$y=f(x),x=a,x=b$及x轴围成的曲边梯形面积
 - 若$f(x)\leq0$，则表示曲边梯形面积的负值
 - 若有正有负，则表示在x轴**上方**曲边梯形的面积==减去==**下方**曲边梯形的面积

## 定积分的存在性

**必要条件**：$f(x)$有界，即$f(x)在[a,b]$有界
 - 可积$\rightarrow$有界，有界$\nrightarrow$可积

**充分条件**：
 1. $f(x)$在$[a,b]$连续
 2. $f(x)$在$[a,b]$有界且只有有限个间断点
 3. $f(x)$在$[a,b]$仅有有限个第一类间断点

## 定积分的计算

### 牛顿-莱布尼茨公式

若F(x)是连续函数f(x)在区间$[a,b]$上的一个原函数，则
$$
\int^b_af(x)dx=F(b)-F(a)
$$
### 换元积分法

作变量代换，即：
$$
\int^b_af(x)dx=\int^{\alpha}_{\beta}f(\varphi(t))\varphi'(t)dt
$$
### 分部积分法

与不定积分类似，即：
$$
\int^b_audv=uv\Bigg|^v_a-\int^b_avdu
$$
### 利用奇偶性及周期性

$$
\int^{a}_{-a}f(x)dx=\left\{
\begin{matrix}
0,f(x)为奇函数\\\\
2\int^a_0f(x)dx,f(x)为偶函数
\end{matrix}
\right.
$$
$$
\int^{a+T}_af(x)dx=\int^T_0f(x)dx
$$
### 利用公式

$$
\int^{\dfrac{\pi}{2}}_0\sin^nxdx=\int^{\dfrac{\pi}{2}}_0\cos^nxdx=
\left\{
\begin{matrix}
\dfrac{n-1}{n}·\dfrac{n-3}{n-2}·...·\dfrac{1}{2}·\dfrac{\pi}{2},n为奇数\\\\
\dfrac{n-1}{n}·\dfrac{n-3}{n-2}·...·\dfrac{2}{3},n为偶数
\end{matrix}
\right.
$$

$$
\int^{\pi}{0}f(\sin x)\,dx=\dfrac{\pi}{2}\int^{\pi}_{0}f(\sin x)\,dx
$$

## 变上限积分及其应用

若$f(x)在[a,b]$连续，则$\int^b_af(t)dt在[a,b]$可导且
$$
(\int^x_af(t)\,dt)'=f(x)
$$
**公式**：**1**，2，3中只有**1**重要
 1. .$(\int^{\psi(x)}_{\varphi(x)}f(t)\,dt)'=f(\psi(x))\psi'(x)-f(\varphi(x))\varphi'(x)$
 2. .$(\int^{\psi(x)}_{\varphi(x)}f(x,t)\,dt)'=\int^{\psi(x)}_{\varphi(x)}\dfrac{\partial f(x,t)}{\partial x}\,dt+f(\psi(x))\psi'(x)-f(\varphi(x))\varphi'(x)$
 3. .$(\int^{b}_{a}f(x,t)\,dt)'=\int^{b}_{a}\dfrac{\partial f(x,t)}{\partial x}\,dt$

## 定积分性质

### 不等式

（1）若$f(x)\leq g(x)$，则$$\int^b_af(x)dx\leq \int^b_ag(x)dx$$

（2）若$f(x)在[a,b]$上连续，则
$$
m(b-a)\leq \int^b_af(x)dx \leq M(b-a)
$$
（3）积分的绝对值小于绝对值的积分
$$
\Big|\int^b_af(x)dx\Big|\leq \int^b_a\big|f(x)\big|dx
$$

### 积分中值定理

==（1）==若$f(x)在[a,b]$连续，则
$$
\int^b_af(x)dx=f(c)(b-a),\,a<c<b
$$
（2）若$f(x),g(x)在[a,b]$连续，$g(x)$不变号，则（广义积分中值定理）
$$
\int^b_af(x)g(x)dx=f(c)\int^b_ag(x)dx,\, a\leq c\leq b
$$

# 定积分常考题型方法

## 题型1 定积分的概念、性质及几何意义

定积分使用几何意义求解问题时，<span style="color:red;font-weight:bold;">一定要保证上限大，下限小</span>

## 题型2 定积分计算

根据题目选择之前的五个方法
 1. 牛顿莱布尼兹公式
 2. 换元积分法
 3. 分部积分法
 4. 利用奇偶性及周期性
 5. 利用公式

常见的积分式：（圆的积分）
 1. .$\int^a_0\sqrt{a^2-x^2}\,dx=\dfrac{\pi}{4}a^2$（1/4圆）
 2. .$\int^a_0\sqrt{2ax-x^2}\,dx=\dfrac{\pi}{4}a^2$（1/4偏心圆）
 3. .$\int^{2a}_0\sqrt{2ax-x^2}\,dx=\dfrac{\pi}{2}a^2$（偏心半圆）

三角函数n次方化简公式：
$$
\begin{matrix}
\int^\pi_0\sin^n xdx= 2\int^{\frac{\pi}{2}}_0\sin^n xdx\\\\
\int^\pi_0\cos^n xdx=
\left\{
\begin{matrix}
0,n为奇数\\\\
2\int^{\frac{\pi}{2}}_0\cos^n xdx,n为偶数
\end{matrix}
\right.\\\\
\int^{2\pi}_0\cos^n xdx=\int^{2\pi}_0\sin^n xdx
\left\{
\begin{matrix}
0,n为奇数\\\\
4\int^{\frac{\pi}{2}}_0\sin^n xdx,n为偶数
\end{matrix}
\right.
\end{matrix}
$$

形如$\int \dfrac{a\sin x+b\cos x}{c\sin x+d\cos x}dx$的化简
$$
\begin{matrix}
\int \dfrac{a\sin x+b\cos x}{c\sin x+d\cos x}dx=\int\dfrac{A(c\cos x-d\sin x)+B(c\sin x+d\cos x)}{c\sin x+d\cos x}\\\\
求解
\left\{
\begin{matrix}
a=Bc-Ad\\
b=Bd+Ac
\end{matrix}
\right.\,，得出A，B\\\\
A系数之后的为c\sin x+d\cos x的导数，凑微分，B系数之后可直接化简
\end{matrix}
$$

## 变上限函数积分及其应用

**连续性**：设$f(x)在[a,b]$上可积，则$\int^x_af(t)\,dt在[a,b]$上连续

<span style="color:red;font-weight:bold;">可导性</span>：
**定理**：设$f(x)在[a,b]$上可导，则$\int^x_af(t)\,dt在[a,b]$上可导且$(\int^x_af(t)\,dt)'=f(x)$

==**有关$F(x)=\int^x_af(t)\,dt$在一点处的可导性的结论**==

如果$f(x)在[a,b]$除点$x=x_0\in(a,b)$外均连续，则在点$x_0$处

| $f(x)$ |               | $F(x)=\int^x_af(t)\,dt$                         |
| ------ | ------------- | ----------------------------------------------- |
| 连续     | $\rightarrow$ | 可导，且$F'(x_0)=f(x_0)$                            |
| 可去间断点  | $\rightarrow$ | 可导，且$F'(x_0)=\lim_{x\to x_0}f(x)$               |
| 跳跃间断点  | $\rightarrow$ | 连续但不可导，且$F'_-(x_0)=f(x_0^-),F'_+(x_0)=f(x_0^+)$ |

**奇偶性**：设$f(x)$连续，则
 1. 若$f(x)$为**奇**函数，则$\int^x_af(t)\,dt$为==偶函数==
 2. 若$f(x)$为**偶**函数，则$\int^x_0f(t)\,dt$为==奇函数==（ **下限是0！！** ）





$$
\left\{
\begin{matrix}
\end{matrix}
\right.
$$