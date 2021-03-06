# E2-2015级算法练习题（二）

# `A` jhljx水水的卡牌

时间限制：2000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## Problem Description

jhljx是一个很喜欢玩卡牌的人，他总共有n张牌，每张牌都有一个英雄。

每个英雄ii都在离家很远的地方，需要TiTi分钟的时间才能回到家，当该英雄处于等待状态的时候，每分钟消耗SiSi点体力。而奇怪的是英雄在回家的路上不需要消耗体力。

从每个英雄的位置到家只有一条路，也就是说每次只能有一个英雄走过。前一个英雄到家后，下一个英雄才可以开始走。

因此你需要找到这n个英雄的一个合适的顺序，保证所有英雄消耗的体力值总和最小。

## Input

输入多组数据。
对于每组数据，第一行有一个正整数n（1≤n≤1000001≤n≤100000）表示总共有n个英雄。
接下来n行，每行2个整数Ti(1≤Ti≤1000000)Ti(1≤Ti≤1000000),Si(1≤Si≤1000)Si(1≤Si≤1000)，分别表示英雄回家需要的时间，和英雄在等待时需要花费的体力。

## Output

对于每组数据，输出所有英雄消耗的体力总和的最小值。

## Sample Input

```
6
2 5
3 1
4 1
3 2
2 3
1 6
```

## Sample Output

```
43
```

## Source

POJ xxxx

## Hint

- greedy & sorting
- the answer is possible to be long long
- how to override compare function maybe a direction to you

## 思路

上面既然已经说了贪心+排序了，那么考虑两个英雄之间到底让谁先走

很显然，一个回家的时间乘以另一个等待的时间更短的话，那优先让这个假设条件下回家的人先走

# `B` jhljx数组变变变

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

jhljx拿到了一个数组，这个数组是一个降序的序列。
比如：jhljx拿到了7 6 5 4 3 2 1这个序列，请设计一个时间复杂度O(n)和空间复杂度O(1)的算法，使其变成1 7 2 6 3 5 4。
即将一个降序序列变成最小值、最大值，次小值、次大值，次次小值、次次大值...这样的序列。

## 输入

输入多组数据。 每组数据为一个正整数n(1<=n<=1000000)。
第二行为从n到1的降序序列。

## 输出

输出新的序列。

## 输入样例

```
7
7 6 5 4 3 2 1
```

## 输出样例

```
1 7 2 6 3 5 4
```

## 题目来源

改编自阿里2016校招算法工程师笔试

## 思路

这题其实本意是希望如何设置一个较好的swap策略进行调整

然而北航OJ的普通评测原理仅仅是校对输出的文件

如果这题采用类似leetcode那样的special judge，那还有做一做的价值，现在很遗憾，直接水过都是可以的

# `C` Magry的幸运度

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

已知：左边给出长度为n一串数组LL，右边给出同样长的一串数RR，左右两边的数组下标同为i的数（LiLi与RiRi）一一对应且可交换。

另外定义这两组数的`幸运度`为左边数组L各个元素之和 ∑ni=1Li∑i=1nLi 与右边数组各元素和∑ni=1Ri∑i=1nRi之差的绝对值，即∣∣∑ni=1Li−∑ni=1Ri∣∣|∑i=1nLi−∑i=1nRi|

`Magry`可以**最多对一个数对**（即上文提及左右两边的数组下标同为 ii 的数LiLi与RiRi）进行交换操作，从而得到新的`幸运度`∣∣∑ni=1Li−∑ni=1Ri∣∣|∑i=1nLi−∑i=1nRi|，也可以选择不对数组进行任何操作。

请问`Magry`交换第几个数对时得到的`幸运度`最大？若不交换数对就能得到最大值则输出`0`。

## 输入

输入包含多组测试数据，以EOF结束。

对于每组数据，输入n+1行。

第一行为1个正整数，L、R两个数组长度n.

接下来n行，每行2个正整数，以一个空格分隔，对于第 ii 个数对，两个数分别表示LiLi与RiRi

