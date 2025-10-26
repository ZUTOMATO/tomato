时间序列分析
# 时间序列
## 平稳序列
$Def$
时间序列$\left\{X_t\right\}  = \left\{ X_t|t\in \mathbb{N}\right\} $满足：
- $\forall t \in \mathbb{N}有EX_t^2 < \infty$.
- $\forall t \in \mathbb{N}有EX_t = \mu$.
- $\forall t,s \in \mathbb{N}有E\left[\left(X_t-\mu \right)\left(X_s-\mu \right) \right]  = \gamma_{t-s}$.
即：均值函数为常数且自协方差函数只与时间差有关的二阶矩时间序列为**平稳时间序列**，也称**平稳序列**.

自协方差函数的性质：
- 对称性：$\gamma _k = \gamma _{-k},~\forall k \in \mathbb{Z}$
- 非负定性：自协方差矩阵为
$$
\Gamma _n = (\gamma_{k-j})^n_{k,j=1} = \begin{bmatrix}
\gamma _0  &\gamma _1  & \cdots &\gamma _{n-1} \\
\gamma _1  &\gamma _0  & \cdots &\gamma _{n-1} \\
\vdots  &\vdots  & \ddots &\vdots \\
\gamma _{n-1}  &\gamma _{n-2}  & \cdots &\gamma _0 \\
\end{bmatrix}是非负定矩阵.
$$
- 有界性：$\left\lvert \gamma _k\right\rvert\leqslant \left\lvert \gamma _0\right\rvert,~\forall k \in \mathbb{Z}$.

即：平稳序列是非负定序列.

$Lemma$
内积不等式：
$EX^2<\infty,~EY^2<\infty$则有
$$
\left\lvert E(XY)\right\rvert \leqslant \sqrt{(EX^2)(EY^2)},
$$当且仅当有不全为零的常数$a,b$使得
$$
aX+bY=0,\quad a.s.
$$时等号成立.
这个不等式是概率意义下的柯西-施瓦茨不等式.

$Def$
自相关系数：$\rho _k = \frac{\gamma _k}{\gamma _0},\quad k \in \mathbb{Z}$

$Def$
白噪声：自协方差函数满足$Cov(\epsilon_t,\epsilon_s) =
\begin{cases}
   \sigma^2, &  t = s, \\
   0, & t \neq s.
\end{cases}$
记号：$WN(\mu , \sigma^2)$.
独立序列：独立白噪声 $\quad\mu = 0$：零均值白噪声 $\quad WN(0 , 1)$：标准白噪声$\quad$服从正态分布的独立白噪声：正态白噪声.

$Def$
正交平稳序列：
$\forall s,t \in \mathbb{Z},E(X_tY_s) = 0$则两序列正交;
若协方差函数恒为$0$则两序列不相关.
对于期望为$0$的平稳序列不相关和正交等价.

$Them$
- 正交的平稳序列的和的自协方差函数：
$$
\gamma_Z(k) = \gamma_X(k) + \gamma_Y(k) - 2\mu_X\mu_Y
$$
- 不相关的平稳序列的和的自协方差函数：
$$
\gamma_Z(k) = \gamma_X(k) + \gamma_Y(k)
$$

## 线性平稳序列和线性滤波
### 有限运动平均：
$Def$
白噪声的有限项线性组合是白噪声的（**有限**）**运动平均**，也称**滑动平均**，有均值函数：$\mu = EX_t = \sum_{j=0}^{q} a_jE\epsilon_{t-j} = 0,\quad t\in \mathbb{Z}$.
自协方差函数：$\gamma _{t-s} = E(X_tX_s) = \sum_{j=0}^{q}\sum_{k=0}^{q} a_ka_jE(\epsilon_{t-k}\epsilon_{s-j}) = \begin{cases}
   \sigma^2\sum_{j=0}^{q-(t-s)}a_ja_{j+t-s}, &  0\leqslant t-s \leqslant  q, \\
   0, & t-s > q.
\end{cases}$
即$\gamma _{k} =  \begin{cases}
   \sigma^2\sum_{j=0}^{q-k}a_ja_{j+k}, &  0\leqslant k \leqslant  q, \\
   0, & k > q.
