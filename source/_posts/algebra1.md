---
title: 六校联合夏令营习题
date: 2026-09-08
tags:
  - 多项式
  - 线性代数
mathjax: true
---

# 代数



---

## T1

证明：

$$
Ax=b\ \text{有解}
\iff
\begin{pmatrix}
A^T\\
b^T
\end{pmatrix}x
=
\begin{pmatrix}
O\\
1
\end{pmatrix}
\ \text{无解}.
$$

Proof:

$$
\operatorname{rank}
\begin{pmatrix}
A^T & O\\
b^T & 1
\end{pmatrix}
=
\operatorname{rank}(A^T)+1
=
\operatorname{rank}A+1.
$$

### $(\Rightarrow)$

若 $Ax=b$ 有解，则

$$
\operatorname{rank}A=\operatorname{rank}(A,b).
$$

于是

$$
\operatorname{rank}
\begin{pmatrix}
A^T\\
b^T
\end{pmatrix}
=
\operatorname{rank}(A,b)
=
\operatorname{rank}A
\neq
\operatorname{rank}A+1
=
\operatorname{rank}
\begin{pmatrix}
A^T&O\\
b^T&1
\end{pmatrix},
$$

故

$$
\begin{pmatrix}
A^T\\
b^T
\end{pmatrix}x
=
\begin{pmatrix}
O\\
1
\end{pmatrix}
$$

无解。

### $(\Leftarrow)$

由无解可得

$$
\operatorname{rank}
\begin{pmatrix}
A^T\\
b^T
\end{pmatrix}
\le
\operatorname{rank}
\begin{pmatrix}
A^T&O\\
b^T&1
\end{pmatrix}
-1.
$$

因此

$$
\operatorname{rank}(A,b)\le \operatorname{rank}A.
$$

另一方面总有

$$
\operatorname{rank}A\le \operatorname{rank}(A,b),
$$

所以

$$
\operatorname{rank}A=\operatorname{rank}(A,b),
$$

从而 $Ax=b$ 有解。

---

## T2

设

$$
A_1,A_2,\dots,A_{2017}
$$

为 $2016$ 阶实矩阵，证明方程

$$
\left|x_1A_1+x_2A_2+\cdots+x_{2017}A_{2017}\right|=0
$$

有非零解。

Proof:记 $P_i$ 为 $A_i$ 的第一列，考虑

$$
\sum_{i=1}^{2017}x_iP_i=0.
$$

等价于

$$
(P_1,P_2,\dots,P_{2017})
\begin{pmatrix}
x_1\\
x_2\\
\vdots\\
x_{2017}
\end{pmatrix}
=0.
$$

令

$$
B=(P_1,P_2,\dots,P_{2017}),\qquad
x=
\begin{pmatrix}
x_1\\
x_2\\
\vdots\\
x_{2017}
\end{pmatrix}.
$$

由于

$$
\operatorname{rank}B\le 2016<2017,
$$

故齐次方程 $Bx=0$ 有非零解。

对这样的非零 $x$，矩阵

$$
x_1A_1+\cdots+x_{2017}A_{2017}
$$

的第一列为零，因此其行列式为零。

---

## T3

设

$$
B(t)=\bigl(b_{ij}(t)\bigr)_{n\times n},
\qquad
b(t)=
\begin{pmatrix}
b_1(t)\\
b_2(t)\\
\vdots\\
b_n(t)
\end{pmatrix},
$$

其中 $b_{ij}(t),b_i(t)$ 均为实系数多项式。

记

$$
d(t)=|B(t)|,
$$

以及

$$
d_i(t)=|B_i(t)|,
$$

其中 $B_i(t)$ 表示将 $B(t)$ 的第 $i$ 列替换为 $b(t)$ 所得矩阵。

若 $d(t)$ 有实根 $t_0$，且

$$
B(t_0)x=b(t_0)
$$

有解，证明 $d(t),d_1(t),\dots,d_n(t)$ 有非平凡公因式。

Proof:由方程有解，

$$
\operatorname{rank}(B(t_0),b(t_0))
=
\operatorname{rank}B(t_0).
$$

又因为

$$
d(t_0)=|B(t_0)|=0,
$$

所以 $B(t_0)$ 不可逆，即

$$
\operatorname{rank}B(t_0)<n.
$$

对任意 $i$，由增广矩阵的列替换关系可得

$$
\operatorname{rank}B_i(t_0)<n,
$$

故

$$
d_i(t_0)=|B_i(t_0)|=0.
$$

于是

$$
t-t_0\mid d(t),\qquad
t-t_0\mid d_i(t)\quad(i=1,\dots,n).
$$

