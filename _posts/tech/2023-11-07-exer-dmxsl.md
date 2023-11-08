---
layout: post
title: "exer-dmsxl"
date: 2023-11-07
permalink: /tech/exer-dmsxl/
---
目录<br>
<a href ="#1"> 1 回溯算法 </a> <br>
<a href ="#2"> 2 贪心算法 </a> <br>  


# <div id ="1"></div> 1 回溯算法


# <div id ="2"></div> 2 贪心算法
## 分发饼干

> https://leetcode.cn/problems/assign-cookies/description/<br>

### 实现1（时间复杂度太高）
对`s[]`进行升序排序<br>
遍历`g[]`，对于`g[i]`，将与`s[]`中的元素从小到大进行对比，判断能否获得饼干
```
class Solution {
    public int findContentChildren(int[] g, int[] s) {
        int sum = 0;
        for(int i = 0; i < s.length; i++ ){
            for(int j = 1; j < s.length - i; j++){
                if(s[j] < s[j - 1]){
                    int temp = s[j];
                    s[j] = s[j - 1];
                    s[j - 1] = temp;
                }
            }
        }
        for(int i = 0; i < g.length;i++){
            for(int j = 0; j < s.length; j++){
                if(s[j] >= g[i]){
                    sum++;
                    s[j] = 0;
                    break;
                }
            }

        }

        return sum;
    }
}
```

### 实现2
实现1在判断过程中，使用了双层`for`循环，考虑优化。<br>
实现1的排序算法时间复杂度$O(n^2)$也要优化，`Arrays.sort()`时间复杂度为$O(nlogn)$。<br>

优先考虑饼干：
```
class Solution {
    public int findContentChildren(int[] g, int[] s) {
        int sum = 0;
        Arrays.sort(s);
        Arrays.sort(g);
        for(int i = 0, j = 0; i < s.length && j < g.length;i++){
            if(s[i] >= g[j]){
                sum++;
                j++;
            }
        }
        return sum;
    }
}
```