\end{cases}$
### 线性平稳序列
$Def$
$\sum_{j=-\infty}^{\infty}\left\lvert a_j\right\rvert<\infty $则称$\left\{a_j\right\} $绝对可和.
$\left\{\epsilon _t\right\} $的无穷滑动：$X_t=\sum_{j=-\infty}^{\infty}a_j\epsilon _{t-j},\quad t \in \mathbb{Z}$

$Them$
若系数绝对可和则零均值白噪声的无穷滑动为平稳序列.
$Prof$
单调收敛定理、内积不等式：
$$
E\left(\sum_{j=-\infty}^{\infty}|a_j\epsilon_{t-j}|\right) = \sum_{j=-\infty}^{\infty}|a_j|E|\epsilon_{t-j}|\leqslant \sigma \sum_{j=-\infty}^{\infty}|a_j| < \infty
$$
由$\left\lvert \sum_{j=-n}^{n}a_j\epsilon_{t-j}\right\rvert \leqslant \sum_{j=-\infty}^{\infty}|a_j\epsilon_{t-j}|$以及控制收敛定理
$$
EX_t = \lim_{n \to \infty}E\left(\sum_{j=-n}^{n}a_j\epsilon _{t-j}\right) = 0  
$$现令$\xi _n =  \sum_{j=-n}^{n}a_j\epsilon _{t-j}, \quad \eta _n = \sum_{k=-n}^{n}a_k\epsilon _{s-k}$则$\xi _n \eta _n\rightarrow X_tX_s, ~a.s.$且$\left\lvert \xi _n \eta _n\right\rvert \leqslant \sum_{j=-\infty}^{\infty}\sum_{k=-\infty}^{\infty}\left\lvert a_ja_k\epsilon _{t-j}\epsilon _{s-k}\right\rvert = V $
由单调收敛定理
$$
EV = E\left(\sum_{j=-\infty}^{\infty}\sum_{k=-\infty}^{\infty}\left\lvert a_ja_k\epsilon _{t-j}\epsilon _{s-k}\right\rvert\right) = \sum_{j=-\infty}^{\infty}\sum_{k=-\infty}^{\infty}\left\lvert a_ja_k\right\rvert E\left\lvert\epsilon _{t-j}\epsilon _{s-k}\right\rvert \leqslant \sigma ^2 \left(\sum_{j=-\infty}^{\infty}|a_j|\right)^2  < \infty
$$
则由控制收敛定理得
$$
E(X_tX_s) = \lim_{n \to \infty}  E(\xi _n \eta _n)=\lim_{n \to \infty}E\left(\sum_{j=-n}^{n}a_j\epsilon _{t-j}\sum_{k=-n}^{n}a_k\epsilon _{s-k}\right) = \sigma^2\sum_{j=-\infty}^{\infty}a_ja_{j+t-s}$$
则可知$\{X_t\}$为平稳序列，且可得到自协方差函数$\gamma _k=\sigma^2 \sum_{j=-\infty}^{\infty}a_ja_{j+k},~k \in \mathbb{Z}.$
我们可以接着得到：$\lim_{n \to \infty}\gamma _k = 0.$这里可以由柯西不等式得：$\sigma ^2\sum_{|j|\leqslant k/2}|a_ja_{j+k}|\leqslant \sigma ^2\left(\sum_{j=-\infty}^{\infty}a_j^2\sum _{j\leqslant k/2}a_{j+k}^2\right)^{1/2} $
然后可证明上式.
### 时间序列的线性滤波
考虑线性滤波：$Y_t=\sum_{j=-\infty}^{\infty}h_jX_{t-j},~t \in \mathbb{Z}.$
可以参照上面的证明过程证明若$\{X_t\}$是平稳序列且$\{h_j\}$绝对可和（保时线性滤波）那么其线性滤波也是平稳序列.其期望为$\mu _Y = \mu _X\sum_{j=-\infty}^{\infty}h_j$，自协方差函数$\gamma _Y(k) = \sum_{j,k=-\infty}^{\infty}h_jh_k\gamma _X(n+k-j)$

## 严平稳序列及其遍历性

定义**严平稳序列**：若$\forall n,k \in \mathbb{N}$有
$$
(X_1,X_2,\cdots , X_n)^T \overset{d}{\thicksim} (X_{1+t},X_{2+t},\cdots , X_{n+t})^T
$$则$\{X_t\}$为严平稳序列.

$Them$

