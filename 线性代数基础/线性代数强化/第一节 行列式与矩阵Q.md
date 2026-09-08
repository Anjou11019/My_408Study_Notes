# 行列式复习

##### 7.28

## 余子式与代数余子式

余子式和代数余子式
 - 把元素$a_{ij}$的i行，j列划去，剩余的元素组成的n-1阶行列式为**余子式**，记作$M_{ij}$
 - 令$A_{ij}=(-1)^{i+j}M_{ij}$，则$A_{ij}$称为$a_{ij}$的**代数余子式**

$$
a_{i1}A_{k1}+a_{i2}A_{k2}+...+a_{in}A_{kn}=0
$$
<mark>即一行与另外一行对应元素的代数余子式的乘积之和为零</mark>

## 行列式性质

**性质**：
 1. 行列式与它的转置的值相等即：$|A|=|A^T|$
 2. 两行（列）互换，行列式的值变号
 3. 若某行（列）有公因数k，可将k提到行列式符号外
 4. 若某行（列）的k倍加到另外一行，行列式的值不变
 5. 若某行（列）所有元素之和都是两个数之和，则可将其写成两个行列式之和
 6. 行列式中如果有一行（列）元素全为0，则==行列式的值为0==
 7. 行列式中如果有一行（列）元素对应相等，则==行列式值为0==
 8. 行列式中如果有一行（列）元素对应成比例，则==行列式值为0==

## 特殊行列式

主对角线、副对角线行列式

主对角线、副对角线上（下）三角行列式

n阶范德蒙德行列式：
$$
\begin{gather*}
D_n=
\begin{vmatrix}
1&1&1&...&1\\
x_1&x_2&x_3&...&x_n\\
x_1^2&x_2^2&x_3^2&...&x_n^2\\
...&...&...&...&...\\
x_1^{n-1}&x_2^{n-1}&x_3^{n-1}&...&x_n^{n-1}
\end{vmatrix} \\\\=
\prod_{1\leq i < j\leq j}(x_j - x_i)\\\\
=(x_2-x_1)(x_3-x_1)...(x_n-x_1)\\(x_3-x_2)(x_4-x_2)...(x_n-x_2)\\...\\(x_n-x_{n-1})
\end{gather*}
$$

若A，B是两个n阶矩阵，有$|AB|=|A|·|B|$

**拉普拉斯行列式**：
 - 若A，B分别为m，n阶矩阵，有
$$
\begin{gather*}
	\begin{vmatrix}
		A&*\\
		O&B
	\end{vmatrix}=
	\begin{vmatrix}
		A&O\\
		*&B
	\end{vmatrix}=|A|·|B|\\\\
	\begin{vmatrix}
		O&A\\
		B&*
	\end{vmatrix}=
	\begin{vmatrix}
		*&A\\
		B&O
	\end{vmatrix}=(-1)^{mn}|A|·|B|
\end{gather*}
$$

**思考**：行列式最简单的计算方法是什么？
 - 行列式中0越多计算起来越简单，因此，低阶行列式的注意计算方法就是**化0降阶法**

## 常见行列式的计算

### 一点一线/二线行列式
$$
\begin{gather*}
	\begin{vmatrix}
		0&1&0&0&0\\
		0&0&2&0&0\\
		1&1&1&3&1\\
		0&0&0&0&4\\
		5&0&0&0&0\\
	\end{vmatrix}=
	\begin{vmatrix}
		0&1&0&0&0\\
		0&0&2&0&0\\
		1&0&0&3&0\\
		0&0&0&0&4\\
		5&0&0&0&0\\
	\end{vmatrix}=5\times 24=120
\end{gather*}
$$
用其他行想办法消掉其中一行，得到一点一线

### 爪型行列式

核心就是**斜爪消横爪**

### 行和相等行列式

行列式中每一行元素的和都相等，说明该行列式是行和相等的，==将其他列全部加到第1列==，这样第一列就有公因子，提出去即可得到==全为1的一列==
 - *列和相等技巧相同*
 - 对于ab型行列式，可以采用**特征值法**求行列式

$$
\begin{gather*}
	\begin{vmatrix}
		a&b&b\\
		b&a&b\\
		b&b&a
	\end{vmatrix}(看成矩阵)=
	\begin{bmatrix}
		b&b&b\\
		b&b&b\\
		b&b&b
	\end{bmatrix}+(a-b)E\\\\
	该矩阵和的特征值为3b+a-b,a-b,a-b\\\\
	故原行列式为(3b+a-b)(a-b)(a-b)
