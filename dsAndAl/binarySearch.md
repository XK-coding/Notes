# 二分查找

leetcode704

需求：在有序数组a内，查找值target

- 如果找到返回索引
- 如果找不到返回-1

## 算法描述

![image-20231129125732346](https://img-blog.csdnimg.cn/direct/8a505bd879ed480590d0c70bd5a69b22.png)


## 二分查找基础版

```java
//二分查找算法实现
//params：a为待查找的升序数组，target为待查找的目标值
//returns：找到则返回索引，找不到返回-1
public static int binarySearch(int[] a, int target){
    int i = 0, int j = a.length - 1;		//设置指针和初值
    while(i <= j){		//i~j 范围内有东西
        int m = (i + j) >>> 1;		//取中间值，向下取整
        if(target < a[m]){		//目标值在左边
            j = m - 1;
        }
        else if(a[m] < target){		//目标值在右边
            i = m + 1;
        }
        else{		//找到了目标值
            return m;
        }
    }
    return -1;		//没有找到，返回-1（就是不存在，因为如果存在至少为0）
}
```

**问题1**：为什么是i <= j 意味着区间内有未比较的元素，而不是i < j

答：i == j意味着它们指向的元素也会参与比较，i < j 只意味着m指向的元素参与比较



**问题2**：(i + j) / 2有没有问题？

答：有问题，同一个二进制数，在不同的语言当中，有的会把最高位视为符号位，有的并不会，这样子会导致同一个二进制数代表了两个不同的十进制数，因此这样子写会有局限性，不能超过整型的最大值

解决方法：用java无符号右移运算符即可解决这个问题	(i + j) >>> 1

**问题3**：都写成小于号有什么好处？

答：按照数组升序排列的话，都写成小于号可以更直观的看出大小即右边的比左边的大



## 二分查找改动版

```java
public static int binarySearchAlternative(int[] a, int target){
    int i = 0, int j = a.length;		//第一处
    while (i < j){			//第二处
        int m = (i + j) >>> 1;
        if (target < a[m]){
            j = m;			//第三处
        }
        else if (a[m] < target){
            i = m + 1;
        }
        else{
            return m;
        }
    }
    return -1;
}
```

改动

- 第一处：j只是作为边界，一定不是查找目标
- 第二处：如果加上等于，会在某些情况下陷入死循环，比如要查找的数组内没有目标值
- 第三处：如果 j = m-1，那么会漏掉查找目标，j一定不会参与比较