- 遍历定理：若遍历严平稳序列的绝对值期望存在即$E|X_1|<\infty$有$$\lim_{n \to \infty} \frac{1}{n}\sum_{t=1}^{\infty}X_t = EX_1,\quad a.s. $$.
- 若系数平方可和则线性平稳序列严平稳遍历.
## 谱函数

$Def$
谱密度函数：$\gamma _k = \int_{-\pi}^{\pi}f(\lambda)e^{ik\lambda}  \,d\lambda , ~ k \in \mathbb{Z}$则非负函数$f(\lambda)$为**谱密度函数**，由$Heglotz$定理可以知道，平稳序列的谱函数是唯一存在的，也就是在几乎处处的意义下，谱密度和平稳序列一一对应.

$Them$
**$\{\epsilon _t\}$是$WN(0,~\sigma^2)$，$\{a_j\}$绝对可和则$\{X_t=\sum_{j=-\infty}^{\infty}a_j\epsilon _{t-j}\}$的谱密度为$f(\lambda) = \frac{\sigma^2}{2\pi}\left\lvert \sum_{j=-\infty}^{\infty} a_j e^{ij\lambda}\right\rvert^2 $**

证明如下：设$Y\thicksim U[-\pi, \pi]$则令$\eta _n = e^{inY}$有$E\eta_n = \delta_n,\quad E(\eta _n\overline{\eta_m} ) = \frac{1}{2\pi}\int_{-\pi}^{\pi}e^{i(n-m)y}  \,dy = \delta _{m-n}$，令$Z_n = \sum_{j=-\infty}^{\infty}a_j\eta _{n-j} = \sum_{j=-\infty}^{\infty}a_j e^{i(n-j)Y}$
由内积的连续性可得$EZ_n = a_n,\quad E(Z_n\overline{Z_m}) = \sum_{j=-\infty}^{\infty}a_ja_{j+n-m} = E\left(\sum_{j=-\infty}^{\infty}a_je^{i(n-j)Y}\sum_{k=-\infty}^{\infty}a_ke^{-i(m-k)Y}\right) = \frac{1}{2\pi}\int_{-\pi}^{\pi}\left(\sum_{j=-\infty}^{\infty}a_je^{i(n-j)y}\right) \left(\sum_{k=-\infty}^{\infty}a_ke^{-i(m-k)y}\right)   \,dy = \frac{1}{2\pi}\int_{-\pi}^{\pi}\left\lvert \sum_{j=-\infty}^{\infty}a_je^{-ijy}\right\rvert^2e^{i(n-m)y}   \,dy $
令$k = m - n $则可得$\sigma^2\sum_{j=-\infty}^{\infty}a_ja_{j+k} = \int_{-\pi}^{\pi} \frac{\sigma^2}{2\pi}\left\lvert \sum_{j=-\infty}^{\infty}a_je^{ij\lambda}\right\rvert^2 e^{ik\lambda} \,d\lambda $

$Them$
有两互相正交的零期望平稳序列，$c$为常数，令$$Z_t = X_t + Y_t + c$$
则
- 谱函数$F_Z = F_X + F_Y$
- 谱密度$f_Z = f_X + f_Y$
证明可由上面的定理得到.

### 线性滤波输出的平稳序列的谱密度和谱函数
由上面定义的线性滤波：
首先$$\gamma_Y(k) = \sum_{l,j=-\infty}^{\infty}h_lh_j\gamma_{k+l-j}$$
则由$$\sum_{l,j=-\infty}^{\infty}\left\lvert h_lh_j\right\rvert =\left(\sum_{j=-\infty}^{\infty}\left\lvert h_j\right\rvert \right)^2 < \infty$$
由控制收敛定理
$$\gamma_Y(k) = \sum_{l,j=-\infty}^{\infty}h_lh_j\int_{-\pi}^{\pi} exp[i(k+l-j)\lambda] \,dF_X(\lambda) \\ =\int_{-\pi}^{\pi}\sum_{l,j=-\infty}^{\infty}h_lh_j exp[i(l-j)\lambda]e^{ik\lambda} \,dF_X(\lambda)\\=\int_{-\pi}^{\pi}\left\lvert \sum_{j=-\infty}^{\infty}h_j exp(-ij\lambda) \right\rvert^2 e^{ik\lambda} \,dF_X(\lambda)\\=\int_{-\pi}^{\pi}\left\lvert H(e^{-i\lambda}) \right\rvert^2 e^{ik\lambda} \,dF_X(\lambda)$$
其中$H(z)=\sum_{j=-\infty}^{\infty}h_j z^{j}$则
$Them$
谱函数为
**$$F_Y(\lambda) = \int_{-\pi}^{\pi}\left\lvert H(e^{-i\lambda}) \right\rvert^2 \,dF_X(\lambda)$$**
谱密度为
**$$f_Y(\lambda) = \left\lvert H(e^{-i\lambda})\right\rvert^2 f_x(\lambda)$$**
$Them$
实值平稳序列的谱密度为偶函数.