所以 $t-t_0$ 是

$$
d(t),d_1(t),\dots,d_n(t)
$$

的非平凡公因式。

---

## T4

设

$$
A\in\mathbb C^{n\times n},
$$

$p(x)$ 为 $A\bar A$ 的特征多项式。证明 $p(x)$ 为实系数多项式。

Proof:

$$
\overline{p(\bar x)}
=
\overline{\left|\bar xI-A\bar A\right|}
=
\left|xI-\bar A A\right|.
$$

又利用

$$
|xI-\bar A A|
=
|xI-A\bar A|,
$$

得到

$$
\overline{p(\bar x)}=p(x).
$$

因此 $p(x)$ 的系数均为实数。

---

## T5

设 $n$ 为奇数，且

$$
A,B\in\mathbb R^{n\times n},
\qquad
AB=0.
$$

设 $A+J_A$ 的特征值集合为 $S_1$，$B+J_B$ 的特征值集合为 $S_2,J_A,J_B$均为$jordon$标准型.

证明

$$
0\in S_1\cup S_2.
$$

Proof:由

$$
AB=0
$$

可得

$$
\operatorname{rank}A+\operatorname{rank}B\le n.
$$

不妨设

$$
\operatorname{rank}A\le \frac n2.
$$

由于 $n$ 为奇数，

$$
\operatorname{rank}A<\frac n2.
$$



$$
\operatorname{rank}J_A=\operatorname{rank}A
$$

于是

$$
\operatorname{rank}(A+J_A)
\le
\operatorname{rank}A+\operatorname{rank}J_A
<n.
$$

故 $A+J_A$ 不可逆，因此 $0$ 为 $A+J_A$ 的特征值，即

$$
0\in S_1.
$$



---

## T6

记

$$
M_n(\mathbb C)
$$

为 $n$ 阶复方阵的集合。设

$$
\varnothing\ne I\subseteq M_n(\mathbb C),
$$

对减法封闭，特别地：

若 $A\in I$，则对任意

$$
B,C\in M_n(\mathbb C)
$$

有

$$
BAC\in I.
$$

证明

$$
I=\{0\}
\quad\text{或}\quad
I=M_n(\mathbb C).
$$

Proof:显然 $0\in I$。若存在

$$
0\ne A=(a_{ij})\in I,
$$

则存在 $a_{ij}\ne0$。

利用矩阵单位 $E_{pq}$，

$$
E_{pi}AE_{jq}=a_{ij}E_{pq}\in I.
$$

若$A,B$ $\in I$,则 

$$
- B = O- B \in I,
$$

$$
 A+B=A-(-B) \in I.
$$ 

即$I$对加法封闭.

若 $A\in I$,则

$$
(\lambda I)AI \in I
$$

即$I$对数乘封闭.
$$
E_{pq}
=
\frac1{a_{ij}}\bigl(a_{ij}E_{pq}\bigr)
\in I.
$$

因此所有矩阵单位 $E_{pq}$ 都属于 $I$。

又由加法与数乘封闭，对任意

$$
X=(x_{ij})\in M_n(\mathbb C),
$$

有

$$
X
=
\sum_{i,j=1}^n x_{ij}E_{ij}
\in I.
$$

故

$$
I=M_n(\mathbb C).
$$

---

## T7

设 $n,l$ 为正整数,证明存在

$$
X\in M_m(\mathbb C)
$$

满足

$$
X^n+X^L=
\begin{pmatrix}
1\\
2&1\\
\vdots&\ddots&\ddots\\
m&\dots&2&1
\end{pmatrix}
+I
$$

Proof:题目等价于

$$
X^n+X^l
=
2I+2N+3N^2+\cdots+mN^{m-1},
$$

其中

$$
N=
\begin{pmatrix}
0\\
1&0\\
&\ddots&\ddots\\
&&1&0
\end{pmatrix},
N^m=0.
$$

令

$$
X
=
I+a_1N+a_2N^2+\cdots+a_{m-1}N^{m-1}
=
I+U.
$$

则

$$
X^r=(I+U)^r
=
\sum_{j=0}^r\binom rj U^j.
$$

在 $X^r$ 中：

- $N$ 的系数为 $ra_1$；
- $N^2$ 的系数为
  $$
  ra_2+\binom r2a_1^2;
  $$
- $N^3$ 的系数为
  $$
  ra_3+r(r-1)a_1a_2+\binom r3a_1^3.
  $$

一般地，$N^k$ 的系数是 $a_1,\dots,a_k$ 的多项式，且关于 $a_k$ 的项只有

