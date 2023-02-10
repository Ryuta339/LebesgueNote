# 有限加法的測度

有限加法的測度とは
- Euclid空間における「体積」の拡張
- $A\in\mathbb{R}^D$ に対して「体積」$|A|$の欲しい性質
    1. $0 \leq |A| \leq +\infty$
    2. $n_1 \neq n_2$ならば$A_{n_1} \cap A_{n_2} = \emptyset$ を満たす
        $A_1, \dots, A_N$ に対して，
        $$\left| \bigsqcup_{n=1}^N A_n \right| = \sum_{n=1}^N |A_n|$$
    3. $x \in \mathbb{R}^D$ に対して
        $$|A + x| = |A|$$
    4. ${}^\forall A \subset \mathbb{R}^D$ に対して$|A|$が値を持つ（これは成り立たない）


<datails>

<summary><u>Def（有限加法族）</u></summary>

$X$を集合とする．
$X$の集合族$\mathfrak{F}\subset 2^X$が次を満たす時，$\mathcal{F}$を有限加法族という．    
1. $\emptyset \in \mathfrak{F}$
2. $A\in\mathfrak{F} \Rightarrow A^c\in\mathfrak{F}$
3. $A, B \in \mathfrak{F} \Rightarrow A \cup B \in\mathfrak{F}$

</details>