## $Hilbert$空间中的平稳序列
$Def$
完备的内积空间称为$Hilbert$空间

对于平稳序列$\{X_t\}$，$L^2(X)$表示其中随机变量有限线性组合的全体：
$$L^2(X) = \left\{\sum_{j=1}^ka_jX(t_j)|a_j \in \mathbb{R},t_j \in \mathbb{Z},1\leqslant j\leqslant k,k \in \mathbb{N_+}\right\} $$
定义内积$\left\langle X,Y \right\rangle = E(XY) $
可证明$L^2(X)$为一个内积空间，进一步可以证明在均方收敛意义下的柯西收敛定理成立，则这是一个$Hilbert$空间
### 内积的连续性
$Them$
在内积空间中若$n\rightarrow \infty$时$\left\lVert \xi _n - \xi\right\rVert \rightarrow 0,\left\lVert \eta _n - \eta\right\rVert \rightarrow 0$则有
- $\left\lVert \xi _n\right\rVert \rightarrow \left\lVert \xi \right\rVert ,n\rightarrow\infty$
- $\left\langle \xi_n,\eta_n\right\rangle \rightarrow \left\langle \xi,\eta\right\rangle$
可由三角不等式和内积不等式证明.

现在我们可以证明当$\{a_j\}$平方可和时$X_t = \sum_{j=-\infty}^{\infty}a_j\epsilon_{t-j}$是平稳序列且$EX_t=0,\gamma_k=\sigma^2\sum_{j=-\infty}^{\infty}a_ja_{j+k1
}$
部分和序列$\xi_n = \sum_{j=-n}^{n}a_j\epsilon_{t-j}$
则可以证明这个序列是柯西序列，则有$\xi_n\rightarrow X_t$
由内积连续性$$EX_t = \lim_{n \to \infty} \left\langle \xi_n,1\right\rangle = \lim_{n \to \infty} E\xi_n = 0 , \\ \gamma_k = E(X_tX_{t+K}) \\ =\lim_{n \to \infty}\left\langle \sum_{j=-n}^{n}a_j\epsilon_{t-j},\sum_{j=-n}^{n}a_j\epsilon_{t+k-j}\right\rangle \\ = \lim_{n \to \infty}E\left(\sum_{j=-n}^{n}a_j\epsilon_{t-j},\sum_{j=-n}^{n}a_j\epsilon_{t+k-j}\right) \\ = \sigma^2\sum_{j=-\infty}^{\infty}a_ja_{j+k
}.$$

## 第一章总结：
重点：
- 平稳序列的定义和正交平稳序列的性质
- 滑动平均和无穷滑动（包括平稳性的证明，绝对可和、平方可和的情况）
- 线性滤波
- 谱函数、谱密度以及无穷滑动和线性滤波的谱密度

证明无穷滑动是平稳序列的重点是：用有限滑动来逼近无穷滑动，工具是单调收敛定理、控制收敛定理以及$Hilbert$空间里的内积连续性.

# 自回归模型

## 推移算子和差分方程

$Def$
$\psi (z) = \sum _{j=-\infty}^{\infty}b_jz^j$则$\psi (\mathcal{B} )X_t = \sum _{j=-\infty}^{\infty}b_jX_{t-j}$

$Def$
$\{a_n\}$为实数列则称
$$X_t - \sum_{j = 1}^{p}a_jX_{t-j} = 0$$即$$A(\mathcal{B} )X_t = 0$$
为$p$**阶齐次常系数线性差分方程**，简称为**齐次差分方程**.
可以由$p$个初值唯一决定.
把$A(z) = 1 -  \sum _{j=-\infty}^{\infty}a_jz^j$称为其特征多项式.