$$
ra_k.
$$

记为

$$
ra_k+f_{r,k}(a_1,\dots,a_{k-1}).
$$

要求 $X^{n+l}+X^l$ 中 $N^k$ 的系数为 $k+1$，于是

$$
(n+l)a_k
+
f_{n,k}(a_1,\dots,a_{k-1})
+
f_{l,k}(a_1,\dots,a_{k-1})
=
k+1.
$$



因此

$$
a_k
=
\frac{
k+1
-
f_{n,k}(a_1,\dots,a_{k-1})
-
f_{l,k}(a_1,\dots,a_{k-1})
}{
n+l
}.
$$

由 $a_1,\dots,a_{k-1}$ 可递推确定 $a_k$，故可逐次构造所需的 $X$。

---

## T8

设

$$
A=(a_{ij})_{n\times n},
\qquad
FA=AF.
$$

证明

$$
A
=
a_{n1}F^{n-1}
+
a_{n-1,1}F^{n-2}
+\cdots+
a_{21}F
+
a_{11}I.
$$

其中 $F$ 为 $n$ 次首一多项式

$$
x^n+a_{n-1}x^{n-1}+\cdots+a_1x+a_0
$$

的友阵。

Proof:

$$
Fe_1=e_2,\quad
Fe_2=e_3,\quad
\dots,\quad
Fe_{n-1}=e_n,
$$

故

$$
e_k=F^{k-1}e_1.
$$

另一方面，

$$
Ae_1
=
\begin{pmatrix}
a_{11}\\
a_{21}\\
\vdots\\
a_{n1}
\end{pmatrix}
=
a_{11}e_1+a_{21}e_2+\cdots+a_{n1}e_n.
$$

因此

$$
Ae_1
=
\left(
a_{n1}F^{n-1}
+
a_{n-1,1}F^{n-2}
+\cdots+
a_{21}F
+
a_{11}I
\right)e_1.
$$

又由 $AF=FA$，

$$
Ae_2
=
AFe_1
=
FAe_1,
$$

依次得到同一多项式在 $e_2,\dots,e_n$ 上也与 $A$ 的作用相同。

因此

$$
\boxed{
A
=
a_{n1}F^{n-1}
+
a_{n-1,1}F^{n-2}
+\cdots+
a_{21}F
+
a_{11}I
}.
$$

---

## T9

设

$$
a\in\mathbb R,\qquad a\ne0,
$$

$A$ 为 $n$ 阶实反对称矩阵：

$$
A=-A^T.
$$

记

$$
\Gamma
=
\left\{
(x,y)\mid
x,y\in\mathbb R^{n\times n},
\ xy=aI+A
\right\}.
$$

任取

$$
(x,y),(M,N)\in\Gamma,
$$

证明

$$
xN+y^TM^T\ne0.
$$

Proof:反证法，设

$$
xN+y^TM^T=0.
$$

转置得

$$
My+N^Tx^T=0.
$$

又

$$
y^Tx^T
=
(xy)^T
=
aI+A^T
=
aI-A.
$$

于是

$$
\begin{pmatrix}
x&y^T\\
M&N^T
\end{pmatrix}
\begin{pmatrix}
y&N\\
x^T&M^T
\end{pmatrix}
=
\begin{pmatrix}
2aI&0\\
0&2aI
\end{pmatrix}.
$$

反向相乘也得到

$$
\begin{pmatrix}
y&N\\
x^T&M^T
\end{pmatrix}
\begin{pmatrix}
x&y^T\\
M&N^T
\end{pmatrix}
=
\begin{pmatrix}
2aI&0\\
0&2aI
\end{pmatrix}.
$$

从而有

$$
yy^T+NN^T=0,
$$

以及

$$
x^Tx+M^TM=0.
$$

取迹：

$$
\operatorname{tr}(yy^T)+\operatorname{tr}(NN^T)=0,
$$

$$
\operatorname{tr}(x^Tx)+\operatorname{tr}(M^TM)=0.
$$

由于

$$
\operatorname{tr}(CC^T)=\sum_{i,j}c_{ij}^2\ge0,
$$

故

$$
x=y=N=M=0.
$$

于是

$$
xy=0=aI+A.
$$

取迹：

$$
\operatorname{tr}(aI+A)
=
\operatorname{tr}(aI)
=
na\ne0,
$$

矛盾。

故

$$
xN+y^TM^T\ne0.
$$

---

## T10

设 $f,g$ 是复域有限维线性空间 $V$ 上的线性变换，并满足

$$
fg-gf=f.
$$

