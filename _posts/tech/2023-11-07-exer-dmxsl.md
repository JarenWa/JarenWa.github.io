---
layout: post
title: "exer-dmsxl"
date: 2023-11-07
permalink: /tech/exer-dmsxl/
---
<p style="font-size:20px;">目录</p>
<a href ="#1"> 1 回溯算法 </a><br>
<a href ="#2"> 2 贪心算法 </a><br>



<h1 id="1"> 1 回溯算法</h1>
递归函数的参数和返回值<br>
确定终止条件<br>
单层递归逻辑<br>

## x 组合
<a href="https://leetcode.cn/problems/combinations/" target="_blank">力扣</a> <br>


## 4 组合总和III
<a href="https://leetcode.cn/problems/combination-sum-iii/" target="_blank">力扣</a> <br>
### 实现1
沿用前面的方法，数字1-9,找k个数字（不重复）的组合，求和等于n的才进入返回结果。


## 7 组合总和

<a href="https://leetcode.cn/problems/combination-sum/" target="_blank">力扣</a>

思考：如何实现重复使用每个候选元素，如何保证组合结果不重复？
```
class Solution {
    List<List<Integer>> result = new ArrayList<>();
    LinkedList<Integer> path = new LinkedList<>(); 

    public List<List<Integer>> combinationSum(int[] candidates, int target) {
        solution(candidates, target, 0, 0);
        return result;
    }
    public void solution(int[] candidates, int target, int sum, int start){
        if(sum > target){
            return;
        }
        if(sum == target){
            result.add(new ArrayList<>(path));
            return;
        }
        for(int i = start ;i< candidates.length;i++){
            path.add(candidates[i]);
            sum += candidates[i];
            solution(candidates, target,sum, i);
            sum -= candidates[i];
            path.removeLast();
        }
    }
   
}
```



<h1 id ="2"> 2 贪心算法</h1>

## 2 分发饼干
<a href="https://leetcode.cn/problems/assign-cookies/description/" target="_blank">力扣</a>
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
实现1的排序算法时间复杂度 <em>O(n<sup>2</sup>)</em> 也要优化，`Arrays.sort()`时间复杂度为 <em>O(nlogn) </em>。<br>

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