$Them$
设$A(z) = 0$有$k$个互异根$\{z_j\}$，且$z_j$是$r(j)$重根则
$$\{z_j^{-t}t^l\}, \quad l = 0,1,\cdots ,r(j)-1,~j = 1,2,\cdots ,k$$是差分方程的$p$个解且通解为
$$X_t = \sum _{j=1}^k\sum_{l=0}^{r(j)-1}U_{l,j}t^lz_j^{-t}$$其中$U$为被初值决定的随机变量.若写成
$$U_{l,j} = V_{l,j}e^{i\theta _{l,j}}, \quad z_j = \rho _je^{i\lambda _j}$$
则实值通解可以表示为$$X_t = \sum _{j=1}^k\sum_{l=0}^{r(j)-1}V_{l,j}t^l\rho ^{-t}\cos(\lambda_jt-\theta_{l,j})$$

非齐次：找特解，通解 = 特解 + 齐次通解.

## $AR(p)$模型

$Def$
${\epsilon_t}$为$WN(0\sigma^2)$且$A(z) = 0$的根都在单位圆外.其中$A(z) = 1 -  \sum _{j=-\infty}^{\infty}a_jz^j$即$$A(z) = 1 -  \sum _{j=-\infty}^{\infty}a_jz^j \neq 0,~\left\lvert z\right\rvert \leqslant 1 $$
则称$p$阶差分方程$$A(\mathcal{B} )X_t = \epsilon_t$$为$p$阶自回归模型即$AR(p)$模型.满足上式的平稳序列为**平稳解**即$\bm{AR(p)}$**序列**，$\{a_j\}$为模型的自回归系数，根在单位圆外的条件是稳定性条件或最小相位条件.

### 解$AR(p)$模型
可由$X_t=A^{-1}(\mathcal{B} ) \epsilon_t= \sum_{j=0}^\infty \psi _j \epsilon_{t-j}$求得模型的特解（平稳解），再由上面的定理求得齐次差分方程的通解，最后得到模型的通解.
这里$\{\psi _j\}$被称为$Wold$系数
$Wold$系数可由$Taylor$公式求得，也可以由递推公式求得.

## $AR$序列的谱密度和$Yule-Walker$方程

利用线性平稳序列的谱密度公式：
$$f_X(\lambda) = \frac{\sigma^2}{2\pi}\left\lvert \sum_{j=-\infty}^{\infty}\psi_je^{ij\lambda}\right\rvert^2 = \frac{\sigma^2}{2\pi\left\lvert A(e^{i\lambda})\right\rvert^2 }$$

$Them$
若平稳序列的自协方差函数绝对可和则有
$$f_X(\lambda) = \frac{1}{2\pi}\sum_{k=-\infty}^{\infty}\gamma_k e^{-ik\lambda}$$
由于谱密度是实值函数，则还可以写成
$$f_X(\lambda) = \frac{1}{2\pi}\left[\gamma_0 + 2\sum_{k=1}^{\infty}\gamma_k \cos(k\lambda)\right]$$

**推论**

对于$AR(p)$模型，有
$$f_X(\lambda) = \frac{1}{2\pi}\sum_{k=-\infty}^{\infty}\gamma_k e^{-k\lambda} = \frac{\sigma^2}{2\pi\left\lvert A(e^{i\lambda})\right\rvert^2 }$$
这里我们可以得到自协方差函数和特征多项式的关系.

### $Yule-Walker$方程