证明：

1. $f$ 为幂零变换；
2. $f,g$ 有公共特征向量。

Proof:首先

$$
\operatorname{tr}f
=
\operatorname{tr}(fg-gf)
=
\operatorname{tr}(fg)-\operatorname{tr}(gf)
=
0.
$$

并且对 $1\le m\le n=\dim V$，

$$
\operatorname{tr}(f^m)
=
\operatorname{tr}\bigl(f^mg-f^{m-1}gf\bigr)
=
0.
$$

设

$$
\lambda_1,\lambda_2,\dots,\lambda_n
$$

为 $f$ 的特征值，则

$$
\lambda_1^m+\lambda_2^m+\cdots+\lambda_n^m=0,
\qquad
1\le m\le n.
$$

由 Newton 恒等式可知所有基本对称多项式均为零，因此

$$
\chi_f(x)
=
\prod_{i=1}^n(x-\lambda_i)
=
x^n.
$$

由 Cayley–Hamilton 定理，

$$
f^n=0,
$$

故 $f$ 幂零。

于是

$$
\ker f\ne\{0\}.
$$

对任意

$$
\alpha\in\ker f,
$$

有

$$
f(g\alpha)
=
fg\alpha
=
(f+gf)\alpha
=
0.
$$

所以

$$
g\alpha\in\ker f,
$$

即 $\ker f$ 是 $g$ 的不变子空间。

考虑限制映射

$$
g|_{\ker f}.
$$

由于底域为 $\mathbb C$，它存在特征向量 $\alpha\ne0$。

同时

$$
f(\alpha)=0,
$$

因此 $\alpha$ 也是 $f$ 对应特征值 $0$ 的特征向量。

故 $f,g$ 有公共特征向量。

---

## T11

设 $n$ 阶方阵 $A$ 的 $n$ 个特征值均为偶数

证明矩阵方程

$$
X+AX=XA^2
$$

只有零解。

Proof:等价地，

$$
(I+A)X=XA^2.
$$

设 $A$ 的特征值为

$$
\lambda_1,\lambda_2,\dots,\lambda_n.
$$

则

$$
I+A
$$

的特征值为

$$
1+\lambda_1,\dots,1+\lambda_n,
$$

而 $A^2$ 的特征值为

$$
\lambda_1^2,\dots,\lambda_n^2.
$$

由

$$
(I+A)X=XA^2
$$

反复迭代可得

$$
(I+A)^kX=X(A^2)^k.
$$

记

$$
B=I+A,\qquad C=A^2,
$$

则

$$
BX=XC,
\qquad
B^kX=XC^k.
$$

$B$ 的特征多项式为

$$
\varphi_B(x)
=
\prod_{i=1}^n
\bigl(x-(\lambda_i+1)\bigr).
$$

由 Cayley–Hamilton，

$$
0
=
\varphi_B(B)X
=
X\varphi_B(C)
=
X\prod_{i=1}^n
\bigl(C-(\lambda_i+1)I\bigr).
$$

而

$$
C-(\lambda_i+1)I
$$

的特征值为

$$
\lambda_j^2-\lambda_i-1.
$$

由于各 $\lambda_i,\lambda_j$ 均为偶数，

$$
\lambda_j^2-\lambda_i-1
$$

为奇数，因而不为 $0$。

所以每个

$$
C-(\lambda_i+1)I
$$

均可逆，其乘积也可逆。

故

$$
X=0.
$$

---

## T12

设

$$
A\in\mathbb C^{4\times4},
$$

且

$$
\operatorname{tr}(A^i)=i,
\qquad i=1,2,3,4.
$$

求

$$
|A|.
$$

Proof:设 $A$ 的特征值为

$$
\lambda_1,\lambda_2,\lambda_3,\lambda_4.
$$

则

$$
\lambda_1+\lambda_2+\lambda_3+\lambda_4=1,
$$

$$
\lambda_1^2+\lambda_2^2+\lambda_3^2+\lambda_4^2=2,
$$

$$
\lambda_1^3+\lambda_2^3+\lambda_3^3+\lambda_4^3=3,
$$

$$
\lambda_1^4+\lambda_2^4+\lambda_3^4+\lambda_4^4=4.
$$

由 Newton 恒等式依次得到

$$
e_1=1,
$$

$$
e_2=-\frac12,
$$

$$
e_3=\frac16,
$$

$$
e_4=\frac1{24}.
$$

而

$$
|A|
=
\lambda_1\lambda_2\lambda_3\lambda_4
=
e_4,
$$

故

