多元统计分析
# 多元正态分布及其参数的估计
## 随机向量
均值向量和协方差阵的性质：
$$
E(AX) = AE(X),\\
E(AXB) = AE(X)B,\\
D(AX) = AD(X)A^T,\\
COV(AX, BY) = ACOV(X, Y)B^T.
$$
协方差阵对称且非负定.可以将其分解：
$$
\Sigma = L^2
$$
可以这样做：
$$
\Sigma = \Gamma
\begin{bmatrix}
\lambda _1 &  & 0 \\
 & \ddots &  \\
0 &  & \lambda _p
\end{bmatrix}\Gamma^T = \Gamma
\begin{bmatrix}
\sqrt \lambda _1 &  & 0 \\
 & \ddots &  \\
0 &  & \sqrt \lambda _p
\end{bmatrix}\Gamma^T \Gamma\begin{bmatrix}
\sqrt \lambda _1 &  & 0 \\
 & \ddots &  \\
0 &  & \sqrt \lambda _p
\end{bmatrix}\Gamma^T  =L^2
$$
其中$\Gamma$为正交矩阵

即对角化以后分解.

也可以称$L^2$为$\Sigma$的**平方根矩阵**，记为$\Sigma^{\frac{1}{2}}$.

## 多元正态分布的定义与基本性质

- $Def~1$ 
分量相互独立同$N(0,1)$分布的$q$维随机向量$U=(U_1,\cdots,U_q)^T$，$A$为$p\times q$维常数矩阵，则称$X=AU+\mu$的分布维$p$维多元正态分布，$X$为$p$维正态随机向量，记为$X\thicksim N_p(\mu, AA^T)$.
即：由$q$个相互独立的标准正态随机变量的一些线性组合所构成的随机向量的分布.
- $Def~2$
特征函数为
$$
\Phi_X(t) = exp\left[it^T\mu -\frac{1}{2}t^T\Sigma t\right] 
(\Sigma\geqslant  0)
$$
的随机向量.
- $Def~3$
任意线性组合均服从医院正态分布的随机向量.
- $Def~4$
密度为
$$
f(x) = \frac{1}{(2\pi )^{\frac{p}{2}}\left\lvert \Sigma\right\rvert ^{\frac{1}{2}}}exp\left[-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(x-\mu)\right] 
$$
的随机向量.

定义中，$\mu$为$X$的均值向量，$\Sigma$为$X$的协方差矩阵，$\Sigma = AA^T$.

## 条件分布与独立性
### 独立性
多元正态分布的分量独立$\Leftrightarrow $不相关
### 条件分布
$X = \begin{bmatrix}
	X^{(1)}\\
	X^{2}
\end{bmatrix}\thicksim N_p(\mu,\Sigma ),\Sigma \geqslant 0$，$X^{(1)}$为$r$维，$X^{(2)}$为$p-r$维向量.
则$$(X^{(1)}|X^{(2)})\thicksim N_r(\mu _{1\cdot 2},\Sigma _{11\cdot 2} )$$
其中
$$
\mu _{1\cdot 2} = \mu^{(1)} + \Sigma_{12} \Sigma _{22}^{-1}(x^{(2)}-\mu ^{(2)}),\\ \Sigma _{11\cdot 2} = \Sigma _{11}- \Sigma_{12} \Sigma_{22}^{-1}\Sigma _{21}.
$$
这里的证明可以从线性回归的思想出发.
用$X^{(2)}$预测$X^{(1)}$：
$$
X^{(1)} -\mu ^{(1)}= \beta ^T(X^{(2)}-\mu ^{(2)}) + \epsilon
$$
我们要预测得更精确则要最小化$E\epsilon ^2$.
当$E\epsilon ^2 = E\left(X^{(1)} - \beta ^TX^{(2)}\right)^T \left(X^{(1)} - \beta ^TX^{(2)}\right)$
最小时可求得$\beta = \Sigma _{22}^{-1} \Sigma _{21}$
则$$E\left(X^{(1)}|X^{(2)} \right) = E\left(\mu ^{(1)}+  \beta ^T(X^{(2)}-\mu ^{(2)}) + \epsilon\right) = \mu^{(1)} + \Sigma_{12} \Sigma _{22}^{-1}(x^{(2)}-\mu ^{(2)}),
$$
$$
Var\left(X^{(1)}|X^{(2)} \right) = Var\left(\mu ^{(1)}+  \beta ^T(X^{(2)}-\mu ^{(2)}) + \epsilon\right) = \Sigma _{11}- \Sigma_{12} \Sigma_{22}^{-1}\Sigma _{21}.$$