---
date : "2015-02-03T04:33:41-08:00"
type : page
title : "test unicode and mathjex"

---

`$ f(x) = x^{-1} + sqrt{x} $`


```
/***
Algorithms: Design and Analysis, Part 1
Week 1
Jan 2015
***/
 
#include <bits/stdc++.h>
using namespace std;
 
// [s,e) consider boundary!! make range uniform
long long countMergeInv(int A[], int s, int e){
long long cnt = 0; //result: return value
int mid = ( e - s ) / 2 + s;
int size = ( e - s ) + 1;
vector<int> res(size,-1);
int i = s;
int j = mid;
 
for(int k = 0; k < size; k++){
if ( i < mid && ( j >= e || A[i] < A[j] ) ){
res[ k ] = A[i++];
}
else{
cnt += mid - i;
res[ k ] = A[j++];
}
}
 
//copy to A[]
for(int k = 0; k < size; k++){
A[ k + s ] = res[ k ];
}
 
return cnt;
}
 
long long count(int A[], int s, int e){
if ( e - s < 2 ){
return 0;
}
else {
int mid = ( e - s ) / 2 + s;
long long x, y, z;
x = count(A, s, mid ); //split first part
y = count(A, mid , e); //split second part
z = countMergeInv(A, s, e); //Merge and count Inversion
return x + y + z;
}
}
 
int main(){
int A[200000];
int i = 0;
while ( scanf("%d", &A[i]) != EOF ) {
i++;
}
int cnt = i;
long long res;
res = count(A, 0, cnt);
printf("%lld\n", res);
 
int test1[] = {1,3,5,2,4,6}; //test #1: 3
int test2[] = {8,7,6,5,4,3,2,1}; //test #2: 28
return 0;
}
```


```
海平面远方开始阴霾
悲伤要怎么平静纯白
我的脸上 始终挟带
一抹浅浅的无奈
你用唇语说你要离开
心不在
那难过无声慢了下来
汹涌潮水 你听明白
不是浪而是泪海
转身离开 分手说不出来（你有话说不出来）
海鸟跟鱼相爱
只是一场意外
我们的爱（给的爱）
差异一直存在 （回不来）
风中尘埃 （等待）
竟累积成伤害
转身离开 分手说不出来
蔚蓝的珊瑚海
错过瞬间苍白
当初彼此（你我都）
不够成熟坦白 （不应该）
热情不再 （你的）
笑容勉强不来
爱深埋珊瑚海
毁坏的沙雕如何重来
有裂痕的爱怎么重盖
只是一切 结束太快
你说你无法释怀
贝壳里隐藏什么期待
等花儿开
我们也已经无心再猜
面向海风 咸咸的爱
尝不出还有未来
转身离开 分手说不出来（你有话说不出来）
海鸟跟鱼相爱
只是一场意外
我们的爱（给的爱）
差异一直存在 （回不来）
风中尘埃 （等待）
竟累积成伤害
转身离开 分手说不出来
蔚蓝的珊瑚海
错过瞬间苍白
当初彼此（你我都）
不够成熟坦白 （不应该）
热情不再 （你的）
笑容勉强不来
爱深埋珊瑚海
```