---
layout: post
title: 桶排序
---
## 一、简介 ##  

&#160;&#160;&#160;&#160;桶排序 (Bucket sort)或所谓的箱排序，是一个排序算法，工作的原理是将数组分到有限数量的桶子里。每个桶子再个别排序（有可能再使用别的排序算法或是以递归方式继续使用桶排序进行排序）。桶排序是鸽巢排序的一种归纳结果。当要被排序的数组内的数值是均匀分配的时候，桶排序使用线性时间（Θ（N））。但桶排序并不是比较排序，他不受到 O(N log N) 下限的影响。  
&#160;&#160;&#160;&#160;桶排序是一种稳定的排序；  
&#160;&#160;&#160;&#160;对N个关键字进行桶排序的时间复杂度分为两个部分：一是循环计算每个关键字的桶映射函数，这部分的时间复杂度为O(N)；另一部分是每个桶内排序的时间复杂度的和。由此可见，提高效率的方法，应该是增加桶的数量，减少每个桶内的排序，但是桶的数量过多会造成空间浪费严重。  

## 二、简单实现 ##

	/**
	*一个简单的桶排序，0~1000的数字进行倒序排序，每个数字占用一个桶，桶内无排序
	*/
	#include <stdio.h>

	void main() {
		int a[1001],i,j,t,n;
		for (i = 0; i <= 1000; i++) {
			a[i] = 0; // 初始化“桶”
		}
		scanf("%d",&n); //接收一个输入，表示接下来要排序几个数，存放在n中
		for (i = 1; i <= n; i++) {
			scanf("%d",&t); //接收需要排序的数字
			a[t]++; //对应的桶里个数+1
		}
		for(i=1000;i>=0;i--){  //依次判断编号1000~0的桶
			for(j=1;j<=a[i];j++){  //出现了几次就将桶的编号打印几次
				printf("%d ",i);
			}
		}
	}

## 三、适用场景 ##  

&#160;&#160;&#160;&#160;输入数据呈均匀分布，如输入数据平均分布再某个区间内。  
&#160;&#160;&#160;&#160;举例来说，比如高考考生成绩排序，考生成绩总数量很大，但是大部分区域满分都是750分，这样的话，最多751个桶，就可以很快的完成排序。  

## 四、排序过程 ##  
&#160;&#160;&#160;&#160;以上面的简单实现为例，假如需要把 1、10、25、66、999、1000、25 这几个数字排序，在这几个数字输入后，a[1] = 1，a[10] = 1，a[25] = 2，a[66] = 1，a[999] = 1，a[1000] = 1，数组元素里存放的数字，表示桶所代表的数字出现的次数，然后再从按下标从大到小进行轮询，其值为几就将其下标打印几次，整个排序就完成了（当然还打印好了）。  
&#160;&#160;&#160;&#160;这是一个很典型的例子，从这个例子可以看出，桶排序并不是比较排序。