# 区間に幅に着目して、全探索する。ループの中身が和級数の計算量で処理できる
https://atcoder.jp/contests/abc128/tasks/abc128_f

# 文字の引き算では、prefixもしくはsuffixしか残らないので、状態数を減らせる
https://atcoder.jp/contests/abc175/tasks/abc175_f

# 数列Cがあり、L, Rに+1するとき、数列Cをグラフで考え、L-Rに貼ったエッジを考える
https://atcoder.jp/contests/abc155/tasks/abc155_f

# 2つ同時にparity入れ替えるとき、1の数および、0の数の偶奇は不変
https://atcoder.jp/contests/abc155/tasks/abc155_f

# 区間加算は、区間差を見ると両端の2点加算、減算
https://atcoder.jp/contests/abc155/tasks/abc155_f

# 漸化式を見抜いた時、行列累乗を考える
https://atcoder.jp/contests/abc009/tasks/abc009_4

# グループの数で包除するのではなく、全体の辺の数で包除する
https://atcoder.jp/contests/abl/tasks/abl_f

# 昇順配列と降順配列の要素を比べると、一致する数字は１種類のみ
https://atcoder.jp/contests/abc178/tasks/abc178_f

# ダブリング配列を使って、二分探索しながら進むとき、最終目的値の直前でとまっておくとバグりにくい
https://atcoder.jp/contests/arc060/tasks/arc060_c

# 回文は、左、中、右に分ける
https://atcoder.jp/contests/arc088/tasks/arc088_c

# 偶数長の閉路しかない　⇄　二部グラフ
https://atcoder.jp/contests/jsc2019-qual/tasks/jsc2019_qual_d

# 昇順ソート、降順ソートの2つの数列は、同じindexで値が重なるのは高々１箇所
https://atcoder.jp/contests/abc178/tasks/abc178_f

# マンハッタン距離は４５度回転する。等距離の奇跡が４５度傾いた正方形から傾きのない正方形に変わる。
https://atcoder.jp/contests/arc047/tasks/arc047_b

# f[i][j] = f[j][i]となる配列は、 y = -x方向に平行移動しても、f[i][j] = f[j][i]が満たされる
https://atcoder.jp/contests/agc023/tasks/agc023_b

# 差が１の最長増加部分列の長さは、idx[]を作成した時、idx[]の最長の連続増加部分列の長さ
https://atcoder.jp/contests/agc024/tasks/agc024_b

# たくさんの文字列のprefix, suffixを扱う時、Trie木を使うと高速
https://atcoder.jp/contests/agc047/tasks/agc047_b

# ２変数をたくさん扱うとき、二次元累積和で高速に処理できるかも
https://atcoder.jp/contests/agc047/tasks/agc047_a

# BITで区間の数の種類を管理する
https://atcoder.jp/contests/abc174/tasks/abc174_f

* point：右端が固定された時、ある数が複数あっても、一番右のものだけ考えればいい

* 問題設定：N要素の数列a[]が与えられて、区間[l,r)に現れる数の種類のクエリQ個に答えたい。（クエリはオフラインとするため、先読みできる。）
* 制約：N <= 10^5, Q <= 10^5, a[i] <= 10^5

* 解法：各数字の最後の登場位置をBITで管理する。<br>

ポイント：「aの要素xが[l, r)に含まれる」という命題は、「a[]を先頭からrまでを見た時、最後にxが登場した位置がl以上」と言い換えられる。
そこで、各数字について最後に登場した位置をBITで管理することで、区間の要素種類数が高速に求められる。BITの更新を手戻りなく進めるために、クエリをrの昇順にソートし、順番に処理していく。

# グラフ上で距離３のパスが問われたら二分グラフを考える
https://atcoder.jp/contests/code-festival-2017-qualb/tasks/code_festival_2017_qualb_c
https://atcoder.jp/contests/hitachi2020/tasks/hitachi2020_c

* 性質：二分グラフでは奇数長のパスは異なる色である。

# 簡単に計算できるような理想的な状態を維持しながら数え上げる（状態が崩れた時には、一定の処理をすると理想的な状態を維持して計算できる）
https://atcoder.jp/contests/mujin-pc-2017/tasks/mujin_pc_2017_a

# 一筆書きで処理するとき、両端を決めると、その左、中、右の順に、線が通る回数が偶、奇、偶となる
https://atcoder.jp/contests/yahoo-procon2019-qual/tasks/yahoo_procon2019_qual_d

# 合計０の状態からずらして考える。数字は１ずらすよりも結構大きく数字をずらす必要がある事が多い。
* https://atcoder.jp/contests/agc007/tasks/agc007_b 
<br>
* https://atcoder.jp/contests/agc016/tasks/agc016_c
はみ出た部分のプラスが大きいほど、総和が大きくなるので、＋とーは限界まで大きくするのがいい。<br>
考察で使えるかもしれないメモ：２次元配列の中に異質な点が点在するようなアイデアよりも、「１行丸ごと異質」のような構築が妥当性を考えやすかったり、偏りによる無駄が生じにくいかもしれない。ただ、この問題では前者のアイデアでも解けた。

# 割ってから引くのと、引いてから割るのでは前者の方が手数減りがち（引いてから割る処理は一番近い値まで引けば十分。それより遠くには引き算で行き、割るより、割ってから引き算した方が引き算の回数が少なく、同じ値に到達できる。）
https://atcoder.jp/contests/agc044/tasks/agc044_a