$$
\boxed{|A|=\frac1{24}}.
$$

---

## T13

设 $A$ 为实方阵，且对任意实向量 $\alpha$，

$$
\alpha^TA\alpha\ge0.
$$

且若

$$
x^TAy\ne0
\Longrightarrow
x^TAy+y^TAx\ne0.
$$

设存在

$$
\beta\ne0,
\qquad
\beta^TA\beta=0.
$$

证明任意的$v$

$$
v^TA\beta=0.
$$

Proof：令

$$
B=\frac{A+A^T}{2}.
$$

则

$$
\alpha^TB\alpha
=
\alpha^TA\alpha
\ge0,
$$

故 $B$ 为实对称半正定矩阵。

取可逆矩阵 $T$，使

$$
T^TBT
=
\begin{pmatrix}
I_r&0\\
0&0
\end{pmatrix}.
$$

设

$$
T^{-1}\beta
=
\begin{pmatrix}
b_1\\
\vdots\\
b_r\\
b_{r+1}\\
\vdots\\
b_n
\end{pmatrix}
=
\begin{pmatrix}
P\\
Q
\end{pmatrix}.
$$

由

$$
\beta^TB\beta=0
$$

得到

$$
b_1^2+\cdots+b_r^2=0,
$$

于是

$$
b_1=\cdots=b_r=0,
\qquad
P=0.
$$

因此

$$
B\beta=0.
$$

故对任意 $v$，

$$
v^TB\beta=0,
$$

也即

$$
v^TA\beta+v^TA^T\beta=0.
$$

若存在 $v$ 使

$$
v^TA\beta\ne0,
$$

则由题设条件应有

$$
v^TA\beta+\beta^TAv\ne0.
$$

但

$$
\beta^TAv
=
(v^TA^T\beta)^T
=
v^TA^T\beta,
$$

从而

$$
v^TA\beta+\beta^TAv
=
v^TA\beta+v^TA^T\beta
=
0,
$$

矛盾。

因此对任意 $v$，

$$
v^TA\beta=0,
$$

所以

$$
A\beta=0.
$$

### 注：

设

$$
B=C^TC,
$$

则

$$
\beta^TB\beta
=
(C\beta)^T(C\beta)
=
0
$$

立即得到

$$
C\beta=0,
$$

从而

$$
B\beta=C^TC\beta=0.
$$

---

## T14

设 $A,B,C$ 正定阵，并令

$$
P(t)=At^2+Bt+C.
$$


设 $\lambda$ 是

$$
|P(t)|
$$

的根，证明

$$
\operatorname{Re}\lambda<0.
$$

因为

$$
|P(\lambda)|=0,
$$

所以 $P(\lambda)$ 不可逆，$0$ 是 $P(\lambda)$ 的特征值。

取相应非零特征向量 $\alpha$，有

$$
P(\lambda)\alpha=0.
$$

左乘 $\alpha^T$：

$$
\alpha^TP(\lambda)\alpha=0.
$$

即

$$
(\alpha^TA\alpha)\lambda^2
+
(\alpha^TB\alpha)\lambda
+
\alpha^TC\alpha
=
0.
$$

这是一个系数全为正数的实二次方程。

由二次方程根的性质（或 Vieta 定理）可得其根的实部均小于 $0$，故

$$
\boxed{\operatorname{Re}\lambda<0}.
$$

---

## T15

设

$$
A=(a_{ij})_{n\times n},
$$

满足

$$
a_{11}=a_{22}=\cdots=a_{nn}=a>0,
$$

且对任意

$$
i\in\{1,2,\dots,n\},
$$

有

$$
\sum_{j=1}^n|a_{ij}|
+
\sum_{j=1}^n|a_{ji}|
<
4a.
$$

求二次型

$$
f(x)=x^TAx
$$

的规范型。

Proof:注意

$$
x^TAx
=
x^TA^Tx
=
x^T\frac{A+A^T}{2}x.
$$

令

$$
B=\frac{A+A^T}{2}
=
(b_{ij}).
$$

则

$$
b_{ij}
=
\frac{a_{ij}+a_{ji}}2,
$$

从而

$$
|b_{ij}|
\le
\frac12\left(|a_{ij}|+|a_{ji}|\right).
$$

由题设

$$
4a
>
\sum_{j=1}^n
\left(|a_{ij}|+|a_{ji}|\right)
\ge
2\sum_{j=1}^n|b_{ij}|.
$$

故

$$
2a>\sum_{j=1}^n|b_{ij}|.
$$

又

$$
b_{ii}=a,
$$

于是

