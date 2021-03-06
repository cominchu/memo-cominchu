# 線形代数[linear algebra]

教科書

- 原啓介 線形性・固有値・テンソル <線形代数>応用への最短コース (KS理工学専門書)
- [amazonリンク](https://www.amazon.co.jp/dp/4065146852/ref=cm_sw_em_r_mt_dp_U_RNAaFbDHM8ZG3)

## 1. 定義など

### 1.1 線形性1 - 線形空間とベクトル

- (p27)$F$：「数」の集合。おおらかに言えば加減乗除の四則演算ができる集合、厳密には「体」
- 定義1.1 集合$V$が$F$上の線形空間(ベクトル空間)であるとは、以下の性質を持つ
  - 自然な足し算と定数倍が定義されている空間であり、ベクトルはその元のこと。(要加筆)
- 定理1.1 $F$上の線形空間$V$について以下が成り立つ
  1. 零ベクトルは一意
  2. 0倍は零ベクトル
  3. 零ベクトルのa倍も零ベクトル
  4. 任意のベクトルの逆ベクトルは-1倍で一意
- ベクトルと線形空間の例：座標空間、数列、多項式、関数、線形微分方程式の解などが挙げられている。
- 定義1.2 $V$の線形部分空間$U$
  - 同じ零ベクトルを元に持つ
  - ベクトルの和について「閉じている」
  - スカラー倍について「閉じている」
- 定義1.3 線形空間の和：各線形部分空間の元の和全体で定義される
  - $V_1 + \cdots + V_m = \\{v_1 + \cdots + v_m : v_1 \in V_1, \ldots, v_m \in V_m \\}$
- 定義1.4 線形空間の直和
  - 各$v$に対し$v = v_1 + \cdots + v_m$と書く$v_1 \in V_1, \ldots , v_m \in V_m$が一意に存在するとき、Vは$V_1, \ldots V_m$の直和であると言い、$V = V_1 \oplus \ldots \oplus V_m$と書く。
- 定義1.5 （線形）独立と従属
  - $a_1 v_1 + \cdots + a_n v_n = o$を満たす$a_1, \ldots, a_n \in F$が自明なもの、つまり$a_1 = \cdots = a_n = 0$のみに限られるとき、これらのベクトルの組$\\{ v_1, \ldots, v_n\\}$は（線形）独立である、独立性を持つ、などと言う。
  - 独立でないとき、すなわち非自明な$a_1, \ldots, a_n$が存在するとき、これらのベクトルの組は（線形）従属である、従属性を持つ、などと言う。
- 定義1.6 ベクトルの生成する線形空間
  - $span\\{v_1, \ldots, v_n\\} = \\{v \in V: v = a_1 v_a + \ldots + a_n v_n, a_1, \ldots, a_n \in F \\}$
  - 集合$span\\{v_1, \ldots v_n \\}$は$F$上の線形空間だから、これをこのベクトルの組で張られた、または生成された線形空間と呼ぶ。
- 定義1.7 ベクトルの組が$V$を張る、または$V$を生成する
  - $V$のベクトルの組$\\{v_1 \ldots, v_n \\}$の生成する線形空間$span\\{v_1, \ldots v_n \\}$が$V$自身と一致するとき、この組は$V$を張る、または$V$を生成すると言う。
- 定義1.8 有限次元、無限次元
  - $V$が有限個のベクトルの組から生成されるとき、$V$は有限次元であると言う。
  - そうでない場合無限次元であると言う。
- 定義1.9 基底
  - $V$を張る独立なベクトルの組のことを、$V$の基底と言う。またこの組に属するベクトルを基底ベクトルと言う。
- 注意1.2 ベクトルとその成分表示
  - $v = a_1 v_1 + \ldots + a_n v_n$であるとき、  
    $$\mathcal M(v) = \left(
    \begin{array}{c}
      a_1 \\
      a_2 \\
      \vdots \\
      a_n
    \end{array}
    \right)$$  
    のように$\mathcal M(v)$と書く。
  - i番目の成分は$M(v)_i = a_i$のように書く。
  - 特に基底に依存していることを強調したいときには、$\mathcal M(v;(v_1, \ldots, v_n))$のようにも書く。
- 定義1.10 次元
  - 有限次元空間$V$の基底ベクトルの個数を$V$の次元と言い、dim$V$やdim$(V)$と書く
  - 特にdim$\\{ \mathbf{o} \\}$は0と約束する。

### 1.2 線形性2 - 線形写像と行列

- 定義2.1 線形性、線型写像
  - $F$上の線形空間$V$から同じく$F$上の線形空間$W$への写像$L$で、以下の性質を満たすものを、線形である、線形性を持つ、線型写像である、などと言う。
  - 任意の$v \in V$と$k \in F$について$L(kv) = kL(v)$
  - 任意の$u,v \in V$について$L(u+v) = L(u) + L(v)$
- 定義2.2 像、核
  - $V$から$W$への写像Lによる定義域$V$の像を$L$の像と言い、$Im(L)$と書く。  
    つまり$Im(L) = \\{L(v) \in W : v \in V\\}$
  - $W$の零ベクトル飲みの集合$\mathbf{o}$の逆像のことを$L$の核と言い、$Ker(L)$と書く。  
    つまり$Ker(L) = \\{v \in V: L(v)=\mathbf{o} \\}$
- 定義2.3 回数、退化字数
  - 線型写像$L$の像が有限次元であるとき、その元を$L$の階数と呼び、$rank(L)$と書く。すなわち$rank(L) = dim Im(L)$
  - また$L$の核が有限次元であるとき、その次元を$L$の退化次数と呼び、$nullity(L)$と書く。すなわち$nullity(L) = dim Ker(L)$
- 定義2.4 線型写像の可逆性、逆写像
  - 線型写像$L:V → W$に対し、もし線型写像$L':W→V$で$L'L=I_V$かつ$LL'=I_W$が成り立つものがあるとき、$L$は可逆であると言い、この$L'$のことを$L$の逆、または逆写像と言い、$L^{-1}$と書く。
- 定義2.5 線形空間の同型
  - $V$と$W$の間に可逆な線型写像が存在するとき、$V$と$W$は同型であると言い、$V \simeq W$と書く。
- 定義2.6 線形汎関数と双対空間
  - $F$上の線形空間$V$から$W$への線型写像全体の集合$\mathcal L(V;W)$を、和とスカラー倍を定義した線形空間として考える。
  - $F$上の線形空間$V$から$F$への線型写像を特に線形汎関数、または線形形式と言う。
  - この線形汎関数全体のなす線形空間$\mathcal L(V;F)$を$V$の双対空間と良い、$V^*$とも書く。
- (p62) クロネッカーのデルタ$\delta_ij$
  - $\delta_ij$は$i=j$のときは1、$i \neq j$のときは0を表す。
- (p64) 線型写像とその成分表示
  - TBE

## 2. 各種定理・証明

定義を用いて、特に重要と思われる証明を載せていく

### 2.1 双対基底 (p62 定理2.9より)

TBE

### 2.2 線型写像とその成分表示(p63~)

TBE
