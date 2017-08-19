算法导论代码实现
========

算法导论日常更新中。。。
****
### Author:Song
### E-mail:Z.S.Chang@qq.com
****
## 目录
* [chapter02](https://github.com/Changzhisong/Introduction_to_Algorithms/tree/master/chapter02 "跳转到chapter02")
	* 插入排序
	* 选择排序
	* 归并排序
	* 冒泡排序
* [chapter03](https://github.com/Changzhisong/Introduction_to_Algorithms/tree/master/chapter03 "跳转到chapter03")
	* ***更新中...***
	
	
***
---
___

更新日志
-------
#### \######2017-8-12######
* 插入排序【O(n^2)】  
		通过构建有序序列，在已经排序的序列中从后面向前扫描，找到相应的位置并插入。
		换句话说，每次从剩余数组中拎出一个元素，与有序数组从后往前对比，直到插入合
		适的位置，然后剩余数组缩小规模在循环插入。（类似于抓牌后整理牌）  
![动画演示](https://github.com/Changzhisong/Introduction_to_Algorithms/blob/master/chapter02/Doc/Insertion-sort1.gif)  
* 选择排序【O(n^2)】  
		找出数组A中最小的元素并将其与A[0]进行交换，接着，找出A中第二小的元素与A[1]
		交换。对A中前n-1个元素按该方式交换。  
![动画演示](https://github.com/Changzhisong/Introduction_to_Algorithms/blob/master/chapter02/Doc/Selection-Sort.gif)  

-----
#### \######2017-8-15######
* 归并排序【O(nlgn)】  
		***分治思想：***  
		将原问题分解为n个规模较小但类似于原问题的子问题，递归地求解这些子问题，然后
		再合并这些子问题的解来建立原问题的解。  
		***合并思想：***  
		有两组各自有序的数组及两个指针且两个指针分别指向两个数组的首位置。首先两个0
		位置的数进行比较，较小的放到新数组中，且该数组指针+1，然后再比较两个指针指向
		的数组的元素，将小的放到新数组中，指针+1，最后直到某一组的哨兵（+∞）出现（也
		可以不使用哨兵，但需判断两个数组的长度），则另外一组的剩余的元素全部加入到新
		的数组中。    
		***优化***  
		在归并排序中对小的子数组采用插入排序：  
		在排序长度为k的n/k个子数组采用插入排序，使得最后整个排序运行时间为 ***O(nk+nlg(n/k))***  
![动画演示](https://github.com/Changzhisong/Introduction_to_Algorithms/blob/master/chapter02/Doc/Merge-sort.gif)
		
* 冒泡排序【O(n^2)】  
		重复的走访要排列的序列，依次比较相邻的两个元素，如果顺序相反就交换过来，直到
		没有需要再交换。  
![动画演示](https://github.com/Changzhisong/Introduction_to_Algorithms/blob/master/chapter02/Doc/Bubble-Sort.gif)  

-----
#### \######2017-8-17######
* 渐进记号的定义  
		***1. Θ(big-theta)***  
		`方式一：`设f(n)和g(n)是定义域为自然数集合的函数。如果$\mathop{\lim}\limits_{x\to ∞}\frac{f(n)}{g(n)}$存在，并且等于某个常数c(c>0)，那么f(n)=Θ(g(n))。通俗理解为f(n)和g(n)同阶，Θ用来表示算法的精确阶。  
		`方式二：`Θ(g(n))={f(n):存在正常量$c_1$、$c_2$和$n_0$，使得对所有n≥$n_0$，有 **0≤$c_1$g(n)≤f(n)≤$c_2$g(n)}**  若存在正常量$c_1$、$c_2$，使得对于足够大的n，函数f(n)能“夹入”$c_1$g(n)与$c_2$g(n)之间，则f(n)属于集合Θ(g(n))，记作f(n)∈Θ(g(n))。作为代替，我们通常记“f(n)=Θ(g(n))”。  
		***2. O(big-oh)***  
		设f(n)和g(n)是定义域为自然数集N上的函数。若存在正数c和$n_0$，使得对一切n≥$n_0$都有 **0≤f(n)≤cg(n)** 成立，则称f(n)的渐进的上界是g(n)，记作f(n)=O(g(n))。通俗的说n满足一定条件范围内，函数f(n)的阶不高于函数g(n)。  
		通常有：***O(1)<O(log(n))<O(n)<O(nlogn)<O($n^2$)<O($2^n$)<O(n!)<O($n^n$)***  
		***3. Ω(big-omege)***  
		设f(n)和g(n)是定义域为自然数集N上的函数。若存在正数c和$n_0$，使得对一切n≥$n_0$都有 **0≤cg(n)≤f(n)** 成立，则称f(n)的渐进的下界是g(n)，记作f(n)=Ω(g(n))。通俗的说n满足一定条件范围内，函数f(n)的阶不低于函数g(n)。  
		***4. o(小-oh)***  
		`定义1：`设f(n)和g(n)是定义域为自然数集合N的函数。如果$\mathop{\lim}\limits_{x\to ∞}\frac{f(n)}{g(n)}=0$，那么f(n)=o(g(n))。通俗理解为f(n)低于g(n)的阶。  
		`定义2：`若对于任意正数c，都存在$n_0$，使得对一切n≥$n_0$都有 **0≤f(n)<cg(n)** 成立，则称f(n)的渐进的非紧确上界是g(n)，记作f(n)=o(g(n))。通俗的说n满足一定条件范围内，函数f(n)的阶低于函数g(n)。  
		***5. ω(小-omege)***  
		`定义1：`设f(n)和g(n)是定义域为自然数集合的函数。如果$\mathop{\lim}\limits_{x\to ∞}\frac{f(n)}{g(n)}=∞$，那么f(n)=o(g(n))。通俗理解为f(n)高于g(n)的阶。  
		`定义2：`设f(n)和g(n)是定义域为自然数集N上的函数。若对于任意正数c，都存在$n_0$，使得对一切n≥n0都有 **0≤cg(n)<f(n)** 成立，则称f(n)的渐进的非紧确下界是g(n)，记作f(n)=ω(g(n))。通俗的说n满足一定条件范围内，函数f(n)的阶高于函数g(n)。   

* 渐近记号Θ、Ο、Ω、o、ω之间的关系

| 记号 | 含义  | 通俗理解 |
|:--------------:|:-------------------------:|:-------------------------:|
| Θ | 紧确界 | 相当于”=” |
| O | 上界   | 相当于”<=” |
| Ω | 下界   | 相当于”>=”|
| o | 非紧的上界   |  相当于”<” |
| ω | 非紧的下界   |  相当于”>” |

-----
#### \######2017-8-19######
		
		
		
		
		
		
		
		
		
		
		
		
		