需要注意的是，这里1≤i≤n1≤i≤n

保证1≤n≤1000001≤n≤100000，1≤Li,Ri≤5001≤Li,Ri≤500

## 输出

对于每组数据，输出一行，一个数，`Magry`交换第几个数对时得到的`幸运度`最大？若不交换数对就能得到最大值则输出`0`。

当然，在某些情况下可能存在多种解，输出**任意一种解**即可。

## 输入样例

```
3
5 6
8 9
10 3
2
6 5
5 6
```

## 输出样例

### 第一种答案

```
3
1
```

### 第二种答案

```
3
2
```

## 样例解释

对于上述样例，第二组数据有两种答案，即交换第一个数对或第二个数对均可达到所求幸运度最大(最大值为2)。本题输出任意一种均可。

## 思路

这题好像跟算法没有卵关系...

# `E` 钢管拼接

时间限制：2000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

给定nn根钢管，除**长度**外其余特征全都一样，且任意两根钢管均可拼接，拼接后得到的新的钢管长度为两根钢管长度之和。

求这nn根钢管**任取两根钢管**拼接后得到的新的钢管可能的长度的最小值和最大值。

## 输入

第一行包含一个正整数TT，表示有TT组测试数据。

接下来依次给出每组测试数据。对于每组测试数据：

第一行为一个正整数nn，代表钢管个数；

第二行为nn个正整数l1,l2,...,lnl1,l2,...,ln，代表各根钢管的长度。

保证1≤T≤101≤T≤10，1≤n≤1,000,0001≤n≤1,000,000，1≤li≤1,000,000,0001≤li≤1,000,000,000

## 输出

对于每组数据，输出一行，两个数x,yx,y，以一个空格分隔，分别代表新的钢管可能长度的最小值xx和最大值yy

## 输入样例

```
4
2
5 5
3
1 4 3
4
1 5 2 1
4
1 6 7 9
```

## 输出样例

```
10 10
4 7
2 7
7 16
```

## 思路

这题跟算法好像也没有卵关系...

# `G` jhljx的最长零子数组

时间限制：1000ms  内存限制：65536kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

jhljx非常喜欢数组。现在他有一个只含有1和-1的数组。
他希望子数组的所有元素和为0，并且保证该子数组的长度最长。
求出最长sum和为0的子数组的长度。

## 输入

输入多组数据。 每组数据第一行为一个正整数n(1<=n<=5000000)，第二行为n个为1或-1的元素。

## 输出

求出最长零子数组的长度。

## 输入样例

```
10
1 -1 1 1 -1 -1 -1 1 1 1
```

## 输出样例

```
8
```

## 题目来源

改编自猿题库2016校招笔试

## 思路

较为简单，通过前缀和+哈希表进行记录，前缀和相同的即为其中一组解

找到最大解即可

# `H` jhljx上大学学数学

时间限制: 300 ms 内存限制: 65536 kb

通过率：/ `(%) `  正确率：/ `(%)`

## 题目描述

jhljx上了大学来学数学，有一天他发现了一个有趣的式子。
$$
A_n=(3+\sqrt5)^n
$$
于是乎，他想求出An的整数部分到底是多少。

## 输入

输入多组数据。
每组数据为一个正整数n(1<=n<=10181018)。

## 输出

输出An的整数部分后5位。

## 输入样例

```
1
2
```

## 输出样例

```
00001
00027
```

## 题目来源

阿里2016校招笔试（C++工程师及Java工程师笔试选择题）

## 思路

这题直接高精肯定会废掉

而且n的数非常大，这题必然是要用到快速幂的

可以通过以下方面去下手

(3+√5)^n = An +Bn √5

(3-√5)^n = An - Bn√5

然后就有(3+√5)^n = 2An - (3-√5)^n

整数部分就是2An-1

然后递推。假设(3+√5)^(n+1)=An+1+Bn+1√5，那么An+1=3An+5Bn Bn+1 = An+3Bn

所以这个时候就可以用矩阵乘法来表示了，然后就是矩阵快速幂，只要求出其n次方就可以了