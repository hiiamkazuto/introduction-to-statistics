# 第9章 相関分析

## 9.1 相関関係と相関分析

相関関係とは、二つの変数の間に見られる関係性のことである。一方の変数の値が変化すると、もう一方の変数の値も一定の傾向を持って変化する場合、二つの変数には相関関係があると言える。

*   **正の相関：** 一方の変数の値が増加すると、もう一方の変数の値も増加する傾向がある場合。
*   **負の相関：** 一方の変数の値が増加すると、もう一方の変数の値は減少する傾向がある場合。
*   **無相関：** 二つの変数の間に明確な関係性が見られない場合。

相関分析は、この相関関係の有無や強さを定量的に評価する手法である。散布図を用いてデータの分布を視覚的に確認することも重要である。

## 9.2 単純相関係数の計算（Raw data のケース）

生データ（Raw data）、つまり個々のデータがそのままの形で与えられている場合、ピアソンの積率相関係数と呼ばれる指標を用いて相関関係を測定する。単純相関係数とも呼ばれる。

単純相関係数 *r* を求める手順は、教科書に示されている通り、以下の3つのステップに分けられる。

1.  **平均値 X̄, Ȳ の計算 (Step 3)：**

    XとYそれぞれの平均値 X̄, Ȳ を以下の式で計算する。

    $$
    \bar{X} = \frac{1}{n}\sum X
    $$

    $$
    \bar{Y} = \frac{1}{n}\sum Y
    $$

    ここで、

    *   ΣX, ΣY: XとYのデータの総和
    *   *n*: データ数

2.  **決定係数 r² の計算 (Step 4)：**

    決定係数 *r*² を以下の式で計算する。教科書には以下の式が紹介されている。

    $$
    r^2 = \frac{(\sum XY - n\bar{X}\bar{Y})^2}{(\sum X^2 - n\bar{X}^2)(\sum Y^2 - n\bar{Y}^2)}
    $$

    ここで、

    *   ΣXY: XとYの積の総和
    *   ΣX², ΣY²: XとYの二乗の総和
    *   $\bar{X}$, $\bar{Y}$: XとYの平均値
    *   *n*: データ数

    教科書には、分子は正相関なら正、負相関なら負になるという記述がある。これは、分子 $(\sum XY - n\bar{X}\bar{Y})$ が共分散を表しており、共分散の符号が相関の符号を決定するためである。

3.  **相関係数 *r* の計算 (Step 5)：**

    決定係数 *r*² の平方根をとり、相関係数 *r* を求める。

    $$
    r = \pm \sqrt{r^2}
    $$

    正相関の場合は+、負相関の場合は-をつける。符号は、Step 4の分子 $(\sum XY - n\bar{X}\bar{Y})$ の符号に一致する。

相関係数 *r* は-1から+1までの値をとり、

*   *r* = +1：完全な正の相関
*   *r* = -1：完全な負の相関
*   *r* = 0：無相関

を表す。|r| が1に近いほど相関が強く、0に近いほど相関が弱いと言える。教科書には、電卓で直接計算した場合と、上記の式で計算した場合で、有効数字の取り方の違いによって結果に若干の誤差が生じる場合があるという注意書きがある。

## 9.3 単純相関係数の計算（Classified data のケース）

分類データ（Classified data）、つまりデータがいくつかの階級に分けられている場合、上記の生データの場合の式をそのまま用いることはできない。このような場合は、各階級の中央値を用いて計算を行う。原料価格Xと不良品率Yがそれぞれ階級分けされており、各階級の生産個数f<sub>i</sub>（またはf<sub>ij</sub>）が与えられている場合の相関係数 *r* の計算手順は以下の通りである。

1.  **各階級の中央値を求める：** 各階級の範囲の中央の値を *x<sub>i</sub>*, *y<sub>j</sub>* とする。原料価格はそのまま数値で与えられているため、これを *x<sub>i</sub>* とする。不良品率は割合で与えられているため、これを *y<sub>j</sub>* とする。

2.  **各階級の度数（生産個数）を確認：** 各階級の生産個数 *f<sub>i</sub>*（または *f<sub>ij</sub>*）を確認する。

3.  **以下の式を用いて計算を行う：**

    まず、決定係数 *r*² を以下の式(9.3)で求める。

    $$
    r^2 = \frac{\{\sum_{i=1}^{m}\sum_{j=1}^{l}f_{ij}(x_i - \bar{x})(y_j - \bar{y})\}^2}{\sum_{i=1}^{m}f_i(x_i - \bar{x})^2 \sum_{j=1}^{l}f_j(y_j - \bar{y})^2}
    $$

    または、計算を簡略化するために、以下の式(9.4)を用いることもできる。

    $$
    r^2 = \frac{(\sum XYf - \frac{\sum X \cdot \sum Y}{\sum f})^2}{(\sum X^2f - \frac{(\sum X)^2}{\sum f})(\sum Y^2f - \frac{(\sum Y)^2}{\sum f})}
    $$

    ただし、教科書によっては分母が$(\sum X^2f - \frac{(\sum X)^2}{\sum f})(\sum Y^2f - \frac{(\sum Y)^2}{\sum f})$ではなく、$(\sum X^2f - (\sum X)^2)(\sum Y^2f - (\sum Y)^2)$と表記されている場合がある。この点については、教科書に合わせて適切に判断する必要がある。

    ここで、

    *   *x<sub>i</sub>*, *y<sub>j</sub>*: i番目、j番目の階級の中央値
    *   $\bar{x}$, $\bar{y}$: xとyの平均値
    *   *f<sub>ij</sub>*: i番目、j番目の階級の度数（例題ではf<sub>i</sub>として与えられている）
    *   *m*, *l*: x, yそれぞれの階級数

4.  **相関係数 *r* を求める：** 決定係数 *r*² の平方根をとり、相関係数 *r* を求める。この際、$\sum_{i=1}^{m}\sum_{j=1}^{l}f_{ij}(x_i - \bar{x})(y_j - \bar{y})$ の符号（正または負）によって、*r* の符号を決定する。例題では、この値がマイナスであるため、*r* にマイナスをつけている。

    $$
    r = \pm \sqrt{r^2}
    $$
    符号は、$\sum XYf - \frac{\sum X \cdot \sum Y}{\sum f}$の符号に一致する。

分類データの場合の相関係数の計算手順を具体的に理解することができた。特に、決定係数 *r*² を求めてから相関係数 *r* を求める手順、そして *r* の符号の決定方法が重要であることを学んだ。また、有効数字の取り方によって計算結果に若干の誤差が生じる場合があることも理解した。