\end{gather*}
$$

### 行列同数行列式

将行列式添加一行一列，使其升阶后的行列式的值不变，称为**加边法**，加边法通常计算==除主对角线外，各行对应元素分别都有相同元素的行列式==，行列同数行列式可以加边法化简成爪形


### 范德蒙德行列式

不会直接考，一般需要转化
$$
\begin{gather*}
	\begin{bmatrix}
		a&b&c&d\\
		a^2&b^2&c^2&d^2\\
		a^3&b^3&c^3&d^3\\
		b+c+d&a+c+d&a+b+d&a+b+c\\
	\end{bmatrix}=(第1行加到第4行)\\\\
	(a+b+c+d)\begin{bmatrix}
		a&b&c&d\\
		a^2&b^2&c^2&d^2\\
		a^3&b^3&c^3&d^3\\
		1&1&1&1\\
	\end{bmatrix}
\end{gather*}
$$

### 拉普拉斯行列式

**拉普拉斯行列式**：
 - 若A，B分别为m，n阶矩阵，有
$$
\begin{gather*}
	\begin{vmatrix}
		A&*\\
		O&B
	\end{vmatrix}=
	\begin{vmatrix}
		A&O\\
		*&B
	\end{vmatrix}=|A|·|B|\\\\
	\begin{vmatrix}
		O&A\\
		B&*
	\end{vmatrix}=
	\begin{vmatrix}
		*&A\\
		B&O
	\end{vmatrix}=(-1)^{mn}|A|·|B|
\end{gather*}
$$
## 递推型行列式计算

##### 7.29

### 么型行列式

$$
\begin{gather*}
	\begin{vmatrix}
		2&0&...&0&2\\
		-1&2&...&0&2\\
		...&...&&...&...\\
		0&0&...&2&2\\
		5&0&0&-1&2\\
	\end{vmatrix}=
	\begin{vmatrix}
		0&1&0&0&0\\
		0&0&2&0&0\\
		1&0&0&3&0\\
		0&0&0&0&4\\
		5&0&0&0&0\\
	\end{vmatrix}=\\\\
	D_n=2(-1)^{(1+1)}D_{n-1}+2(-1)^{n+1}(-1)^{n-1}\\\\
	D_n=2D_{n-1}+2(n\geq 2)
	令D_n+a=2(D_{n-1}+a) \rightarrow a=2
\end{gather*}
$$

### 三对角行列式

$$
\begin{gather*}
	\begin{vmatrix}
		2a&1&0&...&0&0\\
		a^2&2a&1&...&0&0\\
		0&a^2&2a...&&0&0\\
		...&...&...&...&...&...\\
		0&0&0&...&2a&1\\
		0&0&0&...&a^2&2a\\
	\end{vmatrix}(对第一行展开)\\\\
	\rightarrow D_n=2a(-1)^{1+1}D_{n-1}+1(-1)^{1+2}a^2(-1)^{1+1}D_{n-2}\\\\
	\rightarrow D_n=2aD_{n-1}-a^2D_{n-2}\\\\
	\rightarrow 令(D_n+lD_{n-1})=k(D_{n-1}+lD_{n-2})\rightarrow k=a,l=-a\\\\
	\rightarrow D_n-aD_{n-1}=a^2(D_{n-2}-aD_{n-3})\\\\
	\rightarrow D_n-aD_{n-1}=a^{n-2}(D_2-D_1)=a^n\\\\
	\rightarrow D_n-aD_{n-1}=a^n\\\\
	\rightarrow D_n=aD{n-1}+a^n = a(aD_{n-2}+a^{n-1})+a^n\\\\
	=a^{n-1}D_1+(n-1)a^n=2a·a^n+(n-1)a^n=(n+1)a^n(n\geq 3)
\end{gather*}
$$

## 抽象型行列式计算

### 行列式与矩阵

设A，B为三阶正交矩阵，且|A|+|B|=0，则|A+B|=
$$
\begin{gather*}
|A+B|=|EA+BE|=|BB^TA+BA^TA|\\\\
=|B(B^T+A^T)A|=|B||A+B||A|=-|A+B|
\end{gather*}
$$
### 行列式与向量

