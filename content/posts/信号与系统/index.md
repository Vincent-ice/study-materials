---
title: 信号与系统
description: 每题都说了考啥，你还不会？
date: 2024-6-17T16:45:45+08:00
lastmod: 2024-6-24T19:10:45+08:00
author: Vincent Ice
cover: cover.jpg
images:
  - cover.jpg
categories:
  - 信号与系统
tags:
  - 期末复习
---

## 1.连续信号的线性、时不变性、因果性判断

假设$e_1(t)、e_2(t)、e(t)$激励信号得到的响应为$r_1(t)、r_2(t)、r(t)$，

- 线性  $\Leftrightarrow $   $C_1e_1(t)+C_2e_2(t)$激励系统得到$C_1r_1(t)+C_2r_2(t)$
- 时不变  $\Leftrightarrow $  $e(t-t_0)$激励系统得到$r(t-t_0)$
- 因果  $\Leftrightarrow $  $r(t_0)$只与$e(t),t\ge t_0$有关

## 2.信号类型判断

**连续信号**：指在连续时间范围内所定义的信号，在讨论的时间间隔内，对于任意时间值（除若干不连续点外）都给出确定的函数值。

**离散信号**：在时间上是离散的，只在某些不连续的规定瞬时给出函数值，在其他时间没有定义。离散信号的振幅值可以是连续值，也可以是离散值：当离散信号振幅值是连续值时，称为**抽样信号**，当离散信号振幅值是离散值时，称为**数字信号**。

## 3.分解直流、交流分量

信号可分解为直流分量和交流分量的和
$$
f\left( t\right) =f_{D}+f_{A}\left( t\right) \\
$$
其中直流分量$f_D$是信号在其持续时间内的平均值
$$

f_{D}=\dfrac{1}{t_{2}-t_{1}}\int _{t_{1}}^{t_{2}}f\left( t\right) dt\\

$$
对于周期信号而言，直流分量是其一个周期内的平均值
$$
f_{D}=\dfrac{1}{T}\int _{t_1}^{t_{1}+T}f\left( t\right) dt
$$

## 4.冲激信号的抽样特性

$$
\int _{-\infty }^{\infty }f(t)\delta \left( t-t_{0}\right) dt=\int _{-\infty }^{\infty }f\left( t_{0}\right) \delta \left( t-t_0\right) dt=f\left( t_{0}\right) 
$$

## 5.卷积的信号分解思想

卷积（convolution）方法的原理就是将<u>信号分解为冲激信号之和</u>，借助系统的<u>冲激响应</u>，从而求解系统对任意激励信号的<u>零状态响应</u>。

