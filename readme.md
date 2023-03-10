# D Q axis inductance calculator

这是一个简单的电机DQ轴计算器，输入Labc矩阵，输出$L_d$ 和 $L_q$

该电感计算器可用于计算三相交流电机的dq轴电感。


## 用法
在labc矩阵中输入L_A, L_B, L_C的自感、互感值。

点击"计算"按钮，即可得到dq轴电感Ld和Lq的值。
## 注意事项
该计算器使用mathjs和mathjax库，需要在浏览器中启用JavaScript。
输入的参数必须是数字。

## 公式
dq轴电感Ld和Lq的计算公式如下：

$$
i_{abc}=Ci_{dq0} \tag{1}
$$

$$
\begin{align}
\psi_{dq0}
&= C^{-1}\psi_{abc} \\
&= C^{-1}L_{abc}i_{abc} \\
&=  C^{-1}L_{abc}Ci_{dq0}\\
&= L_{dq0}i_{dq0} \tag{2}
\end{align}
$$

$$
L_{dq0}=C^{-1}L_{abc}C \tag{3}
$$


$$
L_{abc} =
\begin{bmatrix}

L_{aa} & L_{ab} & L_{ac} \\
L_{ba} & L_{bb} & L_{bc} \\
L_{ca} & L_{cb} & L_{cc} \\

\end{bmatrix}\tag{4}
$$

$$
L_{dq0}=
\begin{bmatrix}

L_{dd} & L_{dq} & L_{d0} \\
L_{qd} & L_{qq} & L_{q0} \\
L_{0d} & L_{0q} & L_{00} \\

\end{bmatrix}
\tag{5}
$$

$$
C=\begin{bmatrix}
cos\theta & -sin\theta & 1\\
cos(\theta-120^\circ) & -sin(\theta-120^\circ) & 1\\
cos(\theta+120^\circ) & -sin(\theta+120^\circ) & 1\\
\end{bmatrix}\tag{6}
$$

$$
C^{-1}=\frac{2}{3}\begin{bmatrix}
cos\theta & cos(\theta-120^\circ) & cos(\theta+120^\circ) \\
-sin\theta & -sin(\theta-120^\circ) & -sin(\theta+120^\circ)\\
\frac{1}{2} & \frac{1}{2} & \frac{1}{2}\\
\end{bmatrix}\tag{7}
$$


# License
本项目遵循 MIT License，详见 LICENSE 文件。