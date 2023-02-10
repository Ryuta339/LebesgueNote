# 有限加法的測度

有限加法的測度とは
- Euclid空間における「体積」の拡張
- $A\in\mathbb{R}^D$ に対して「体積」 $|A|$ の欲しい性質
    1. $0 \leq |A| \leq +\infty$
    2. $n_1 \neq n_2$ならば $A_{n_1} \cap A_{n_2} = \emptyset$ を満たす
        $A_1, \dots, A_N$ に対して，
        $$\left| \bigsqcup_{n=1}^N A_n \right| = \sum_{n=1}^N |A_n|$$
    3. $x \in \mathbb{R}^D$ に対して
        $$|A + x| = |A|$$
    4. ${}^\forall A \subset \mathbb{R}^D$ に対して $|A|$が値を持つ（これは成り立たない）


<details>

<summary><ins>定義（有限加法族）</ins></summary>

$X$を集合とする．
$X$の集合族 $\mathcal{F}\subset 2^X$が次を満たす時，
$\mathcal{F}$を有限加法族という．    
1. $\emptyset \in \mathcal{F}$
2. $A\in\mathcal{F} \Rightarrow A^c\in\mathcal{F}$
3. $A, B \in \mathcal{F} \Rightarrow A \cup B \in\mathcal{F}$

</details>


<ins>系</ins>
1. $X \in \mathcal{F}$
2. $A, B \in \mathcal{F} \Rightarrow A \cap B \in \mathcal{F}$
3. $A, B \in \mathcal{F} \Rightarrow A \backslash B \in \mathcal{F}$
4. $\displaystyle A_1, \dots, A_N \in \mathcal{F} \Rightarrow \bigcup_{n=1}^N A_n \in \mathcal{F}$
5. $\displaystyle A_1, \dots, A_N \in \mathcal{F} \Rightarrow \bigcap_{n=1}^N A_n \in \mathcal{F}$




<details>
<summary><ins>証明</ins></summary>

1. 有限加法族の定義より $\emptyset \in \mathcal{F}$  
   したがって， $X = \emptyset^c \in \mathcal{F}$．
2. $A, B \in \mathcal{F}$より $A^c, B^c \in \mathcal{F}$．  
   よって， $A^c \cup B^c \in \mathcal{F}$．  
   したがってde Morganの定理より， $A \cap B = (A^c \cup B^c)^c \in \mathcal{F}$．
3. $B \in \mathcal{F}$より $B^c \in \mathcal{F}$．  
   よって，2より $A \backslash B = A \cap B^c \in \mathcal{F}$．
4. 次が成り立つので，有限加法族の定義3. を繰り返すことにより成立する．
    $$\bigcup_{n=1}^N A_n = (\cdots((A_1 \cup A_2) \cup A_3) \cup \cdots \cup A_N)$$

5. $A_n \in \mathcal{F}$より $A_n^c\in\mathcal{F}$．  
   したがって，4より $\displaystyle \bigcup_{n=1}^N A_N^c \in \mathcal{F}$．  
   ゆえに，有限加法族の定義より $\displaystyle \bigcap_{n=1}^N A_n = \left( \bigcup_{n=1}^N A_n^c \right)^c \in \mathcal{F}$．
</details>




<details>
<summary><ins>定理（直積空間の有限加法族）</ins>


$Z = X \times Y$ とし， $\mathcal{E}, \mathcal{F}$ をそれぞれ $X$と $Y$の有限加法族とする．
$$\mathcal{G} = \left\\{ \bigsqcup_{n=1}^N E_n \times F_n \middle| E_n \in \mathcal{E}, F_n \in \mathcal{F}, N \in \mathbb{N} \right\\}$$
とすると， $\mathcal{G}$は $Z$の有限加法族．
</summary>

<ins>証明</ins>

1. 有限加法族の定義から $\emptyset \in \mathcal{E}, \emptyset \in \mathcal{F}$より，
   $\emptyset=\emptyset\times\emptyset\in\mathcal{G}$．
2. $A \in \mathcal{G}$とする．
   1. $A = E \times F, E \in \mathcal{E}, F \in \mathcal{F}$とすると，
        $$A^c = E^c \times F^c \sqcup E^c \times F \sqcup E \times F^c$$
        ここで， $E\in\mathcal{E}, F\in\mathcal{F}$より
        $E^c\in\mathcal{E}, F^c\in\mathcal{F}$であるため，
        $A^c \in \mathcal{G}$．
    2. $A, B \in \mathcal{G}$が次のように書けるとする．
        $$A = \bigsqcup_{n=1}^N E_{A,n} \times F_{A,n}, \quad B = \bigsqcup_{m=1}^M E_{B,m} \times F_{B,m}.$$
        ただし， $E_{A,n}, E_{B,m} \in \mathcal{E}, F_{A,n}, F_{B,n}\in\mathcal{F}, M, N \in \mathbb{N}$とする．  
        この時，
        $$A \cap B = \bigsqcup_{n=1}^N \bigsqcup_{m=1}^M (E_{A,n} \cap E_{B,m}) \times (F_{A,n} \cap F_{B,m}).$$
        ここで，
        $E_{A,n}\cap E_{B,m} \in \mathcal{E}, F_{A,n}\cap F_{B,m} \in \mathcal{F}$より，
        $A \cap B \in \mathcal{G}$.  
        特に， $A_1, \dots, A_N \in \mathcal{G}$ ならば
        $\displaystyle \bigcap_{n=1}^N A_n \in \mathcal{G}$．
    3. $A \in \mathcal{G}$ が次のように書けるとする．
        $$A = \bigsqcup_{n=1}^N E_n \times F_n, \quad E_n \in \mathcal{E}, F_n \in \mathcal{F}, N \in \mathbb{N}$$
        この時，
        $$A^c = \bigcap_{n=1}^N (E_n^c \times F_n^c \sqcup E^c_n \times F_n \sqcup E_n \times F_n^c).$$
        ここで， $E_n\in\mathcal{E}, F_n\in\mathcal{F}$より
        $E_n^c\in\mathcal{E}, F_n^c\in\mathcal{F}$．  
        したがって， $n=1,\dots,N$に対して
        $E_n^c \times F_n^c \sqcup E^c_n \times F_n \sqcup E_n \times F_n^c \in \mathcal{G}$．  
        ゆえに，iiから $A^c \in \mathcal{G}$．
3. $A, B \in \mathcal{G}$とする．  
    2より $A^c, B^c\in\mathcal{G}$であるため，2iiより $A^c \cap B^c\in\mathcal{G}$．  
    よって，再度2より
    $$A \cup B = (A^c \cap B^c)^c \in \mathcal{G}.$$
</details>
