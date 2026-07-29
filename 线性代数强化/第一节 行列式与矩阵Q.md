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
	D_n=2(-1)^(1+1)D_{n-1}+2(-1)^{n+1}(-1)^{n-1}\\\\
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












$$
\begin{gather*}
\begin{bmatrix}

\end{bmatrix}
\end{gather*}
$$