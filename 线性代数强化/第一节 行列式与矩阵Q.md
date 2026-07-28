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



$$
\begin{gather*}
\begin{bmatrix}

\end{bmatrix}
\end{gather*}
$$