$$
b_{ii}
>
\sum_{j\ne i}|b_{ij}|.
$$

设 $\lambda$ 为 $B$ 的任意特征值。由于 $B$ 为实对称矩阵，

$$
\lambda\in\mathbb R.
$$

设

$$
\alpha=
\begin{pmatrix}
\alpha_1\\
\vdots\\
\alpha_n
\end{pmatrix}
$$

是对应的非零特征向量，取 $i$ 使

$$
|\alpha_i|=\max_{j=1}^n|\alpha_j|.
$$

由

$$
B\alpha=\lambda\alpha
$$

的第 $i$ 行，

$$
b_{i1}\alpha_1+\cdots+b_{in}\alpha_n
=
\lambda\alpha_i.
$$

故

$$
\lambda
=
b_{ii}
+
\sum_{j\ne i}
\frac{\alpha_j}{\alpha_i}b_{ij}.
$$

于是

$$
\lambda
\ge
b_{ii}
-
\sum_{j\ne i}
\left|
\frac{\alpha_j}{\alpha_i}
\right|
|b_{ij}|
\ge
b_{ii}
-
\sum_{j\ne i}|b_{ij}|
>0.
$$

所以 $B$ 的所有特征值均为正，故 $B$ 正定。

因此二次型 $f(x)$ 为正定二次型，其规范型为

$$
\boxed{
y_1^2+y_2^2+\cdots+y_n^2
}.
$$

---

## T16

### 回忆：Eisenstein 判别法

设

$$
f(x)=\sum_{i=0}^n a_ix^i\in\mathbb Z[x].
$$

若存在素数 $p$，使得

$$
p\nmid a_n,
$$

$$
p\mid a_i\qquad (0\le i<n),
$$

且

$$
p^2\nmid a_0,
$$

则 $f(x)$ 在 $\mathbb Z[x]$ 中不可约，进而在 $\mathbb Q[x]$ 中不可约。

设

$$
p_1,p_2,\dots,p_s
$$

为互不相同的素数。

证明

$$
\sqrt[n]{p_1p_2\cdots p_s}
$$

为无理数。

Proof:反证。若

$$
\sqrt[n]{p_1p_2\cdots p_s}\in\mathbb Q,
$$

则多项式

$$
x^n-p_1p_2\cdots p_s
$$

在 $\mathbb Q[x]$ 上有一次因子，因而可约。

但对任意某个 $p_i$ 使用 Eisenstein 判别法，该多项式不可约，矛盾。

故

$$
\boxed{
\sqrt[n]{p_1p_2\cdots p_s}\notin\mathbb Q
}.
$$

---

## T17

设

$$
a_1,a_2,\dots,a_n
$$

为 $n$ 个互不相同的正整数。

证明

$$
f(x)
=
\prod_{i=1}^n(x-a_i)^2+1
$$

在 $\mathbb Q[x]$ 上不可约。

Proof:反证。设

$$
f(x)=g(x)h(x)
$$

可约。由 Gauss 引理，可取

$$
g(x),h(x)\in\mathbb Z[x]
$$

为首一多项式。

对任意 $i$，

$$
f(a_i)
=
g(a_i)h(a_i)
=
1,
$$

所以

$$
g(a_i)=h(a_i)=\pm1.
$$

若存在 $i$ 使

$$
g(a_i)=h(a_i)=-1,
$$

则由首一多项式在无穷远处趋于 $+\infty$，结合介值定理，$g$ 将有实零点，从而 $f$ 有实零点。

但

$$
f(x)
=
\prod_{i=1}^n(x-a_i)^2+1
\ge1,
$$

矛盾。

故对所有 $i$，

$$
g(a_i)=h(a_i)=1.
$$

于是

$$
\prod_{i=1}^n(x-a_i)
\mid
g(x)-1,
$$

以及

$$
\prod_{i=1}^n(x-a_i)
\mid
h(x)-1.
$$

因此存在整系数多项式 $g_1,h_1$ 使

$$
g(x)
=
\prod_{i=1}^n(x-a_i)g_1(x)+1,
$$

$$
h(x)
=
\prod_{i=1}^n(x-a_i)h_1(x)+1.
$$

又

$$
\deg f=2n=\deg g+\deg h.
$$

在非平凡分解下，必有

$$
\deg g\ge n,\qquad
\deg h\ge n,
$$

故

$$
\deg g=\deg h=n.
$$

再由首一性可得

$$
g_1(x)=h_1(x)=1.
$$

所以

$$
g(x)=h(x)=\prod_{i=1}^n(x-a_i)+1.
$$

从而

