# 重极限、连续、偏导数、全微分
##### 8.25

## 重极限

$$
\lim_{(x,y)\to(x_0,y_0)}\,f(x,y)=A
$$
**注**：
 1. $(x,y)\to(x_0,y_0)$是以==**任意方式**==
     - 只要有一种方式极限不存在，或者两种方式的极限不相等，则极限不存在
     - 洛必达法则失效
 2. **还存在的结论**：
     1. 局部有界性
     2. 保号性
     3. 有理运算
     4. 极限与无穷小的关系
     5. 夹逼性

计算重极限：
1. 取绝对值
2. 使用夹逼

证明重极限不存在：==沿两种不同路径极限不同==
 - 一般取y=kx，x->0，当k值不一样时，极限值不一样说明其不存在

## 连续

定义：
$$
\lim_{(x,y)\to(x_0,y_0)}\,f(x,y)=f(x_0,y_0)
$$
**性质**：
 1. 多元连续函数的和、差、积、商（分母不为零）及复合仍为连续函数
 2. 多元基本初等函数在其定义区域内连续；初等函数在其定义区域内连续
 3. 有界闭区域上连续函数的性质
     - **有界性**：若$f(x,y)$在有界闭区域D上连续，则$f(x,y)$在D上有界
     - **最值性**：若$f(x,y)$在有界闭区域D上连续，则$f(x,y)$在D上必有最大值和最小值
     - **介值性**：若$f(x,y)$在有界闭区域D上连续，则$f(x,y)$在D上可取到介于最大值和最小值之间的任何值

## 偏导数

定义：本质上是一个一元函数的导数
$$
\begin{matrix}
\varphi'(x_0)=\lim_{\Delta x\to0}\dfrac{\varphi(x_0+\Delta x)-\varphi(x_0)}{\Delta x}\\\\
f_x(x_0,y_0)=\lim_{\Delta x\to0}\dfrac{f(x_0+\Delta x,y_0)-f(x_0,y_0)}{\Delta x}=\dfrac{d}{dx}f(x,y_0)\Big|_{x=x_0}\\\\
\end{matrix}
$$

### 高阶偏导数

设$z=f(x,y)$

$$
\begin{matrix}
\dfrac{\partial^2 z}{\partial x^2}=f_{xx}''(x,y)=\dfrac{\partial}{\partial x}(\dfrac{\partial z}{\partial x})\\\\
\dfrac{\partial^2 z}{\partial x\partial y}=f_{xy}''(x,y)=\dfrac{\partial}{\partial y}(\dfrac{\partial z}{\partial x})\\\\
\dfrac{\partial^2 z}{\partial y\partial x}=f_{yx}''(x,y)=\dfrac{\partial}{\partial x}(\dfrac{\partial z}{\partial y})\\\\
\dfrac{\partial^2 z}{\partial y^2}=f_{yy}''(x,y)=\dfrac{\partial}{\partial y}(\dfrac{\partial z}{\partial y})\\\\
\end{matrix}
$$
**定理**：如果函数$z=f(x,y)$的两个二阶混合偏导数$f_{xy}''(x,y)\,,f_{yx}''(x,y)$在区域D内连续，则在区域D内恒有
$$
f_{xy}''(x,y)=f_{yx}''(x,y)
$$

## 全微分

$$
\Delta y=f(x_0+\Delta x)-f(x_0)=A\Delta x+o(\Delta x)
$$
**定义**：若$\Delta z = f(x_0+\Delta x,y_0+\Delta y)-f(x_0,y_0)=A\Delta x+B\Delta y+o(\rho)$，其中$\rho=\sqrt{(\Delta x)^2+(\Delta y)^2}$

**结论**：以下四条结论等价
 1. $\Delta z = f(x_0+\Delta x,y_0+\Delta y)-f(x_0,y_0)=A\Delta x+B\Delta y+o(\rho)$，**定义**
 2. $\lim_{\Delta x\to0,\Delta y\to0}\dfrac{[f(x_0+\Delta x,y_0+\Delta y)-f(x_0,y_0)]-[A\Delta x+B\Delta y]}{\sqrt{(\Delta x)^2+(\Delta y)^2}}=0$
 3. $\Delta z=f(x,y)-f(x_0,y_0)=A(x-x_0)+B(y-y_0)+o(\rho)$
 4. $\lim_{x\to x_0,y\to y_0}\dfrac{[f(x,y)-f(x_0,y_0)]-[A(x-x_0)+B(y-y_0)]}{\sqrt{(x-x_0)^2+(y-y_0)^2}}=0$


### 可微性判断

可微：$\Delta z = f(x_0+\Delta x,y_0+\Delta y)-f(x_0,y_0)=A\Delta x+B\Delta y+o(\rho)$

**必要条件**：$f_x(x_0,y_0)\,,f_y(x_0,y_0)$都存在

**充分条件**：$f_x(x,y)\,,f_y(x,y)$在$(x_0,y_0)$连续

**用定义判断**：
 1. $f_x(x_0,y_0)\,,f_y(x_0,y_0)$ 是否都存在？
 2. $\lim_{(\Delta x,\Delta y)\to(0,0)}\dfrac{\Delta z-[f_x(x_0,y_0)\Delta x+f_y(x_0,y_0)\Delta y]}{\sqrt{(\Delta x)^2+(\Delta y)^2}}$ 是否为零？

### 计算

若$f(x,y)$可微，则
$$
dz=\dfrac{\partial f}{\partial x}dx+\dfrac{\partial f}{\partial y}dy
$$

