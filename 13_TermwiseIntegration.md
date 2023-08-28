# 項別積分に関する諸定理

- 積分と極限の入れ替えができる条件を調べる
- $(X, \mathcal{F}, \mu)$: 測度空間

## 単調収束定理

- 単調増加する非負値単調増加可測関数列は積分と極限の入れ替えが可能であるという定理
- 非負値単調増加 **単関数** 列であればLebesgue積分の定義

<ins>Thm 13.1</ins> （単調収束定理）

$E \in \mathcal{F}$ 上で可測な非負値関数列$\{f_n\}_{n=1}^\infty$が$f_1 \leq f_2 \leq \cdots \leq f_n \leq \cdots \leq f$ が，$f$ に各点収束するならば，次が成り立つ．
```math
\begin{align}
    \lim_{n \to \infty} \int_E f_n d\mu
    = \int_E fd\mu
\end{align}
```

- これを示すために，次のいくつかの補題を示す．

<details>
<summary>
<ins>Lemma 13.2</ins>

$E \in \mathcal{F}$ 上で可測な任意の非負値関数$f$に対して，非負値単関数列$\{g_n\}_{n=1}^\infty$で， ${}^\forall x \in E$ に対して次が成り立つものが存在する．
```math
\begin{align}
    f(x) = \sum_{n=1}^\infty g_n(x)
\end{align}
```

</summary>

<ins>Pf</ins><br />
$f$ は非負値可測関数より，$f$に各点収束する単調増加非負値単関数列$\{h_n\}_{n=1}^\infty$が存在する．
$g_1 = h_1, g_{n+1} = h_{n+1} - h_n (n=1,2, \dots)$ とおくと，$\{g_n\}_{n=1}^\infty$ は非負値単関数列であり，
```math
\begin{align*}
    h_N(x) = \sum_{n=1}^N g_n(x)
\end{align*}
```
が成立する．
特に，次が各点で成り立つ．
```math
\begin{align*}
    f(x) = \lim_{N\to\infty} h_N(x) = \sum_{n=1}^\infty g_n(x)
\end{align*}
```

</details>



<details>
<summary>
<ins>Lemma 13.3</ins>

$E$ 上の非負値単関数列$\{f_n\}_{n=1}^\infty$ と$E$上で可測な非負値関数$f$に対して，各点で次が成り立つとする．
```math
\begin{align*}
    f(x) = \sum_{n=1}^\infty f_n(x)
\end{align*}
```
この時，次が成り立つ．
```math
\begin{align}
    \int_E f d\mu = \sum_{n=1}^\infty \int_E f_n d\mu
\end{align}
```

</summary>

<ins>Pf</ins>
非負値単調増加単関数列$\{g_n\}_{n=1}^\infty$を次で定義する．
```math
\begin{align*}
    g_N(x) = \sum_{n=1}^N f_n(x)
\end{align*}
```
この時，$f(x) = \lim_{N\to\infty} g_N(x)$ が各点$x \in E$で成立する．
したがって，積分の定義より
```math
\begin{align*}
    \int_E f d\mu
    = \lim_{N \to \infty} \int_E g_N d\mu
    = \lim_{N \to \infty} \sum_{n=1}^N \int_E f_n d\mu
    = \sum_{n=1}^\infty \int_E f_n d\mu
\end{align*}
```


</details>



<details>
<summary>
<ins>Lemma 13.4</ins>

$E \in \mathcal{F}$ 上で可測な非負値関数列$\{f_n\}_{n=1}^\infty$ と，非負値関数$f$に対して，各点で次が成立するとする．
```math
\begin{align*}
    f(x) = \sum_{n=1}^\infty f_n(x)
\end{align*}
```
この時，次が成り立つ．
```math
\begin{align}
    \int_E fd\mu = \sum_{n=1}^\infty \int_E f_n d\mu
\end{align}
```

</summary>

<ins>Pf</ins>
${}^\forall n \in \mathbb{N}$ に対して，$f_n$ は非負値可測関数より，lemma 13.2 から非負値単関数列$\{g_{nm}\}_{m=1}^\infty$で，${}^\forall x \in E$に対して次が成立するものが存在する．
```math
\begin{align*}
    f_n(x) = \sum_{m=1}^\infty g_{nm}(x)
\end{align*}
```
この時，
```math
\begin{align*}
    f(x) = \sum_{n=1}^\infty \sum_{m=1}^\infty g_{mn}(x)
\end{align*}
```
$\{g_{mn}\}_{m,n=1}^\infty$を適当に並び替えた非負値単関数列$\{h_\ell\}_{\ell=1}^\infty$を考える．
$g_{mn}$ は非負値より，各点で次が成立する．
```math
\begin{align*}
    f(x) = \sum_{\ell=1}^\infty h_\ell(x)
\end{align*}
```
Lemma 13.3より
```math
\begin{align*}
    \int_E f d\mu
    = \sum_{\ell=1}^\infty \int_E h_\ell d\mu
    = \sum_{n=1}^\infty \sum_{m=1}^\infty \int_E g_{nm} d\mu
    = \sum_{n=1}^\infty \int_E f_n d\mu
\end{align*}
```
</details>



- 以上の準備のもと，単調収束定理を示す．

<ins>Pf of Thm 13.1</ins>


1. ある$N \in \mathbb{N}$ で$\mu(E(f_N = \infty)) > 0$ の時．
   $\{f_n\}{n=1}^\infty$ は単調増加より，${}^\forall x \in E(f_N=\infty)$ と${}^\forall n \geq N$ に対して$f_n(x) = \infty$.
   したがって，$f(x) = \infty$．
   この時，${}^\forall n \geq N$ に対して
   ```math
    \begin{align*}
        \int_E f_n(x) d\mu = \infty
    \end{align*}
   ```
   であるので，
   ```math
    \begin{align*}
        \lim_{n \to \infty} \int_E f_n d\mu = \infty = \int_E f d\mu
    \end{align*}
   ```
2. ${}^\forall n \in \mathbb{N}$に対して$\mu(E(f_n = \infty))=0$ の時．
   $E_\infty = \bigcup_{n=1}^\infty E(f_n=\infty)$とおくと，$\mu(E_\infty)=0$．
   よって，$E \backslash E_\infty$を改めて$E$と置くことで，任意の$n \in \mathbb{N}$に対して$f_n(x) < \infty$ を仮定して証明を進めても問題ない．

    $E$上可測な非負値関数列$\{g_n\}_{n=1}^\infty$を次で定義する．
    ```math
    \begin{align*}
        g_1(x) = f_1(x),
        \qquad
        g_{n+1}(x) =  f_{n+1}(x) - f_n(x)
        \quad(n=1,2,\dots)
    \end{align*}
    ```
    この時，${}^\forall x \in E$ で次が成り立つ．
    ```math
    \begin{align*}
        f_N(x) = \sum_{n=1}^N g_n(x),
        \qquad
        f(x) = \sum_{n=1}^\infty g_n(x)
    \end{align*}
    ```
    Lemma 13.4より，
    ```math
        \begin{align*}
            \int_E f d\mu = \sum_{n=1}^\infty \int_E g_n d\mu
            = \lim_{N \to \infty} \sum_{n=1}^N \int_E g_n d\mu
            = \lim_{N \to \infty} \int_E f_N d\mu
        \end{align*}
    ```