$$
g(x)h(x)
=
\left(
\prod_{i=1}^n(x-a_i)+1
\right)^2
\neq
\prod_{i=1}^n(x-a_i)^2+1
=
f(x),
$$

矛盾。

故 $f(x)$ 在 $\mathbb Q[x]$ 上不可约。

---

## T18

设

$$
f(x)=\sum_{i=0}^n a_ix^i,
\qquad
a_na_0\ne0,
$$

其 $n$ 个非零互异零点为

$$
\alpha_1,\dots,\alpha_n.
$$

求以

$$
\frac1{\alpha_1},\dots,\frac1{\alpha_n}
$$

为零点的多项式。

Proof:取

$$
g(x)
=
a_0x^n+a_1x^{n-1}+\cdots+a_{n-1}x+a_n.
$$

因为

$$
f\left(\frac1x\right)
=
\sum_{i=0}^n a_i\left(\frac1x\right)^i
=
\frac1{x^n}\sum_{i=0}^n a_ix^{n-i}
=
\frac1{x^n}g(x),
$$

所以

$$
\boxed{
g(x)=x^nf\left(\frac1x\right)
}.
$$

因此若

$$
f(\alpha_i)=0,
$$

则

$$
g\left(\frac1{\alpha_i}\right)=0.
$$

所以所求多项式可取

$$
\boxed{
g(x)
=
a_0x^n+a_1x^{n-1}+\cdots+a_{n-1}x+a_n
}.
$$

### 证明：$f,g$ 有相同的可约性

若

$$
f(x)=f_1(x)f_2(x)
$$

可约，则

$$
g(x)
=
x^nf\left(\frac1x\right)
=
x^nf_1\left(\frac1x\right)f_2\left(\frac1x\right).
$$

写成

$$
g(x)
=
\left[
x^{\deg f_1}f_1\left(\frac1x\right)
\right]
\left[
x^{\deg f_2}f_2\left(\frac1x\right)
\right],
$$

即 $g$ 也可约。

反向同理，因此 $f,g$ 具有相同的可约性。

---

## T19

设

$$
f(x)
=
x^{2021}
+
a_{2020}x^{2020}
+\cdots+
a_1x+a_0
\in\mathbb Z[x],
\qquad
a_0\ne0.
$$

若对所有系数均有

$$
|a_i|\le40,
$$

证明 $f(x)$ 有非实复根。

## T19

设

$$
f(x)
=
x^{2021}
+
a_{2020}x^{2020}
+\cdots+
a_1x+a_0
\in \mathbb Z[x],
\qquad
a_0\ne0,
$$

且

$$
|a_i|\le 40.
$$

证明：$f(x)$ 有非实复根。

### 反证

假设 $f(x)$ 的根

$$
x_1,x_2,\dots,x_{2021}
$$

均为实数。

由于

$$
a_0\ne0,
$$

所以

$$
x_i\ne0,
\qquad
i=1,2,\dots,2021.
$$

考虑倒数多项式

$$
g(x)
=
a_0x^{2021}
+
a_1x^{2020}
+\cdots+
a_{2020}x
+
1.
$$

它的根为

$$
\frac1{x_i},
\qquad
i=1,2,\dots,2021.
$$

由 Cauchy–Schwarz 不等式，

$$
2021^2
=
\left(
\sum_{i=1}^{2021}
x_i\frac1{x_i}
\right)^2
\le
\left(
\sum_{i=1}^{2021}x_i^2
\right)
\left(
\sum_{i=1}^{2021}\frac1{x_i^2}
\right).
$$

由根与系数的关系，

$$
\sum_{i=1}^{2021}\frac1{x_i^2}
=
\left(
\sum_{i=1}^{2021}\frac1{x_i}
\right)^2
-
2\sum_{1\le i<j\le2021}\frac1{x_ix_j}
=
\frac{a_1^2}{a_0^2}
-
2\frac{a_2}{a_0},
$$

而

$$
\sum_{i=1}^{2021}x_i^2
=
\left(
\sum_{i=1}^{2021}x_i
\right)^2
-
2\sum_{1\le i<j\le2021}x_ix_j
=
a_{2020}^2-2a_{2019}.
$$

因此

$$
2021^2
\le
\left(
\frac{a_1^2}{a_0^2}
-
2\frac{a_2}{a_0}
\right)
\left(
a_{2020}^2-2a_{2019}
\right).
$$

又由于

$$
a_0\in\mathbb Z,\qquad a_0\ne0,
$$

故

$$
|a_0|\ge1.
$$

于是