![image-20240623165056513](https://img-blog.csdnimg.cn/202103121106301.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQyMjM1MTI5,size_16,color_FFFFFF,t_70)

## 6.奇异函数平衡法求单位冲击响应

- 求特征根

- 写出齐次根
  $$
  r_1 \ne r_2 \ \ \Leftrightarrow \ \  h(t) = (A_1e^{r_1t}+A_2e^{r_2t})u(t) \\
  r_1 =   r_2 \ \ \Leftrightarrow \ \  h(t) = (A_1+A_2t)e^{r_1t}u(t)      \\
  r = a \pm bj\ \ \Leftrightarrow \ \  h(t) = e^{at}(A_1\cos(bt)+A_2\sin(bt))u(t)
  $$

- 对应求导，代入原式
- 奇异函数比较系数
- 解得$A_1,A_2$
- 写出解（加上特解）

## 7.傅里叶变换的信号分解思想

将一个连续信号分解成一些正弦波（即基本频率）的加权和

## 8.傅立叶变换的微分特性

$$
\begin{array}{c}
时域微分：\mathcal F[\frac{d}{dt}f(t)]=j\omega F(\omega)    \\
频域微分：\mathcal F^{-1}\left[ \dfrac{d}{d\omega }F\left( \omega \right) \right] =-jtf\left( t\right)
\end{array}
$$

## 9.傅立叶变换的卷积特性

$$
时域卷积：\mathcal F [f_1(t)*f_2(t)]=F_1(\omega)F_2(\omega) \\
频域卷积：\mathcal F [f_1(t)f_2(t)]=\frac{1}{2\pi}F_1(\omega)*F_2(\omega)
$$

## 10.时域抽样定理，频域卷积定理

对于频谱函数只在有限区间$(-\omega_m,\omega_m)$内的频谱受限信号$x(t)$，最低抽样频率为$2f_m(其中\omega_m=2\pi f_m)$能保证无失真的从抽样信号中恢复出原信号。最低抽样频率称为“奈奎斯特频率”，最大抽样间隔为“奈奎斯特间隔”。

$f_s(t)=f(t)s(t)$ 求最大频率（$s(t)$为抽样信号）

## 11.求拉普拉斯逆变换

部分分式展开法
$$
F(s)=\dfrac{A(s)}{B(s)}=\sum_{i=1}^{n} \frac{K_i}{s-s_i} \\
K_i=(s-s_i)F(s)	|_{s=s_i}\\
\\
f(t)=\sum_{i=1}^{n} K_ie^{s_it}
$$

$$
F(s)=\dfrac{A(s)}{B(s)[(s+\alpha)^2+\beta^2]}=\frac{K_1}{s+\alpha-j\beta} + \frac{K_2}{s+\alpha+j\beta} \cdots \\
\\
f(t)=e^{-\alpha t}(K_1e^{j\beta t}+K_2^*e^{-j\beta t})=2e^{-\alpha t}[Acos(\beta t)-Bsin(\beta t)] \\
K_1=A+jB,K_2=A-jB=K_1^*
$$


![img](https://img-blog.csdnimg.cn/2020070311090936.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NDMxNjkw,size_16,color_FFFFFF,t_70)

## 12.拉普拉斯变换时域延时定理

$$
\mathcal L [f(t-t_0)u(t-t_0)]=e^{-st_0}F(s)
$$

## 13.系统函数的零极点，判断滤波特性；是否是最小相移网络

系统函数$H(s)$是系统零状态响应的拉氏变换与激励的拉氏变换之比。

$H(s)$分子上有什么就通什么频率。

> $H(s)=\frac{a}{bs+c}$
> 分子上有“低次”，所以是低通。
>
> $H(s)=\frac{as^2}{ bs^2+cs+d}+3$
> 分子上有“高次”，所以是高通。
>
> $H(s)=\frac{as}{bs^2+cs+d}$
> 分子上有“中间次”，所以是带通。
>
> $H(s)=\frac{(j\omega - j\omega_0) \cdots}{\cdots}$
> 分子上当$\omega = \omega_0$时阻断，所以是带阻。

零点仅位于左半平面或者$j\omega$轴的网络函数称为“最小相移网络”。

## 14.系统物理可实现性

时域特性：
$$
h(t)=0,t<0
$$
频域特性：
$$
\left.\begin{matrix}
\int_{-\infty }^{\infty} |{H(j\omega )}|^2 d\omega  < \infty \\
\int_{-\infty }^{\infty} \frac{|ln|{H(j\omega )}||}{1+\omega ^2}  d\omega  < \infty
\end{matrix}\right\}佩利-维纳准则（必要条件）
$$

> 网络函数的值不能为0
>
> 幅度特性呈高斯函数的网络不可实现
>
> 对于有理多项式函数构成的幅度特性是可实现的

## 15.信号恢复的信号分解思想

- 冲激抽样：
  - 抽样信号的频谱是原信号频谱的周期延拓
  - 为了恢复原信号，需要通过理想低通滤波器
- 零阶抽样保持：
  - 取值保持一段时间(用直线代替)
  - 为了恢复原信号，需要通过带补偿的低通滤波器
- 一阶抽样保持：
  - 两个抽样点之间连线(用斜线代替)
  - 为了恢复原信号，需要通过带补偿的低通滤波器
- 欠抽样：产生混叠现象

## 16.信号周期性判断

注意数字信号的离散性

## 17.离散时间系统的因果性、稳定性

- 因果性 $\Leftrightarrow$ $h(n)=0,\forall n<0$
- 稳定性 $\Leftrightarrow$ $\sum _{n=-\infty}^{\infty} |h(n)| < \infty$

## 18.卷积和

![](https://img-blog.csdn.net/20170112153514134?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdGFpeWFuZ3NoZW5uaWFv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)

## 19.z变换定义

定义：
$$
X(z)=\sum _{n=-\infty}^{\infty}  x(n)z^{-n}
$$
收敛域：

满足绝对可和条件，即幂级数收敛
$$
\sum _{n=-\infty}^{\infty}  |x(n)z^{-n}| < \infty
$$
的$z$的取值范围

## 20.z变换的线性性质

若
$$
\mathcal Z[x(n)]=X(z) \quad (R_{x1}<|z|<R_{x2})  \\
\mathcal Z[y(n)]=Y(z) \quad (R_{y1}<|z|<R_{y2})
$$
则
$$
\mathcal Z [ax(n)+by(n)] = aX(z)+bY(z) \quad (max(R_{x1},R_{y1})<|z|<min(R_{x2},R_{y2}))
$$

## 21.傅立叶变换

### 21.1典型信号的傅立叶变换和傅里叶变换的性质

| 信号名称      | $f(t)$                                               | $F(\omega)$                                                  |
| ------------- | ---------------------------------------------------- | ------------------------------------------------------------ |
| *单边指数脉冲 | $Ee^{-at}u(t)$                                       | $\frac{E}{a+j\omega}$                                        |
| 双边指数脉冲  | $Ee^{-a|t|}$                                         | $\frac{2aE}{a^2+\omega ^2}$                                  |
| **矩形脉冲    | $E(u(t+\tau)-u(t-\tau))$                             | $2E\tau Sa(\omega \tau)$                                     |
| **抽样信号    | $Sa(\omega _ct)=\frac{\sin{(\omega_ct})}{\omega_ct}$ | $\frac{\pi}{\omega_c}(u(\omega+\omega_c)-u(\omega-\omega_c))$ |
| 冲击函数      | $E\delta(t)$                                         | $E$                                                          |
| **阶跃函数    | $Eu(t)$                                              | $\frac{E}{j\omega}+\pi E\delta (\omega)$                     |
| *符号函数     | $Esgn(t)$                                            | $\frac{2E}{j\omega}$                                         |
| **直流信号    | $E$                                                  | $2\pi E \delta (\omega)$                                     |
| 余弦信号      | $E \cos(\omega _0t)$                                 | $E \pi [\delta (\omega+\omega_0)+\delta(\omega - \omega_0)]$ |
| 正弦信号      | $E\sin (\omega_0t)$                                  | $j\pi E[\delta (\omega+\omega_0)-\delta(\omega - \omega_0)]$ |

| 性质     | 时域$f(t)$                       | 频域$F(\omega )$                                     |
| -------- | -------------------------------- | ---------------------------------------------------- |
| 线性     | $\sum_{i=1}^{n}a_if_i(t)$        | $\sum_{i=1}^{n}a_iF_i(\omega)$                       |
| 对称性   | $F(t)$                           | $2\pi f(-\omega)$                                    |
| 尺度变换 | $f(at)$                          | $\frac{1}{|a|}F(\frac{\omega}{a})$                   |
| 反褶     | $f(-t)$                          | $F(-\omega)$                                         |
| 时移     | $f(t-t_0)$                       | $F(\omega )e^{-j\omega t_0}$                         |
| 频移     | $f(t)e^{j\omega_0t}$             | $F(\omega-\omega_0)$                                 |
| 时域微分 | $\frac{d^nf(t)}{dt^n}$           | $(j\omega)^nF(\omega)$                               |
| 频域微分 | $(-jt)^nf\left( t\right)$        | $\dfrac{d^n}{d\omega ^n}F\left( \omega \right)$      |
| 时域积分 | $\int_{-\infty}^{t}f(\tau)d\tau$ | $\frac{1}{j\omega}F(\omega)+\pi F(0)\delta (\omega)$ |
| 时域卷积 | $f_1(t)*f_2(t)$                  | $F_1(\omega)F_2(\omega)$                             |
| 频域卷积 | $f_1(t)f_2(t)$                   | $\frac{1}{2\pi}F_1(\omega)*F_2(\omega)$              |
|          |                                  |                                                      |

### 21.2相位谱，幅度谱

把各个分量的幅度$|F_n|$或$ C_n $随着频率$nω_1$的变化称为信号的**幅度谱**。

把各个分量的相位 $φ_n $随角频率 $nω_1$ 变化称为信号的**相位谱**。
$$
F(\omega) = |F(\omega)|e^{j\varphi (\omega)} \\
|F(\omega)|=\arctan \frac{Im[F(\omega)]}{Re[F(\omega)]}
$$

### 21.3傅立叶变换和傅立叶逆变换定义

$$
F(\omega)=\mathcal F (f(t)) = \int _{-\infty}^{\infty} f(t)e^{-i\omega t} dt \\
f(t) = \mathcal F^{-1} [F(\omega)] = \frac{1}{2\pi} \int _{-\infty}^{\infty} F(\omega) e^{j\omega t} d\omega
$$

## 22.求单位冲激响应

冲激响应$h(t)$是系统函数$H(s)$的逆变换，而系统函数是系统零状态响应的拉氏变换与激励的拉氏变换之比，即$H(s)=\frac{R(s)}{E(s)}$。

| $f(t) \quad (t>0)$       | $F(s)=\mathcal L [f(t)]$          |
| ------------------------ | --------------------------------- |
| $\delta (t)$             | 1                                 |
| $u(t)$                   | $\frac{1}{s}$                     |
| $e^{-at}$                | $\frac{1}{s+a}$                   |
| $t^n$                    | $\frac{n!}{s^{n+1}}$              |
| $e^{-at}\sin (\omega t)$ | $\frac{\omega}{(s+a)^2+\omega^2}$ |
| $e^{-at}\cos (\omega t)$ | $\frac{s+a}{(s+a)^2+\omega^2}$    |
| $t^ne^{-at}$             | $\frac{n!}{(s+a)^{n+1}}$          |

| 性质     | 时域                                  | s域                                                          |
| -------- | ------------------------------------- | ------------------------------------------------------------ |
| 线性     | $\sum_{i=1}^{n}a_if_i(t)$             | $\sum_{i=1}^{n}a_iF_i(s)$                                    |
| 时域微分 | $\frac{d^nf(t)}{dt^n}$                | $s^nF(s)-s^{n-1}f^{(1)}(0)-s^{n-2}f^{(2)}(0)-\cdots -f^{(n)}(0)$ |
| 时域积分 | $\int _{-\infty}^{\tau }f(\tau)d\tau$ | $\frac{F(s)}{s}+\frac{f^{(-1)}(0_-)}{s}$                     |
| 延时     | $f(t-t_0)u(t-t_0)$                    | $e^{-st_0}F(s)$                                              |
| s域平移  | $f(t)e^{-at}$                         | $F(s+a)$                                                     |
| 尺度变换 | $f(at)$                               | $\frac{1}{a}F(\frac{s}{a})$                                  |
| 卷积     | $f_1(t)*f_2(t)$                       | $F_1(s)F_2(s)$                                               |
| s域微分  | $-tf(t)$                              | $\frac{dF(s)}{ds}$                                           |
| s域积分  | $\frac {f(t)}{t}$                     | $\int _{s}^{\infty} F(s)ds$                                  |

## 23.利用时域卷积定理，求卷积和

| $x(n)$                                         | $X(z)$                        |
| ---------------------------------------------- | ----------------------------- |
| $\delta(n-a)$                                  | $z^{-a}$                      |
| $u(n)$                                         | $\frac{z}{z-1}$               |
| $a^nu(n) \quad (|z|>|a|)$                      | $\frac{z}{z-a}$               |
| $\frac{(n+1)(n+2)\cdots (n+m)}{m!}a^nu(n)$     | $\frac{z^{m+1}}{(z-a)^{m+1}}$ |
| $-a^nu(-n-1) \quad (|z|<|a|)$                  | $\frac{z}{z-a}$               |
| $-\frac{(n+1)(n+2)\cdots (n+m)}{m!}a^nu(-n-1)$ | $\frac{z^{m+1}}{(z-a)^{m+1}}$ |
| $nu(n)$                                        | $\frac{z}{(z-1)^2}$           |
| $na^nu(n) \quad (|z|>|a|)$                     | $\frac{az}{(z-a)^2}$          |
| $\frac{n(n-1)\cdots (n-m+1)}{m!}u(n)$          | $\frac{z}{(z-1)^{m+1}}$       |

| 序列        | z变换                | 收敛域                                      |
| ----------- | -------------------- | ------------------------------------------- |
| $x(-n)$     | $X(z^{-1})$          | $R_{x1}<|z^{-1}|<R_{x2}$                    |
| $a^nx(n)$   | $X(a^{-1}z)$         | $|a|R_{x1}<|z|<|a|R_{x2}$                   |
| $nx(n)$     | $-z\frac{dX(z)}{dz}$ | $R_{x1}<|z|<R_{x2}$                         |
| $x(n-m)$    | $z^{-m}X(z)$         | $R_{x1}<|z|<R_{x2}$                         |
| $x(n)*h(n)$ | $X(z)H(z)$           | $max(R_{x1},R_{h1})<|z|<min(R_{x2},R_{h2})$ |

