# 特征值与特征向量

##### 9.15

$$
Ax=\lambda x
$$

*特征值仅针对方阵，且特征向量不为0*

**求解**：

1. 求解特征方程$f(\lambda)=|\lambda E-A|$，得到n个根，这n个根即为n个特征值，根的重数即为==**代数重数k**==（所有代数重数加起来必须等于阶数）
2. 将个特征值带入特征矩阵，求出齐次线性方程组$(\lambda E-A)x=0$的基础解系，得到矩阵A各个特征值对应的全部特征向量
   对于某特征值$\lambda_i$，齐次方程组$(\lambda_iE-A)x=0$所对应的基础解系有p个线性无关的向量，==**p即为几何重数**==

*注：几何重数p ≤ 代数重数k，即k重特征值λ只多只有k个线性无关的特征向量*

- *若矩阵的所有特征值的==代数重数=几何重数==，那么这个矩阵就可以**相似对角化**
  
  $$
  |A|=0\Leftrightarrow A的列向量线性相关\Leftrightarrow Ax=0有非零解\Leftrightarrow A有0特征值
  $$

## 特征值、特征向量的性质

**特征值相关性质**：

1. n次方程必有n个特征值，也即任一n阶矩阵必有n个特征值
2. **特征值之和等于==矩阵的迹tr(A)==，特征值之积为==矩阵的行列式|A|==**
   - *底层性质：只要矩阵是方阵就满足*

**特征向量**：

1. 若x为λ对应的特征向量，则kx也是对应特征值的特征向量
   - 若$x_1,x_2$是λ对应的特征向量，则$x_1,x_2$对应的任一线性组合也是该特征值对应的特征向量
2. 不同特征值的特征向量必然**线性无关**

## <span style="color:red;font-weight:bold">A以及A有关常用矩阵的特征值与特征向量</span>

| 矩阵   | A         | $kA+bE$      | $A^k$       | $f(A)$       | $A^{-1}$            | $A^*$                   | $P^{-1}AP$ |
| ---- | --------- | ------------ | ----------- | ------------ | ------------------- | ----------------------- | ---------- |
| 特征值  | $\lambda$ | $k\lambda+b$ | $\lambda^k$ | $f(\lambda)$ | $\frac{1}{\lambda}$ | $\frac{\|A\|}{\lambda}$ | $\lambda$  |
| 特征向量 | x         | x            | x           | x            | x                   | x                       | $P^{-1}x$  |

上述表格中：

1. $A^{-1},A^*$所在列，$\lambda \neq0$
2. 若矩阵A满足$f(A)=O$，则矩阵A对应的特征值必满足$f(\lambda)=0$，但$f(\lambda)=0$的解不一定都是矩阵A对应的特征值
3. $A^T$的特征值与A相同，但特征向量不再相同，需另外计算
4. 只有A与$kA+bE$的特征值特征向量可以**互推**，除非题目给出条件

# <span style="color:red;font-weight:bold">秩为1矩阵专题</span>

若一个矩阵A秩$r(A)=1$，则A可分解为==一个列向量×一个行向量==
![[秩为1矩阵的相关结论]]

# <span style="color:red;font-weight:bold">矩阵相似对角化</span>

## 相似对角化常用结论

![[相似对角化的常用结论]]

## 相似对角化的求解

**步骤**：
 1. 求出A的特征值
 2. 若A可对角化，则k重特征值对应k个线性无关的特征向量，求出A的n个线性无关的特征向量$x_1,...,x_n$
 3. 令P=$(x_1,...,x_n),\Lambda=	\begin{bmatrix}\lambda_1&&&\\&\lambda_2&&\\&&...&\\&&&\lambda_n\end{bmatrix}$，则P可逆，且有$P^{-1}AP=\Lambda$

# 矩阵相似

##### 9.16
$$
P^{-1}AP=B \Rightarrow A\sim B
$$

