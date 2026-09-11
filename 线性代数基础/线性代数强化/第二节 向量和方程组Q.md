# 向量复习课

##### 9.10

## 向量内积

$\alpha 与 \beta$的内积为：（**一行×一列**是一个数字）（**一列×一行**是一个n×n的矩阵）
$$
(\alpha,\beta)=\alpha^T\beta=a_1b_1+a_2b_2+...+a_nb_n
$$
**向量内积的性质**：
 1. $(\alpha,\beta) = (\beta,\alpha)$
 2. $(k\alpha,\beta)=k(\alpha,\beta)$
 3. $(\alpha+\beta,\gamma)=(\alpha,\gamma)+(\beta,\gamma)$
 4. 双线性性质：$(k\alpha+l\beta,\gamma)=k(\alpha,\gamma)+l(\beta,\gamma)$
 5. $(\alpha,\alpha)=\alpha^T\alpha\geq0,且若(\alpha,\alpha)=0\Leftrightarrow \alpha=0$

**柯西不等式用内积表示为**：
$$
|(\alpha,\beta)|\leq\sqrt{(\alpha,\alpha)}\sqrt{(\beta,\beta)}
$$

## 向量的模

**向量的模的性质**：
 1. 非负性：$\|\alpha\|\geq0，\|\alpha\|=0\Leftrightarrow \alpha=0$
 2. 齐次性：$\|k\alpha\|=|k|\|\alpha\|$
 3. **三角不等式**：$\|\alpha+\beta\|\leq\|\alpha\|+\|\beta\|$
 4. 若$\alpha$非零，则$\dfrac{1}{\|\alpha\|}\alpha$一定是单位向量

**向量的夹角**：$\cos\theta = \dfrac{(\alpha,\beta)}{\|\alpha\|\|\beta\|}$

## 向量组

$r(A)=A的行秩=A的列秩$

三列/行成比例的矩阵A，$r(A)=1$，一定可以化为**一列乘一行**的形式
 - $tr(A)=向量内积$
 - $A^n=l^{n-1}A$

# 向量组的线性相关性