设4阶矩阵$A=(\alpha,\gamma_1,2\gamma_2,3\gamma_3),B=(\beta,\gamma_1,-\gamma_2,\gamma_3)$，其中$\alpha,\beta,\gamma_1,\gamma_2,\gamma_3$均为4维列向量，且已知行列式|A|=6，|B|=2，则行列式|A+B|=
$$
\begin{gather*}
|A|=|\alpha,\gamma_1,2\gamma_2,3\gamma_3|=6|\alpha,\gamma_1,\gamma_2,\gamma_3|=6\\\\
|B|=|\beta,\gamma_1,-\gamma_2,\gamma_3|=-|\beta,\gamma_1,\gamma_2,\gamma_3|=-2\\\\
|A+B|=|\alpha+\beta,2\gamma_1,\gamma_2,4\gamma_3|=8|\alpha+\beta,\gamma_1,\gamma_2,\gamma_3|\\\\
=8\times (1-2)=-8
\end{gather*}
$$

### 行列式与方程组

方程组$\left\{\begin{matrix}ax_1+x_3=1\\x_1+ax_2+x_3=0\\x_1+2x_2+ax_3=0\\ax_1+bx_2=2\end{matrix}\right.$，有解，其中a,b为常数，若$\begin{vmatrix}a&0&1\\1&a&1\\1&2&a\end{vmatrix}=4$，$\begin{vmatrix}1&a&1\\1&2&a\\a&b&0\end{vmatrix}=$
 - 题目中的两个行列式均在方程组增广矩阵中，又方程组有解所以方程组矩阵秩为3，所以增广矩阵的行列式=0，则将增广矩阵按最后一列展开，求解

### 行列式与特征值、特征向量

已知A为三阶矩阵，$\alpha_1,\alpha_2,\alpha_3$是三维线性无关的特征向量，若$A\alpha_1=\alpha_1-\alpha_2,A\alpha_2=\alpha_2-\alpha_3,A\alpha_3=\alpha_3+\alpha_1$，则|A+2E|=
$$
\begin{gather*}
	(A\alpha_1,A\alpha_2,A\alpha_3)=(\alpha_1-\alpha_2,\alpha_2-\alpha_3,\alpha_1+\alpha_3)\\\\
	\rightarrow A(\alpha_1,\alpha_2,\alpha_3)=
	(\alpha_1,\alpha_2,\alpha_3)
	\begin{bmatrix}
		1&0&1\\
		-1&1&0\\
		0&-1&1
	\end{bmatrix}\\\\
	\rightarrow A相似于C \rightarrow |A+2E|=|C+2E|=28
\end{gather*}
$$

## 行列式与高数结合

求解多项式中某项的系数，可以利用逆序数定义快速求解

多项式$f(x)=\begin{vmatrix}x&x&1&2x\\1&x&2&-1\\2&1&x&1\\2&-1&1&x\end{vmatrix}$的$x^3$项的系数为
 - 暴力解也行，或者使用逆序数


# 逆序数的应用

## 排列与逆序数

由1，2...n组成的一个有序组，称为一个**n级排列**，常用$j_1j_2...j_n$表示，在一个n级排列$j_1j_2...j_n$中，如果较大的数排在较小的数前面，则称$j_s,j_t$构成一个**逆序**，一个排列的逆序总和称为这个排列的**逆序数**，记作$\tau(j_1...j_n)$

逆序数为奇数的排列称为**奇排列**，逆序数为偶数的排列称为**偶排列**
 - *注：在5级排列32154中，有逆序32，31，21，54，故逆序数$\tau(32154)=4$，则32154为偶排列*
 - *注2：两个特殊的排列*：
    1. n级自然排列123...n的逆序数$\tau(123...n)=0$，为偶排列
    2. n级排列$n(n-1)(n-2)...321$的逆序数$\tau(n(n-1)(n-2)...321)=\frac{n(n-1)}{2}$，其排列的奇偶性与n有关

## n阶行列式逆序数定义

$$
D_n=
\begin{gather*}
	\begin{vmatrix}
		a_{11}&a_{12}&...&a_{1n}\\
		a_{21}&a_{22}&...&a_{2n}\\
		...&...&...&...\\
		a_{n1}&a_{n2}&...&a_{nn}
	\end{vmatrix}=\sum_{j_1j_2...j_n}(-1)^{\tau(j_1j_2...j_n)}a_{1j_1}a_{2j_2}...a_{nj_n}
\end{gather*}
$$
它表示所有取自不同行、不同列的n个元素乘积的代数和
**特点**：
 1. 每一项$a_{1j_1}a_{2j_2}...a_{nj_n}$都是**不同行、不同列**的n个元素的乘积，$j_1j_2...j_n$是n级排列
 2. 各项的符号由列标排列$j_1...j_n$的逆序数决定：当该排列为偶排列时为正，为奇排列时为负
 3. $\sum_{j_1...j_n}$表示对所有的n级排列求和，展开式中有n!项


# 矩阵复习

##### 9.7

## 矩阵乘法

**矩阵的数乘**：$|k·A|=k^n|A|$

<span style="color:red;font-weight:bold">矩阵的伪消去律</span>：AB=AC，当A==可逆==的时候，两边可消去A
 - 其实当A列满秩的时候就可以消去了
    - **推导**：$A(B-C)=0\Rightarrow r(A)=r(B-C)\leq n$，又A列满秩$\Rightarrow r(B-C)=0\Rightarrow B-C=0$，从而得出B=C
 - 同理，BA=CA，当A行满秩时就可以消去

## 转置、伴随、逆、正交

### 转置矩阵

**结论1**：B是一个m×n矩阵，则$B^TB和BB^T$都是**对称矩阵**

**结论2**：对于反对称矩阵而言，必有**主对角线元素为0**
 - 反对称矩阵若是**奇数阶**的话，==行列式必为0==
 - 对于反对称矩阵A，$\forall x$有$x^TAx=0$

**结论3**：对于任意的n阶方阵，$A+A^T$总是一个对称矩阵，$A-A^T$是反对称矩阵

### 伴随矩阵

二阶矩阵的伴随矩阵（主对调，副变号）
$$
\begin{gather*}
	\begin{bmatrix}
		a&b\\
		c&d
	\end{bmatrix}^*
	=
	\begin{bmatrix}
		d&-b\\
		-c&a
	\end{bmatrix}
\end{gather*}
$$

遇到$A^*$的题从以下几种情况分析：
 1. 代数余子式
 2. $AA^*=A^*A=|A|E$
     - 特别的，当|A|=0时，得到$A^*A=0$，即A的每一列均为$A^*x=0$的解
 3. 从$r(A^*)与r(A)$的关系进行分析
 4. 从$A^*,A$特征值、特征向量的关系进行分析

### 逆矩阵
$$
A^{-1}=\dfrac{1}{|A|}A^*
$$
### 正交矩阵
$$
若n阶矩阵满足Q^TQ=E，则Q是正交矩阵
$$

## 矩阵常用公式

*方阵才谈行列式、伴随矩阵、逆矩阵*
![[矩阵]]

# 代数余子式与伴随矩阵

*遇到余子式或代数余子式的问题，可以从两个角度考虑：*
 1. 构造一个新的行列式求解
 2. 向**伴随矩阵**转化

# 矩阵的逆

**常考题型**：
 1. 考察逆矩阵的性质
     1. A，B为n阶，给出AB=E，得出BA=E（可交换）
     2. 伪消去律
     3. 等价说法：A为n阶，$A可逆\Leftrightarrow|A|\neq0\Leftrightarrow r(A)=n\Leftrightarrow A无0特征值$
 2. 考察具体型逆矩阵的求法
 3. 考察抽象型逆矩阵的求法
     - 想办法凑出形如==AB=E==的形态
 4. 判断是否可逆

**常用公式**：
$$
B^n-E^n=(B-E)(B^{n-1}+B^{n-2}+...+B+E)
$$
*特别的：n为奇数时*
$$
B^n+E^n=(B+E)(B^{n-1}-B^{n-2}+B^{n-3}-B^{n-4}+...+B^2-B+E)
$$

**判断矩阵可逆**：三板斧
 1. $|A|\neq0$
2. 满秩即可逆
3. 特征值不为0

# 矩阵的高次幂

##### 9.8

**定义**：设A是n阶矩阵，k个A连乘的乘积称为A的k次幂

当m，k为正整数时，有$\left\{\begin{matrix}A^mA^k=A^{m+k}\\(A^m)^k=A^{mk}\end{matrix}\right.$

遇到高次幂的题型，考虑以下情况：
 1. 幂0矩阵
 2. 二项展开型
 3. 秩为1矩阵
若不为上述三种，则：
 4. 试算法
 5. 矩阵相似对角化

## <span style="color:red;font-weight">秩为1矩阵</span>

若矩阵A的秩$r(A)=1$，则A一定可以拆分成一个列向量和一个行向量的乘积
$$
\begin{gather*}
	\begin{bmatrix}
		a_1b_1&a_1b_2&a_1b_3\\
		a_2b_1&a_2b_2&a_2b_3\\
		a_3b_1&a_3b_2&a_3b_3\\
	\end{bmatrix}=
	\begin{bmatrix}
		a_1\\a_2\\a_3
	\end{bmatrix}
	\begin{bmatrix}
		b_1&b_2&b_3
	\end{bmatrix}=\alpha\beta^T
\end{gather*}
$$

**相关结论**：
 1. $tr(A)=\alpha^T\beta=\beta^T\alpha=l$ 都是同一个数
 2. 此时，A满足$A^2=lA$，从而$A^n=l^{n-1}A$

# 初等矩阵与初等变换

**初等矩阵**：单位矩阵经过一次初等变换所得的矩阵

**初等变换**：
 1. 对换变换：交换矩阵A的两行位置
 2. 倍乘变换：用一非零常数乘以A的某一行
 3. 倍加变换：把矩阵A的某一行的k倍加到矩阵A的另外一行上去

**定理1**：设A是m×n的矩阵，对A实施一次初等**列**变换，相当于在A的**右边**乘以相应的n阶初等矩阵，同理，对A实施一次初等**行**变换，相当于在A的**左边**乘以相应的m阶初等矩阵

**定理2**：设A是m×n的矩阵，皆可经过有限次初等行变换化为行阶梯型矩阵或行最简形矩阵

**定理3**：对于任意的m×n的矩阵，总存在行最简矩阵U和m阶初等矩阵$P_1P_2P_3...P_s$使得
$$
P_s...P_2P_1A=U
$$

**定理4**：对于任意的m×n的矩阵A，总可经过有限次初等变换变为标准型矩阵（标准型是唯一的），由m，n，r唯一确定
$$
\begin{gather*}
E_{m\times n}^{(r)}=
\begin{bmatrix}
	E_r&O\\
	O&O\\
\end{bmatrix}_{m\times n}
\end{gather*}
$$

**定理5**：可逆矩阵A可以表示为若干个初等矩阵的乘积

![[初等矩阵的行列式、逆矩阵、转置矩阵]]

**总结**：
 1. 求逆矩阵，解方程，只作**初等行变换**
 2. 求矩阵标准型，求矩阵的秩**行列变换均可**

# 矩阵乘法进阶

**结论1**：若A是m×n的矩阵，B是n×s的矩阵，且AB=O，对B和O矩阵按列分块有：
 1. $r(A)+r(B)\leq n$
 2. 特征值，特征向量角度：$b_1,b_2...b_s$是A对应于**0特征值**的特征向量
$$
AB=A[b_1,b_2...b_s]=[Ab_1,Ab_2...Ab_s]=[0,0...0]
$$
$$
Ab_i=0(i=1,2,...,s)
$$
即==B的**列向量**是齐次方程组Ax=0的解==

**结论2**：若A是m×n的矩阵，对A进行行分块，其次方程组Ax=0可表示为：
 - 若题目出现“正交”，可能需要从这个角度解题
$$
\begin{gather*}
	\begin{bmatrix}
		\alpha_1^T\\
		\alpha_2^T\\
		...\\
		\alpha_m^T
	\end{bmatrix}x=
	\begin{bmatrix}
		0\\0\\...\\0
	\end{bmatrix}
\end{gather*}
$$
即==A的所有**行向量**均与解向量x正交==

**结论3**：若AB=C，A是m×n的矩阵，B是n×s的矩阵，对矩阵AC分块，有：
$$
\begin{gather*}
	\begin{bmatrix}
		\alpha_1&\alpha_2&...&\alpha_n
	\end{bmatrix}
	\begin{bmatrix}
		b_{11}&b_{12}&...&b_{1s}\\
		b_{21}&b_{22}&...&b_{2s}\\
		...&...&...&...\\
		b_{n1}&b_{n2}&...&b_{ns}
	\end{bmatrix}=
	\begin{bmatrix}
		c_1&c_2&...&c_s
	\end{bmatrix}
	\\\\由此得出：
	\left
	\{
	\begin{matrix}
		b_{11}\alpha_1+b_{21}\alpha_2+...+b_{n1}\alpha_n=c_1\\
		b_{12}\alpha_1+b_{22}\alpha_2+...+b_{n2}\alpha_n=c_2\\
		...\\
		b_{1s}\alpha_1+b_{2s}\alpha_2+...+b_{ns}\alpha_n=c_s\\
	\end{matrix}
	\right.
\end{gather*}
$$
即==矩阵AB的**列向量**可由**A**的**列向量**表示==
**同理可得**：==矩阵AB的**行向量**可由**B**的**行向量**线性表示==

# <span style="color:red">矩阵的秩</span>

**定义**：若A是m×n的矩阵，如果A中不为0的子式的最高阶数为r，即存在r阶子式不为0，而任何r+1的子式均为0，则称r为矩阵A的秩

**秩的等价说法**：
$$
\left
\{
\begin{matrix}
	r(A)=r\Leftrightarrow A中至少有r阶子式不为0\\
	r(A)\leq r\Leftrightarrow A中任意r阶以上的子式全为0\\
	r(A)\geq r\Leftrightarrow A中至少有一个r阶子式不为0
\end{matrix}
\right.
$$
## 秩的相关结论

![[秩的相关结论]]

**结论**：若n阶矩阵满足$(A-aE)(A-bE)=O$，且$a\neq b$，则有$r(A-aE)+r(A-bE)=n$
 - **证明**：由$(A-aE)(A-bE)=O$得$r(A-aE)+r(A-bE)\leq n$，
   即要证$r(A-aE)+r(A-bE)=n$，
   只需证$r(A-aE)+r(A-bE)\geq n$即可，
   由$r(A±B)\leq r(A)+r(B)$
   可知：$r(A-aE)+r(A-bE)\geq r[(A-aE)-(A-bE)]=r[(b-a)E]=n(a\neq b)$，故得证

# <span style="color:red">分块矩阵</span>

**拉普拉斯公式**：
1.  $\begin{gather*}\begin{bmatrix}A_m&O\\ *&B_n\end{bmatrix}=|A|·|B|,\begin{bmatrix}A_m&*\\O&B_n\end{bmatrix}=|A|·|B|\end{gather*}$
2. $\begin{gather*}\begin{bmatrix}O&A_m\\ B_n&* \end{bmatrix}=(-1)^{mn}|A|·|B|,\begin{bmatrix}*&A_m\\B_n&O\end{bmatrix}=(-1)^{mn}|A|·|B|\end{gather*}$

**分块对角矩阵的幂**：
$$
\begin{gather*}
	\begin{bmatrix}
		A_1& & &\\
		 &A_2& &\\
		 & & ... &\\
		 & & &A_n
	\end{bmatrix}=
		\begin{bmatrix}
		A_1^n& & &\\
		 &A_2^n& &\\
		 & & ... &\\
		 & & &A_n^n
	\end{bmatrix}
\end{gather*}
$$
*分块副对角矩阵的幂没有这个规律*

**分块对角矩阵的逆**：若B，C均为m阶与n阶的可逆矩阵，则$$
\begin{gather*}
	\begin{bmatrix}
		B&O\\O&C
	\end{bmatrix}^{-1}=
	\begin{bmatrix}
		B^{-1}&O\\O&C^{-1}
	\end{bmatrix}\\\\
	\begin{bmatrix}
		O&B\\C&O
	\end{bmatrix}^{-1}=	
	\begin{bmatrix}
		O&C^{-1}\\
		B^{-1}&O
	\end{bmatrix}
\end{gather*}
$$
**分块矩阵的转置**：大转+小转
$$
\begin{gather*}
\begin{bmatrix}A&B\end{bmatrix}^T=\begin{bmatrix}A^T\\B^T\end{bmatrix}\\\\
\begin{bmatrix}A\\B\end{bmatrix}^T=\begin{bmatrix}A^T&B^T\end{bmatrix}
\end{gather*}
$$
![[分块矩阵的广义初等变换]]

**分块矩阵的秩**：
 1. $\begin{gather*}r\begin{bmatrix}A&O\\O&B\end{bmatrix}=r\begin{bmatrix}O&A\\B&O\end{bmatrix}=r(A)+r(B)\end{gather*}$
 2. $\begin{gather*}r\begin{bmatrix}A&C\\O&B\end{bmatrix}\geq r(A)+r(B),r\begin{bmatrix}A&O\\C&B\end{bmatrix}\geq r(A)+r(B)\end{gather*}$
     - ==取等号的条件==：<span style="color:red">C的行可由A的行表示，或者C的列可由B的列表示</span>，当**A可逆**或**B可逆**时，等号一定成立




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