**矩阵相似的必要条件**：
$$
A\sim B\left
\{
	\begin{matrix}
		|\lambda E-A|=|\lambda E-B|
			\left
			\{
				\begin{matrix}
					|A|=|B|\\\\
					tr(A)=tr(B)\\\\
					\lambda_A=\lambda_B
				\end{matrix}
			\right.
		\\\\
		r(A)=r(B)\\\\
		r(\lambda E-A)=r(\lambda E-B)
	\end{matrix}
\right.
$$

## 矩阵相似的性质

**性质**：
 1. **传递性**：$A\sim C,B\sim C,则A\sim B$
 2. 若$A\sim B$，则$$kA\sim kB,A^m\sim B^m,f(A)\sim f(B)$$，其中$$f(A)=a_nA^n+...+a_1A^1+a_0E,f(B)=a_nB^n+...+a_0E$$
 3. 若$A\sim B$，还可推得$$A^T\sim B^T,A^*\sim B^*$$
 4. 若$A\sim B$，且A可逆，则$$A^{-1}\sim B^{-1},f(A^{-1})\sim f(B^{-1}),AB\sim BA$$
 5. 若$A\sim C,B\sim D$，则$$\begin{bmatrix}A&O\\O&B\end{bmatrix}\sim\begin{bmatrix}C&O\\O&D\end{bmatrix}$$

*注：* 仅有$kA,A^T,A^{-1}$的结论可以==倒推==
*注：两矩阵相似，它们不一定与同一个对角矩阵相似，因为它们**不一定可以相似对角化** *

## 判断、证明矩阵相似

考研范畴内，证明/判断两个矩阵相似主要==靠定义或者相似的传递性==来处理，其中**中介矩阵C**通常选择**对角矩阵**$\Lambda$

问题：若$A\sim B$，且A、B均可相似对角化，求P使得$P^{-1}AP=B$
**解**：
	由$A\sim\Lambda,B\sim\Lambda$，得$P_1^{-1}AP_1=\Lambda,P_2^{-1}BP_2=\Lambda$，
	联立二式得：$P_1^{-1}AP_1=P_2^{-1}BP_2$
	即：$P_2P_1^{-1}AP_1P_2^{-1}=B$
	$\Rightarrow (P_1P_2^{-1})^{-1}AP_1P_2^{-1}=B$，则$P=P_1P_2^{-1}$

# 正交矩阵、实对称矩阵

## 正交矩阵的性质

$$
A^TA=AA^T=E
$$
**性质**：
$$
Q^TQ=E\Rightarrow
\left
\{
	\begin{matrix}
		|Q|= ±1\\
		Q^{-1}=Q^T\\
		Q由规范正交基组成
	\end{matrix}
\right.
\,\,
\left
\{
	\begin{matrix}
		Q^T,Q^*,Q^{-1}也是正交矩阵\\
		若干个同阶正交阵相乘仍是正交阵\\
		特征值\lambda=1或-1
	\end{matrix}
\right.
$$

## 实对称矩阵的性质

**性质**：
 1. n阶实对称矩阵A**必有**n个实的特征值，也**必有**n个线性无关的特征向量，且A的**几何重数等于代数重数**
 2. 实对称矩阵对应于不同的特征值的特征向量必是**正交**的，即$\lambda_1\neq\lambda_2$时，有$(x_1,x_2)=x_1^Tx_2=0$
 3. n阶实对称矩阵A不但可以相似对角化，还能**正交相似对角化**，即存在Q使得$Q^{-1}AQ=\Lambda，又Q^{-1}=Q^T，即Q^{-1}AQ=Q^TAQ=\Lambda$，因此正交矩阵Q在相似及二次型均有意义
     - 反推：n阶实矩阵可以**正交相似对角化**那么这个矩阵就是实对称矩阵

$$
\begin{matrix}
	三个向量两两正交 \Rightarrow 线性无关\\\\
	三个向量两两无关 \nRightarrow 线性无关
\end{matrix}
$$

## 实对称矩阵正交相似对角化的一般步骤

**步骤**：
 1. 求出A的所有特征值$\lambda$，及**互不相同的特征值**$\lambda_{p_i}$
 2. 求出每一个齐次方程组$(\lambda_{p_i}E-A)x=0$的**基础解系**，合并得到A的n个线性无关的**特征向量**，再将这些特征向量==**先正交化再单位化**==$\gamma$
 3. 令$Q=(\gamma_1,...,\gamma_n),\Lambda为\gamma_i所构成的矩阵$，则Q可逆，有$Q^{-1}AQ=Q^TAQ=\Lambda$

### 解题技巧

遇见形如$\alpha\alpha^T,\beta\beta^T$，==要想到==$\alpha\alpha^T\alpha,\beta\beta^T\alpha$

### 施密特正交化

给定一组线性无关但不正交的向量，将其标准正交化**步骤**：
 1. 正交化
     - $\beta_1=x_1$
     - $\beta_2=x_2-\dfrac{(x_2,\beta_1)}{(\beta_1,\beta_1)}\beta_1$
     - $\beta_3=x_3-\dfrac{(x_3,\beta_2)}{(\beta_2,\beta_2)}\beta_2-\dfrac{(x_3,\beta_1)}{(\beta_1,\beta_1)}\beta_1$
 2. 单位化
     - $\gamma_1=\dfrac{1}{|\beta_1|}\beta_1$
     - $\gamma_2=\dfrac{1}{|\beta_2|}\beta_2$
     - $\gamma_3=\dfrac{1}{|\beta_3|}\beta_3$

## 谱分解定理

**原理**：若n阶实对称矩阵A对应于特征值$\lambda_1,...,\lambda_n$的**单位正交**特征向量为$\gamma_1,...,\gamma_n$，则
$$
A=\lambda_1\gamma_1\gamma_1^T+...+\lambda_n\gamma_n\gamma_n^T
$$
*当矩阵特征值的**0越多**越好用*
*当特征值为a、a、b时，可以先求A-aE（它的特征值为0、0、b-a）*

# 反求矩阵问题

![[特征值&特征向量信息常见表现形式]]

# 两类特殊的相似问题

## 同时对角化问题（公共特征向量）

（1）设A，B均是n阶矩阵，则$$AB与BA有相同的特征值$$

（2）设A，B均是n阶矩阵，且A可逆，则$$AB\sim BA$$

（3）设A，B均是n阶矩阵，则$$AB=aA+bB(ab\neq0)\Rightarrow AB=BA$$

（4）设A，B均是n阶矩阵，AB=BA，且A有n个互不相同的特征值，则
$$
A的特征向量都是B的特征向量
$$

## 无法通过相似对角化作为中介的相似传递问题

需要通过相似的定义说明两个矩阵相似
$$
P^{-1}AP=B\,\, 或者AP=PB
$$
**步骤**：
 1. 设一个P矩阵（二阶矩阵）
 2. 解方程
 3. 若为高阶矩阵（一般是三阶）：逐个突破，将P列分块