**线性相关**：
$$
\left
\{
\begin{matrix}
	线性相关定义：存在一组k，使得k_1\alpha_1+k_2\alpha_2+...+k_s\alpha_s=0\\\\
	齐次线性方程组\begin{bmatrix}\alpha_1&...&\alpha_s\end{bmatrix}\begin{bmatrix}\alpha_1\\...\\\alpha_s\end{bmatrix}=0\,有非零解\\\\
	r(\alpha_1,...,\alpha_s)<s
\end{matrix}
\right.
$$

**线性无关**：
$$
\left
\{
\begin{matrix}
	线性无关定义：仅在k全为0时，使得k_1\alpha_1+k_2\alpha_2+...+k_s\alpha_s=0\\\\
	齐次线性方程组\begin{bmatrix}\alpha_1&...&\alpha_s\end{bmatrix}\begin{bmatrix}\alpha_1\\...\\\alpha_s\end{bmatrix}=0\,只有零解\\\\
	r(\alpha_1,...,\alpha_s)=s
\end{matrix}
\right.
$$

**线性表出**：
$$
\left
\{
\begin{matrix}
	定义(\beta=k_1\alpha_1+k_2\alpha_2+...+k_s\alpha_s)\\\\
	非齐次线性方程组\begin{bmatrix}\alpha_1&...&\alpha_s\end{bmatrix}\begin{bmatrix}\alpha_1\\...\\\alpha_s\end{bmatrix}=\beta\,有解\\\\
	r(\alpha_1,...,\alpha_s)=r(\alpha_1,...,\alpha_s,\beta)
\end{matrix}
\right.
$$
**系数矩阵**的秩等于**增广矩阵**的秩

**不能表出**：
$$
\left
\{
\begin{matrix}
\begin{bmatrix}\alpha_1&...&\alpha_s\end{bmatrix}\begin{bmatrix}\alpha_1\\...\\\alpha_s\end{bmatrix}=\beta\,无解\\\\
	r(\alpha_1,...,\alpha_s)<r(\alpha_1,...,\alpha_s,\beta)
\end{matrix}
\right.
$$

**注1**：向量组B可由向量组A线性表示，则：
$$
方程AX=B有解\Leftrightarrow r(\alpha_1,...,\alpha_s)=r(\alpha_1,...,\alpha_s,\beta_1,...,\beta_t)
$$

**注2**：如果向量组$\beta_1,...,\beta_t$，可由向量组$\alpha_1,...,\alpha_s$线性表示，则：
$$
r(\beta_1,...,\beta_t)\leq r(\alpha_1,...,\alpha_s)
$$
## 判断相关性的常用方法

3中基本方法+2种附加方法

**基本方法**：
 1. 定义法
     - 先假设$k_1\alpha_1+k_2\alpha_2+...+k_s\alpha_s=0$
        - **乘**：
           - 在等式两端同乘矩阵、向量、数
           - 目的使等式变短，方便证明$k_1=k_2=...=k_s=0$
        - **向量重组**：将已知条件带入等式，重新组合，结合条件，得到$k_1=k_2=...=k_s=0$
     - 得到$k_1=k_2=...=k_s=0$
 2. 方程组角度
 3. 秩的角度

*附加方法*
 1. **假设反证法**
 2. 如果向量个数等于维数，也可以使用**行列式**的角度证明

**结论**：设$A^{m-1}\alpha\neq0,A^m\alpha=0$，则$\alpha,A\alpha,...,A^{m-1}\alpha$ 线性无关

## 线性相关/无关/表出的相关结论

**（1）部分与整体定理**（个数问题）
 1. 如果向量组$\alpha_1,...,\alpha_s$的某个部分组线性相关，则$\alpha_1,...,\alpha_s$线性相关
 2. 如果向量组$\alpha_1,...,\alpha_s$线性无关，则向量组$\alpha_1,...,\alpha_s$任意一个部分组也线性无关

*部分相关，整体相关。部分无关，整体无关*

**（2）延长与缩短定理**（维数问题）
在$r$维向量组$\alpha_1,...,\alpha_s$的个向量添上n-r个分量变成n维向量组$\beta_1,...,\beta_s$
 1. 如果$\beta_1,...,\beta_s$线性相关，则$\alpha_1,...,\alpha_s$也线性相关
 2. 如果$\alpha_1,...,\alpha_s$线性无关，那么$\beta_1,...,\beta_s$也线性无关
*原相关，缩短相关。原无关，延长无关*

**（3）以少表多，多必相关**
设向量组$\alpha_1,...,\alpha_s$可由$\beta_1,...,\beta_t$线性表出且 t < s，那么$\alpha_1,...,\alpha_s$线性相关
**逆否命题**
设向量组$\alpha_1,...,\alpha_s$可由$\beta_1,...,\beta_t$线性表出且$\alpha_1,...,\alpha_s$线性无，则 **t ≥ s**

**（4）从定义**：
 -  一个向量$\alpha$线性相关$\Leftrightarrow \alpha=0$
 - 两个向量相关$\Leftrightarrow$它们的对应分量成比例

**（5）从行列式**：
 - n维向量组$\alpha_1,...,\alpha_n$线性相关$\Leftrightarrow |\alpha_1,...,\alpha_n|=0$
 - n维向量组$\alpha_1,...,\alpha_n$线性相关$\Leftrightarrow |\alpha_1,...,\alpha_n|\neq0$

**（6）从方程组**：
 - 初等行变换不改变**列向量**组的线性相关性
 - 当向量个数s大于维数n时，$\alpha_1,...,\alpha_s$一定线性相关
 - 设向量组$\alpha_1,...,\alpha_s$线性无关，而向量组$\alpha_1,...,\alpha_s,\beta$线性相关，则$\beta$能由向量组$\alpha_1,...,\alpha_s$**线性表出，且唯一**

**（7）从秩的角度**
 - 包含零向量的向量组是线性相关的
 - 如果向量组$\beta_1,...,\beta_t$可由向量组$\alpha_1,...,\alpha_s$线性表示，则$r(\beta_1,...,\beta_t)\leq r(\alpha_1,...,\alpha_s)$
    - *向量组的秩可理解为向量组表出能力，秩越小，向量组的表出能力就越弱，谁能表示别人，谁就NB，谁的秩就大*
 - 向量组$\beta_1,...,\beta_t$能由向量组$\alpha_1,...,\alpha_s$线性表示的充分必要条件是$$r(\alpha_1,...,\alpha_s)=r(\alpha_1,...,\alpha_s,\beta_1,...,\beta_t)$$
零向量：
 - 包含零向量的向量组是线性相关的
 - 零向量与任何一个向量线性相关
 - 零向量与任何一个向量都正交

# 极大线性无关组

**定义**：设向量组$\alpha_1,...,\alpha_s$，有r个向量线性无关，但$\alpha_1,...,\alpha_s$中任意r+1个向量（如果有的话）线性相关，则称这r个线性无关的向量是$\alpha_1,...,\alpha_s$的**一个极大线性无关组**，其中r为向量组的秩，即$r(\alpha_1,...,\alpha_s)=r$
 - *极大线性无关组只含有零向量的向量组没有极大线性无关组，规定它的秩为0*

**判断极大线性无关组**：主要注意以下三点：
 - 是否是部分组
 - 是否线性无关
 - 个数是否满足要求

## 初等变换法求极大线性无关组、秩

**原理**：初等行变换不改变列向量组的线性相关性

**步骤**：
 1. 对列向量构成的矩阵$A=(\alpha_1,...,\alpha_s)$作**初等行变换**，化为行阶梯矩阵$B=(\alpha_1',...,\alpha_s')$，行阶梯矩阵的秩就是原矩阵A的秩
 2. 在行阶梯矩阵B中**抽取每个主元所在的列**，记录所在的列的序号
 3. 在矩阵A采取同样的抽取方式，所得到的部分组即为矩阵$A=(\alpha_1,...,\alpha_s)$的极大无关组

# *OR分解*

==从命题趋势而言，近期可能会考==

QR分解：A为n阶可逆矩阵，则A一定可以分解为==一个Q（正交矩阵）和一个R（上三角矩阵）==

# <span style="color:red;font-weight:bold">向量组等价</span>

出题：
 1. 具体（含参）：计算量大
 2. 抽象：理论分析多

**定义**：若向量组$\alpha_1,...,\alpha_s$中的每个向量都可由向量组$\beta_1,...,\beta_t$线性表出，就称向量组$\alpha_1,...,\alpha_s$可由$\beta_1,...,\beta_t$线性表出，如果两个向量组互相可以线性表出，就称它们**等价**
 - 等价具有**反身性、对称性、==传递性==**

## <span style="color:red;font-weight:bold">向量组等价常用判据</span>

向量组(I)和向量组(II)等价的三个常用充要条件为：
 1. 向量组(I)和向量组(II)可**相互线性表示**
 2. 其中一个向量组可由另外一个向量组线性表示，即$r(I)=r(II)$
 3. $r(I)=r(II)=r(I,II)$，**三秩相同**

## 向量组等价的性质

**性质**：
 1. 向量组与其**任一极大线性无关**组等价
 2. 向量组的**任意**两个极大无关组等价
 3. 等价向量组的极大无关组等价
 4. ==等价向量组的秩相等==（易错点：不能反推）

*注：两个向量组等价，向量的个数不一定相同*
*注：要将向量组等价与矩阵等价区分*








$$
\left
\{
\begin{matrix}

\end{matrix}
\right.
$$
$$
\begin{gather*}
\begin{bmatrix}

\end{bmatrix}
\end{gather*}
$$