通过在模型等式两边同时乘上$X_{t+k}$然后取期望，我们可以得到一系列式子：
$$\gamma_k - \sum_{j=1}^pa_j\gamma_{k-j} = 0, \quad k \geqslant 1 \\ \gamma_0 - \sum_{j=1}^pa_j\gamma_{-j} = \sigma^2 $$
这组方程称为$Yule-Walker$方程.当然我们也可以用矩阵形式表示：
$$\begin{bmatrix}
\gamma_0  &\gamma_1  & \cdots &\gamma _{n-1} \\
\gamma_1  &\gamma_0  & \cdots &\gamma _{n-2} \\
\vdots  &\vdots  & \ddots &\vdots \\
\gamma _ {n-1}  &\gamma _{n-2}  & \cdots &\gamma _0 \\
\end{bmatrix}
\begin{bmatrix}
a_1 \\
a_2 \\
\vdots \\
a_n \\
\end{bmatrix} =
\begin{bmatrix}
\gamma_1 \\
\gamma_2 \\
\vdots \\
\gamma_n \\
\end{bmatrix}$$其中我们定义自协方差矩阵
$$\Gamma _n = \begin{bmatrix}
\gamma_0  &\gamma_1  & \cdots &\gamma _{n-1} \\
\gamma_1  &\gamma_0  & \cdots &\gamma _{n-2} \\
\vdots  &\vdots  & \ddots &\vdots \\
\gamma _ {n-1}  &\gamma _{n-2}  & \cdots &\gamma _0 \\
\end{bmatrix}$$此外$$\bm{a_n} = \begin{bmatrix}
a_1 &
a_2 &
\cdots &
a_n &
\end{bmatrix}^T \\  \bm{\gamma_n} = \begin{bmatrix}
\gamma_1 &
\gamma_2 &
\cdots &
\gamma_n &
\end{bmatrix}^T$$
则可改写为：
$$\Gamma _n \bm{a_n} = \bm{\gamma_n}\\ \gamma_0 = \Gamma _n^T \bm{a_n} + \sigma ^2 , \quad n \geqslant p$$

我们有如下$Yule-Walker$方程的推论：
$$\gamma_k - (a_1\gamma_{k-1}+a_2\gamma_{k-2}+\cdots +a_p\gamma_{k-p}) = \sigma^2\psi_{-k}$$


#### 自协方差函数的正定性：

$Them$

平稳序列的协方差矩阵正定的充分条件：

- 若序列的谱密度存在则$\forall n\geqslant 1,~\Gamma_n$正定
- 若$\lim_{k\to\infty}\gamma_k = 0$则$\forall n\geqslant 1,~\Gamma_n$正定

证明：
- 对于$\bm{b} = (b_1,b_2,\cdots ,b_n)^T = \bm{0}$，$\lambda$的函数$\sum_{k=1}^nb_ke^{ik\lambda}$最多只有$n-1$个零点.由于$\gamma_0 = \int_{-\pi}^{\pi} f(\lambda) \,d\lambda >0 $则
$$\bm{b^T\Gamma_nb} = \sum_{j=1}^n\sum_{k=1}^nb_k\gamma_{k-j}b_j\\= \sum_{j=1}^n\sum_{k=1}^n\int_{-\pi}^{\pi}  b_kb_jf(\lambda)e^{i(k-j)\lambda} \,d\lambda \\ = \int_{-\pi}^{\pi} \left\lvert \sum_{k=1}^n b_ke^{ik\lambda}\right\rvert^2 f(\lambda) \,d\lambda >0$$

**推论**

线性平稳序列的自协方差矩阵总是正定的.
### 偏相关系数

$Def$
对于一般的平稳序列，称$\bm{\Gamma _n a_n= \gamma_n} $为协方差函数的$n$阶$Yule-Walker$方程，其中$\bm{a_n} = (a_{n,1},a_{n,2},\cdots,a_{n,n})^T$称为协方差函数的$n$阶$Yule-Walker$系数.当$\bm{\Gamma_n}$正定时$\bm{a_n}$由$\bm{\gamma_n}$唯一决定.

$Them$

若$\bm{\Gamma_{n+1}}$正定则$$1-\sum_{j=1}^na_{n,j}z^j \neq 0,\quad |z| \leqslant 1.$$

$Them$

$Levinson$递推公式详见课本.

$Def$

若$\bm{\Gamma_{n+1}}$正定则称$a_{n,n}$为时间序列或自协方差函数的$n$阶**偏相关系数**.

对于$AR(p)$序列：偏相关系数和自回归系数的关系满足：
$$a _k = a_{k,k} ,\quad k = 1,2,\cdots ,p$$
且是$p$后截尾的即$$
\forall n>p,\quad a_{n,n} = 0
$$
其中$a _k$为$AR(p)$模型的自回归系数，$a_{k,k}$为偏相关系数.

$Them$

$AR$序列的充要条件：

零均值平稳序列$\{X_t\}$是$AR(p)$序列的充要条件是它的偏相关系数在$p$后截尾.（可由$Levinson$递推公式证明）

## 第二章总结
重点：
- $AR$模型、序列的定义和最小相位条件
- 谱密度和$Yule-Walker$方程
- 自协方差函数、自相关系数、偏相关系数的求法