## 连续、可导、可微的关系

**一元函数**：
 - 连续$\nrightarrow$可导，可导$\rightarrow$连续
 - 连续$\nrightarrow$可微，可微$\rightarrow$连续
 - 可微$\leftrightarrow$可导

**多元函数**：
 - 连续$\nrightarrow$可导，可导$\nrightarrow$连续
 - 连续$\nrightarrow$可微，可微$\rightarrow$连续
 - 可微$\rightarrow$可导，可导$\nrightarrow$可微
 - 可微$\nrightarrow$一阶偏导数连续，一阶偏导数连续$\rightarrow$可微

**差异点**：==可导$\nrightarrow$连续== 以及 ==可导$\nrightarrow$可微==
 - 可导只与该点沿**坐标轴方向**有关

**经典反例**：
（1）可导$\nrightarrow$连续
$$
f(x,y)=
\left\{
\begin{matrix}
\dfrac{xy}{x^2+y^2},(x,y)\neq(0,0)\\
0,(x,y)=(0,0)
\end{matrix}
\right.
$$

（2）可导$\nrightarrow$可微
$$
f(x,y)=
\left\{
\begin{matrix}
\dfrac{xy}{\sqrt{x^2+y^2}},(x,y)\neq(0,0)\\
0,(x,y)=(0,0)
\end{matrix}
\right.
$$

（3）可微$\nrightarrow$一阶偏导数连续
$$
f(x,y)=
\left\{
\begin{matrix}
(x^2+y^2)\sin\dfrac{1}{x^2+y^2},(x,y)\neq(0,0)\\
0,(x,y)=(0,0)
\end{matrix}
\right.
$$

# 重极限、连续、偏导数、全微分常考题型

## 题型1 讨论连续性、可导性、可微性


# 偏导数与全微分的计算

## 复合函数求导法

**一元函数**：$y=f(u),u=g(x)$可导$\Rightarrow\,y=f[g(x)]$可导
$$
\dfrac{dy}{dx}=f'(u)g'(x)
$$

**多元函数**：设$u=u(x,y)\,,v=v(x,y)$可导，$z=f(u,v)$在相应点有连续一阶偏导数，则：
$$
\dfrac{\partial z}{\partial x}=\dfrac{\partial f}{\partial u}\dfrac{\partial u}{\partial x}+\dfrac{\partial f}{\partial v}\dfrac{\partial v}{\partial x}
$$
$$
\dfrac{\partial z}{\partial y}=\dfrac{\partial f}{\partial u}\dfrac{\partial u}{\partial y}+\dfrac{\partial f}{\partial v}\dfrac{\partial v}{\partial y}
$$
### 全微分形式的不变性

**一元函数**：$y_x'=y'_uu'_x$
$$
dy=y_x'dx=y'_uu'_xdx=y'_udu
$$
**多元函数**：设$u=u(x,y)\,,v=v(x,y),z=f(u,v)$都具有连续的一阶偏导数，则：
$$
dz=\dfrac{\partial z}{\partial x}dx+\dfrac{\partial z}{\partial y}dy=\dfrac{\partial z}{\partial u}du+\dfrac{\partial z}{\partial v}dv
$$

## 隐函数求导法

### 由一个方程所确定的隐函数

设$F(x,y,z)$有连续一阶偏导数，$F_z\neq0,z=z(x,y)$由$F(x,y,z)=0$所确定

**方法**：
 1. **公式法**：$\dfrac{\partial z}{\partial x}=-\dfrac{F_x}{F_z},\dfrac{\partial z}{\partial y}=-\dfrac{F_y}{F_z}$
 2. **等式两边求导**
     - $F_x+F_z\dfrac{\partial z}{\partial x}=0\,,F_y+F_z\dfrac{\partial z}{\partial y}=0$
 3. **全微分形式的不变性**
     - $F_x\,dx+F_y\,dy+F_z\,dz=0$

### 由方程组确定的隐函数

设$u=u(x,y)\,,v=v(x,y)$由$\left\{\begin{matrix}F(x,y,u,v)=0\\G(x,y,u,v)=0\end{matrix}\right.\quad$所确定

**方法**：
 1. **等式两边求导**
     - $\left\{\begin{matrix}F_x+F_u\dfrac{\partial u}{\partial x}+F_v\dfrac{\partial v}{\partial x}=0\\G_x+G_u\dfrac{\partial u}{\partial x}+G_v\dfrac{\partial v}{\partial x}=0\end{matrix}\right.\quad$
 2. **微分形式的不变性**
     - $\left\{\begin{matrix}F_x\,dx+F_y\,dy+F_u\,du+F_v\,dv=0\\ G_x\,dx+G_y\,dy+G_u\,du+G_v\,dv=0\end{matrix}\right.\quad$

# 偏导数与全微分的计算常考题型方法

## 题型1 求一点处的偏导数与全微分

## 题型2 求已给出具体表达式函数的偏导数和全微分

对x求，将y看为常数
对y求，将x看为常数

**结论**：若$P(x,y)\,,Q(x,y)$有一阶连续偏导数，且$P(x,y)dx+Q(x,y)dy$是某一函数的全微分，则
$$
\dfrac{\partial P}{\partial y}=\dfrac{\partial Q}{\partial x}
$$

## 题型3 含有抽象函数的复合函数偏导数与全微分
























$$
\left\{
\begin{matrix}
\end{matrix}
\right.
$$