# C - +/- Rectangle
https://atcoder.jp/contests/agc016/tasks/agc016_c

# ひし形の数を数える（ひし形カウントの制約が厳しい物）
https://codeforces.com/contest/1393/problem/D
<details>
<summary>解法</summary>
<pre>
<code>
中心(i,j)として、大きさxの菱形が成立するかどうかは、上下左右(i−１,j),(i＋１,j),(i,j-1),(i，j+1)を中心としたx-1の大きさの菱形が成立するかどうかを確認すればいい。
大きさを１から調べていくDPで達成できるが、これだと計算量が大きくて間に合わないO（NMX)：XはNとMの小さい方。
そこで、上と左、左と下、下と右、右と上、の４つそれぞれについて、２値の小さい方＋１を持つようなDPをO(NM)で事前計算しておくと、各頂点についてO(１)で最大の菱形の大きさを調べることができる。

参考：titiaさんのコード（https://codeforces.com/contest/1393/submission/89260148）
import sys
input = sys.stdin.readline

n,m=map(int,input().split())
MAP=[input().strip() for i in range(n)]

COUNT0=[[1]*m for i in range(n)]
COUNT1=[[1]*m for i in range(n)]
COUNT2=[[1]*m for i in range(n)]
COUNT3=[[1]*m for i in range(n)]

for i in range(1,n-1):
    for j in range(1,m-1):
        if MAP[i][j]==MAP[i-1][j]==MAP[i][j-1]:
            COUNT0[i][j]=min(COUNT0[i-1][j],COUNT0[i][j-1])+1

for i in range(n-2,0,-1):
    for j in range(m-2,0,-1):
        if MAP[i][j]==MAP[i+1][j]==MAP[i][j+1]:
            COUNT1[i][j]=min(COUNT1[i+1][j],COUNT1[i][j+1])+1

for i in range(1,n-1):
    for j in range(m-2,0,-1):
        if MAP[i][j]==MAP[i-1][j]==MAP[i][j+1]:
            COUNT2[i][j]=min(COUNT2[i-1][j],COUNT2[i][j+1])+1

for i in range(n-2,0,-1):
    for j in range(1,m-1):
        if MAP[i][j]==MAP[i+1][j]==MAP[i][j-1]:
            COUNT3[i][j]=min(COUNT3[i+1][j],COUNT3[i][j-1])+1

ANS=0
for i in range(n):
    for j in range(m):
        ANS+=min(COUNT0[i][j],COUNT1[i][j],COUNT2[i][j],COUNT3[i][j])

print(ANS)


</code>
</pre>
</details>
