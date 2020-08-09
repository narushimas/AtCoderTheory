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

# 合計０の状態からずらして考える。結構大きく数字をずらす。
https://atcoder.jp/contests/agc007/tasks/agc007_b
https://atcoder.jp/contests/agc016/tasks/agc016_c　
考察で使えるかもしれないメモ：２次元配列の中に異質な点が点在するようなアイデアよりも、「１行丸ごと異質」のような構築が妥当性を考えやすかったり、偏りによる無駄が生じにくいかもしれない。
