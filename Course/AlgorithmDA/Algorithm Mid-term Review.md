# Algorithm Mid-term Review

<center>Nobember 2020</center>

## Preface. 基础

### 一些概念

- Loop invariant 循环不变式：问题的某一部分的不变的性质，如 A[1..j-1] 已经排好了序。
-  :star: 多重对数函数：$lg *n$ 表示多重对数（区别于 $f^{(i)}(n)$，其表示多重函数）

![image-20201117182123136](https://billc.oss-cn-shanghai.aliyuncs.com/file/2020-11-17-image-20201117182123136.png)

### 算法的一般特性

- **有穷性：** 一个算法必须保证执行**有限步**之后结束；
- **确切性：** 算法的每一步骤必须有**确切的定义**；
- **输 入：**一个算法有0个或多个输入，以刻画运算对象的初始情况，所谓0个输入是指算法本身限定了初始条件；
- **输 出：一个算法有一个或多个输出，以反映对输入数据加工后的结果。没有输出的算法是毫无意义的；
- **可行性：** 算法原则上能够**精确地运行**，而且人们用笔和纸做**有限次运算**后即可完成。

如何衡量效率（efficiency）：

- 精度和可操作性之间的权衡（trade-off between precision and operability）

### 函数增长

几个渐进函数：

- $\Theta$ ：渐进准确界
- $O$： 准确上界 => $o$ 不准确上界
- $\Omega$： 准确下界 => $\omega$ 不准确下界

![image-20201117181200488](https://billc.oss-cn-shanghai.aliyuncs.com/file/2020-11-17-image-20201117181200488.png)

形式化定义：

> O(g(n)) ={ f(n) ：存在正常量 c、$n_0$，使 $\forall n \ge n_0,, 0 \le f(n) \le cg(n)$ }
>
> o(g(n)) ={ f(n) ：存在正常量 c、$n_0$，使 $\forall n \ge n_0,, 0 \le f(n) \lt cg(n)$ }

（非紧张确界的差别：趋近与无穷是是否相等）

Eg.

![image-20201117185132048](../../../../Library/Application%20Support/typora-user-images/image-20201117185132048.png)

Eg2. 注意 $n^{lgc}$ 和 $c^{lgn}$ 的等价性

![image-20201117185511332](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-11-17-ksFdRO.png)

## Divide & Conquer

### 求解方法

- 代入法
- ![image-20201117191152469](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-11-17-zX077y.png)
  - 对于所有 c >= 1，最后一个步骤都成立
  - 类似于数学归纳法的思路
- 递归树法
  - ![image-20201117191326515](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-11-17-lxEFdU.png)
- :star: 主方法

![image-20201117190153085](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-11-17-KJ7Pjy.png)

也可以使用原始的方法，直接代入进行计算。

![image-20201117194658364](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-11-17-VWouY7.png)

## Sorting

### Heap Sort

节点的高度：该节点到叶节点最长简单路径上边的数目

堆的高度：根节点的高度

- 每个孩子的子树的大小至多为 2n/3。

### Quicksort

运行过程：

![image-20201118002705194](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-11-18-UQoSi4.png)

### Counting Sort

使用三个数组，B 存放输出、A 原数组、C 存放临时

![image-20201118004955871](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-11-18-fy2Hp7.png)

### Bucket Sort & Radix Sort

简单的排序。对于桶排序，可以在内部使用 merge sort 来将最差复杂度减少一些。

## Dynamic Programming

### 矩阵链乘法

递归式：
$$
m[i, j]=\left\{\begin{array}{ll}
0 & \text { if } i=j \\
\min _{i \leq k<j}\left\{m[i, k]+m[k+1, j]+p_{i-1} p_{k} p_{j}\right\} & \text { if } i<j
\end{array}\right.
$$
m[ij] 为 i 到 j 之间的最优解， s 存放最优分隔的地点。

Eg.



![image-20201118152456084](https://billc.oss-cn-shanghai.aliyuncs.com/img/2020-11-18-dlAz4d.png)