$$
\begin{aligned}
2021^2
&\le
\left(
\frac{|a_1|^2}{|a_0|^2}
+
2\frac{|a_2|}{|a_0|}
\right)
\left(
|a_{2020}|^2+2|a_{2019}|
\right)
\\
&\le
(40^2+2\cdot40)
(40^2+2\cdot40)
\\
&=
1680^2.
\end{aligned}
$$

这与

$$
2021^2>1680^2
$$

矛盾。

因此 $f(x)$ 不可能所有根均为实数，即

$$
\boxed{f(x)\text{ 至少有一个非实复根}}.
$$

### 另一种更简单的估计

实际上，由

$$
\sum_{i=1}^{2021}x_i^2
=
a_{2020}^2-2a_{2019},
$$

可得

$$
\sum_{i=1}^{2021}x_i^2
\le
40^2+2\cdot40
=
1680.
$$

另一方面，由 AM-GM 不等式，

$$
\sum_{i=1}^{2021}x_i^2
\ge
2021
\sqrt[2021]{
\prod_{i=1}^{2021}x_i^2
}.
$$

由 Vieta 定理，

$$
\prod_{i=1}^{2021}x_i=-a_0,
$$

故

$$
\prod_{i=1}^{2021}x_i^2=a_0^2.
$$

因此

$$
\sum_{i=1}^{2021}x_i^2
\ge
2021\sqrt[2021]{a_0^2}
\ge
2021,
$$

与

$$
\sum_{i=1}^{2021}x_i^2\le1680
$$

矛盾。

---

## T20

称非常值一元 $n$ 次多项式的 $n-1$ 次项系数为其**第二项系数**。

求所有 $2020$ 次首一复系数多项式 $f(x)$，满足：

对于它的任意一个零点 $x_k$，$f(x)$ 都存在分解

$$
f(x)
=
(x-x_k)g_k(x)h_k(x),
$$

其中 $g_k(x),h_k(x)$ 均为非常值首一多项式，且二者的第二项系数相等。

设 $f(x)$ 的零点为

$$
x_1,x_2,\dots,x_{2020},
$$

并定义

$$
P_k
=
\{x_i\mid g_k(x_i)=0\},
$$

$$
Q_k
=
\{x_i\mid h_k(x_i)=0\}.
$$

则

$$
P_k\cup Q_k
=
\{x_1,x_2,\dots,x_{2020}\}\setminus\{x_k\}.
$$

由于 $g_k(x),h_k(x)$ 均为首一多项式，而首一多项式的第二项系数等于其所有根之和的相反数，因此二者第二项系数相等意味着

$$
\sum_{x_i\in P_k}x_i
=
\sum_{x_i\in Q_k}x_i.
$$

即

$$
\sum_{x_i\in P_k}x_i
-
\sum_{x_i\in Q_k}x_i
=
0.
$$

定义

$$
\varepsilon_{ki}
=
\begin{cases}
1, & x_i\in P_k,\\
-1, & x_i\in Q_k,\\
0, & i=k.
\end{cases}
$$

于是对每个 $k$，

$$
\sum_{i=1}^{2020}
\varepsilon_{ki}x_i
=
0.
$$

令

$$
E=(\varepsilon_{ki})_{2020\times2020},
$$

以及

$$
X=
\begin{pmatrix}
x_1\\
x_2\\
\vdots\\
x_{2020}
\end{pmatrix}.
$$

则

$$
EX=0.
$$

下面证明 $E$ 可逆。

考虑 $\det E$ 模 $2$。

由于

$$
1\equiv -1\pmod2,
$$

所以模 $2$ 意义下，$E$ 等价于矩阵

$$
\widetilde E
=
\begin{pmatrix}
0&1&1&\cdots&1\\
1&0&1&\cdots&1\\
1&1&0&\cdots&1\\
\vdots&\vdots&\vdots&\ddots&\vdots\\
1&1&1&\cdots&0
\end{pmatrix}.
$$

因此

$$
\det E
\equiv
\det \widetilde E
\pmod2.
$$

而

$$
\det\widetilde E
=
(-1)^{2019}\cdot2019.
$$

故

$$
\det E
\equiv
(-1)^{2019}\cdot2019
\equiv1
\pmod2.
$$

于是

$$
\det E\ne0.
$$

所以 $E$ 可逆。

由

$$
EX=0
$$

可知只有零解，因此

$$
x_1=x_2=\cdots=x_{2020}=0.
$$

故

$$
f(x)=x^{2020}.
$$

最后容易验证 $x^{2020}$ 确实满足题设条件，因此

$$
\boxed{f(x)=x^{2020}}.
$$