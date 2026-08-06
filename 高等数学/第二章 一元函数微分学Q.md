# 导数与微分

##### 8.6

## 导数概念

$$
f^{'}(x)=\lim_{\Delta x\to0}\dfrac{f(x_0+\Delta x)-f(x_0)}{\Delta x}=\lim_{x\to x_0}\dfrac{f(x)-f(x_0)}{x}
$$
*注意*：
 1. $\lim_{x\to x_0}f(x)与f(x_0)$**无关**
 2. $f^{'}(x_0)与f(x_0)$**有关**

**定理**：可导 $\Leftrightarrow$ 左右导数都存在且相等
 - 一般用于分段函数分界点

## 微分的概念

若$\Delta y=f(x_0+\Delta x)-f(x_0)=A\Delta x+o(\Delta x)$，则称$f(x)$在$x_0$处**可微**，称$A\Delta x$**为微分**，记为$dy=A\Delta x$
- $A\Delta x$是x的线性函数
- 微分是函数改变量的线性主部

**定理**：函数$y=f(x)$在$x_0$处**可微**的==充分必要条件==是$f(x)$在点$x_0$处**可导**，且有$dy=f^{'}(x_0)\Delta x=f^{'}(x_0)dx$

## 导数与微分的几何意义

**导数** $f^{'}(x_0)=\tan\alpha$，就是函数在对应点的**切线斜率**

**微分** $dy=f^{'}(x_0)dx$  **切线上的增量**

$\Delta y\approx dy$

## 连续、可导、可微的关系

**关系**：
 - 连续 $\nRightarrow$ 可导（|x|），可导 $\Rightarrow$ 连续
 - 可导 $\Leftrightarrow$ 可微
 - 连续 $\nRightarrow$ 可微，可微 $\Rightarrow$ 连续

**重点**：
 - 可导 $\Rightarrow f(x)$连续
 - 可导 $\nRightarrow f^{'}(x)$连续
 - 可导 $\nRightarrow \lim_{x\to x_0}f^{'}(x)$存在
**经典反例**：$\left\{\begin{matrix}x^2\sin\frac{1}{x},x\neq0\\0,x=0\end{matrix}\right.$ 处处**可导**，但$\lim_{x\to 0}f^{'}(x)$不存在

| 条件           | 使用洛必达最多用到    |
| ------------ | ------------ |
| $f(x)$n阶可导   | $f^{n-1}(x)$ |
| $f(x)$n阶连续可导 | $f^{n}(x)$   |

## 求导公式

![[常用求导公式]]

## 求导法则

### 有理运算法则

**求导法则**：
 1. $(u ±v)'=u'±v'$
 2. $(uv)'=u'v+uv'$
 3. $(\dfrac{u}{v})'=\dfrac{u'v-uv'}{v^2}(v\neq0)$

### 复合函数求导

设$u=\varphi(x),y=f(u)$可导，则$y=f[\varphi(x)]$
$$
\dfrac{dy}{dx}=\dfrac{dy}{du}·\dfrac{du}{dx}=f'(u)\varphi'(x)
$$

### 隐函数求导

$$
F(x,y)=0 \quad \dfrac{dy}{dx}=-\dfrac{F_x}{F_y}
$$
### 反函数求导

若$x=\varphi(y)$在某区间上**单调、可导**，且$\varphi'(y)\neq0$，则其反函数$y=f(x)$也可导，且
$$
f'(x)=\dfrac{1}{\varphi'(y)}
$$

### 参数方程求导

设$y=y(x)$是由$\left\{\begin{matrix}x=\varphi(t)\\ y=\psi(t)\end{matrix}\right.,(\alpha<t<\beta)$，确定的函数，则
若$\varphi(t),\psi(t)$都**可导**，且$\varphi(t)\neq0$，则
$$
\dfrac{dy}{dx}=\dfrac{\psi'(t)}{\varphi'(t)}
$$
若$\varphi(t),\psi(t)$都**二阶可导**，且$\varphi'(t)\neq0$，则
$$
\dfrac{d^2y}{dx^2}=\dfrac{d}{dt}(\dfrac{\psi'(t)}{\varphi'(t)})·\dfrac{1}{\varphi'(t)}=\dfrac{\psi''(t)\varphi'(t)-\varphi''(t)\psi'(t)}{\varphi'^3(t)}
$$

### 对数求导法

主要用于连乘，连除，开方，乘方

### 高阶求导

**定义**：
$$
\begin{gather*}
f^{(n)}(x_0)=\lim_{\Delta x\to0}\dfrac{f^{(n-1)}(x_0+\Delta x)-f^{(n-1)}(x_0)}{\Delta x}\\\\
=\lim_{x\to x_0}\dfrac{f^{(n-1)}(x)-f^{(n-1)}(x_0)}{x-x_0}
\end{gather*}
$$
**常用公式**：
$$
\begin{gather*}
(\sin)^{(n)}=\sin(x+n·\dfrac{\pi}{2})\\\\
(\cos)^{(n)}=\cos(x+n·\dfrac{\pi}{2})\\\\
(u±v)^{(n)}=u^{(n)}±v^{(n)}\\\\
(uv)^{(n)}=\sum_{k=0}^nC_n^ku^{(k)}v^{(n-k)}
\end{gather*}
$$

# 导数与微分常考题型方法

## 题型1 导数与微分的概念

**方法**：
 1. 利用导数定义求极限
     - 凑导数定义
     - 对于选填，可以带特殊函数
 2. 利用导数定义求导数
     - n项因子相乘
 3. **利用导数定义判断可导性**（难点）
    - 从$f'(x)存在 \stackrel{\Box\to0,\Box\neq0}{\longrightarrow} \lim_{\Box\to0}\dfrac{f(x_0+\Box)-f(x_0)}{\Box}存在$
    - 从$f'(x)存在 \stackrel{\Box\to0^-,\Box\to0^+,\Box\neq0}{\longleftarrow} \lim_{\Box\to0}\dfrac{f(x_0+\Box)-f(x_0)}{\Box}存在$

**总结**：$f(x)$在$x_0$可导的充要条件为$\lim_{h\to0}\dfrac{f(x_0+\varphi(h))-f(x_0)}{\psi(h)}$存在
 - **其中**：
    1. $\varphi(h)\to0^+,\to0^-$
    2. $\varphi\neq0$
    3. $\varphi(h)$与$\psi(h)$为同阶无穷小
即
$$
\lim_{h\to0}\dfrac{f(x_0+\varphi(h))-f(x_0)}{\psi(h)}=\lim_{h\to0}\dfrac{f(x_0+\varphi(h))-f(x_0)}{\varphi(h)}·\dfrac{\varphi(h)}{\psi(h)}
$$

**结论1**：设$f(x)=\varphi(x)|x-a|$，其$\varphi(x)$在$x=a$处连续，则$f(x)$在$x=a$处可导的充要条件是$\varphi(a)=0$

**结论2**：关于$f(x)$与$|f(x)|$可导之间的关系
 - $f(x)$可导 $\nrightarrow\, |f(x)|$可导（|x|）
 - $f(x)$可导 $\nleftarrow\,|f(x)|$可导（$f(x)=\left\{\begin{matrix}1,x\geq0\\-1,x<0\end{matrix}\right.$）
==但是如果附加$f(x)$连续==，则
 - 若$f(x_0)\neq0$，则$|f(x)|$在$x_0$处可导 $\Leftrightarrow f(x)$在$x_0$处可导
 - 若$f(x_0)=0$，则$|f(x)|$在$x_0$处可导 $\Leftrightarrow f'(x_0)=0$

## 题型2 导数的几何意义

题型：求切线，斜率

## 题型3 导数与微分的计算

### 复合函数求导

**技巧**：设$y=f(u),u=g(x),u_0=g(x_0)$
 - 如果$g'(x_0),f'(u_0)$都存在，则$y=f(g(x))$在$x_0$处可导，且$\dfrac{dy}{dx}|_{x=x_0}g'(x_0)·f'(u_0)$
 - 若$g'(x_0),f'(u_0)$至少有一个不存在，则$y=f(g(x))$在$x_0$处**不一定**可导，此时需要==求出复合函数的表达式==，再进一步考察

### 隐函数求导

### 参数方程求导

一阶**公式**：$\dfrac{dy}{dx}=\dfrac{y'(t)}{x'(t)}$

二阶**推导**：$\dfrac{d^2y}{dx^2}=\dfrac{d}{dt}(\dfrac{y'(t)}{x'(t)})\dfrac{1}{x'(t)}$

二阶**公式**：$\dfrac{d^2y}{dx^2}=\dfrac{y''(t)x'(t)-x''(t)y'(t)}{x'^3(t)}$
 -  综合性题目常用（参数方程+隐函数求导）

### 反函数求导

**反函数求导公式**：
 - 一阶公式：$\varphi'(y)=\dfrac{1}{f'(x)}$
 - ==**二阶推导公式**==：$\varphi''(y)=\dfrac{d}{dx}[\dfrac{1}{f'(x)}]·\dfrac{dx}{dy}=-\dfrac{f''(x)}{[f'(x)]^2}·\dfrac{1}{f'(x)}$
    - ==经典误区==：二阶求导是对y求，不能简单的将$f(x)$的二阶导求倒数

### 对数求导

适合幂指函数、连乘、连除、开方、乘方

### 高阶导数

**方法**：
 1. 代公式
 2. 求一阶，二阶，三阶，归纳n阶导
 3. 利用泰勒级数（公式）

**初等数学结论**：$\sin(x+\frac{\pi}{4})=\frac{\sqrt2}{2}(\sin x+\cos x)$
**推广**：
![[辅助角公式]]

# 导数的应用

## 微分中值定理

意义：将导数和函数联系起来

### 罗尔定理

**若**：
 1. $f(x)$在$[a,b]$上连续
 2. $f(x)$在$(a,b)$内可导
 3. $f(a)=f(b)$
 则$\exists\xi\in(a,b)$，使得$f'(\xi)=0$

*注*：证明存在$\xi\in(a,b)$，使得$f'(xi)=0$常用的两种方法
 - 罗尔定理
 - 证明$f(x)$在$(a,b)$内有极（最）值点

### 拉格朗日定理

**若**：
 1. $f(x)$在$[a,b]$上连续
 2. $f(x)$在$(a,b)$内可导
则$\exists\xi\in(a,b)$，使得$\dfrac{f(b)-f(a)}{b-a}=f'(\xi)$

### 柯西定理

**若**：
 1. $f(x)$在$[a,b]$上连续
 2. $f(x)$在$(a,b)$内可导，且$g'(x)\neq0$
则$\exists\xi\in(a,b)$，使得$\dfrac{f(b)-f(a)}{g(b)-g(a)}=\dfrac{f'(\xi)}{g'(\xi)}$

### 泰勒定理（拉格朗日余项）

设$f(x)$在区间 *I* 上（n+1）阶可导，$x_0\in I$，那么对$\forall x\in I$，至少存在一个$\xi$，使得：
$$
f(x)=f(x_0)+f'(x_0)(x-x_0)+...+\dfrac{f^{(n)}(x_0)}{n!}(x-x_0)^n+R_n(x)
$$
其中$R_n(x)=\dfrac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}$，$\xi$在$x,x_0$之间

### 四大中值定理联系

**本质**：建立函数与一阶导数的关系（泰勒是建立与高阶导数的关系）

**关系**：
 - 罗尔定理$\stackrel{推广}{\longrightarrow}$拉格朗日中值定理$\stackrel{推广}{\longrightarrow}$柯西定理
 - 罗尔定理$\stackrel{特例f(a)=f(b)}{\longleftarrow}$拉格朗日中值定理$\stackrel{特例g(x)=x}{\longleftarrow}$柯西定理
 - 拉格朗日中值定理$\stackrel{推广}{\longrightarrow}$泰勒定理$\stackrel{特例n=0}{\longrightarrow}$拉格朗日中值定理

**罗尔定理**：构造辅助函数可以证明拉格朗日及柯西定理

## 极值与最值

### 极值

#### 极值的必要条件

若$f(x)在x_0$处取得极值，且在$x_0$处可导，则$f'(x_0)=0$
 - 对于可导函数而言，极值点一定是驻点
 - **可能**的极值点$\left\{\begin{matrix}f'(x_0)=0\\f'(x_0)不存在\end{matrix}\right.$

#### 极值的充分条件

**第一充分条件**：
设$f'(x_0)=0$（$f(x)在x_0$连续），且在$x_0$的某去心邻域$\mathring{U}(x_0,\delta)$内可导
 1. 若$x\in(x_0-\delta,x_0)$时，$f'(x_0)>0$，而$x\in(x_0,x_0+\delta)$时，$f'(x_0)<0$，则$f(x)$在$x_0$处取得**极大值**
 2. 若$x\in(x_0-\delta,x_0)$时，$f'(x_0)<0$，而$x\in(x_0,x_0+\delta)$时，$f'(x_0)>0$，则$f(x)$在$x_0$处取得**极小值**
 3. 若$\in\mathring{U}(x_0,\delta)$时，$f'(x)$不变号，则$f(x)在x_0$处**没有极值**

**第二充分条件**：
设$f(x)在x_0$处二阶可导，且$f'(x_0)=0,f''(x_0)\neq0$，则
 1.  当$f''(x_0)<0$，$f(x)在x_0$处取**极大值**
 2. 当$f''(x_0)>0$，$f(x)在x_0$处取**极小值**

**第三充分条件**：
设$f(x)在x_0$处n（$n\geq2$）阶可导，且$f'(x_0)=f''(x_0)=f^{(n-1)}(x_0)=0$，但$f^{(n)}(x_0)\neq0$，则：
 1. 当n为**偶数**时，$f(x)在x_0$处取得极值，当$f^{(n)}(x_0)>0$，$f(x)在x_0$处取**极小值**，当$f^{(n)}(x_0)<0$，$f(x)在x_0$处取**极大值**
 2. 当n为**奇数**时，$f(x)在x_0$处**没有极值**

### 最值

求连续函数$f(x)在[a,b]$上的最值
 1. 求出$f(x)在(a,b)$内的驻点和不可导的点$x_1,x_2...x_n$
 2. 求出函数值$f(x_1),f(x_2)...f(x_n),f(a,f(b)$
 3. 比较上述值
*注：若连续函数$f(x)$在$[a,b]$上仅有**唯一**极值点，则不用比较*

**最大最小值的应用题**：
 1. 建立目标函数
 2. 按上述求最值方法做

## 曲线凹向与拐点

### 曲线的凹向

**定义**：
 - （凹）$\dfrac{x_1+x_2}{2}<\dfrac{f(x_1)+f(x_2)}{2}$
 - （凸）$\dfrac{x_1+x_2}{2}>\dfrac{f(x_1)+f(x_2)}{2}$

**判定**：二阶导数的正负
 - 若在区间$I$上$f''(x)>0(<0)$，则曲线$y=f(x)在I$上是凹（凸）的

### 曲线的拐点

定义：曲线$y=f(x)$在点$(x_0,f(x_0))$两侧凹凸性相反

**判定**：一个必要三个充分（极值的条件升一阶）

## 曲线的渐近线

### 水平渐近线

若$\lim_{x\to\infty}f(x)=A$（$\lim_{x\to-\infty}f(x)=A或者\lim_{x\to+\infty}f(x)=A$），那么$y=A是y=f(x)$的**水平渐近线**

### 垂直渐近线

若$\lim_{x\to x_0}f(x)=\infty$（$\lim_{x\to x_0^-}f(x)=\infty或\lim_{x\to x_0^+}f(x)=\infty$），则$x=x_0是y=f(x)$的**垂直渐近线**

### 斜渐近线

算两个极限：$\lim_{x\to\infty}\dfrac{f(x)}{x}=a\,,\lim_{x\to \infty}(f(x)-ax)=b$（或者$x\to-\infty,x\to+\infty$），那么$y=ax+b是f(x)$的**斜渐近线**

若$f(x)=ax+b+o(1)$，则$y=ax+b$是**斜渐近线**
 - 即线性函数+一个$x\to\infty$时的**无穷小**

## 平面曲线的曲率

**曲率的定义**：$K=\lim_{\Delta s\to0}|\dfrac{\Delta\alpha}{\Delta s}|$（≥0）
 - 切线转角的改变量除以弧长线

**曲率的计算**：
 1. 若由$y=y(x)$给出，则$K=\dfrac{|y''|}{(1+y'^2)^{\frac{3}{2}}}$
 2. 若由$\left\{\begin{matrix}x=x(t)\\y=y(t)\end{matrix}\right.$给出，则$K=\dfrac{|y''x'-y'x''|}{(x'^2+y'^2)^{\frac{3}{2}}}$
     - **思想**：用参数方程求出$y',y''$带入1式即可

**曲率圆与曲率半径**：
 - 圆的曲率K=$\frac{1}{R}$
 - 先算该点的曲率K，再求出曲率圆的半径


$$
\left\{
\begin{matrix}
\end{matrix}
\right.
$$