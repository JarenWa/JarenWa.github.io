---
layout: post
title: "java-collection_map"
date: 2023-11-14
permalink: /tech/javase/java-collection_map/
---
<p style="font-size:20px;">Java-Collection_Map</p>
<p style="font-size:20px;">目录</p>
<a href ="#1"> 1 集合框架概述  </a><br>
<a href ="#2"> 2 Collection 接口及方法 </a><br>
<a href ="#3"> 3 Iterator(迭代器)接口 </a><br>

 
 


<h1 id="1"> 1 集合框架概述</h1><br>

数组在内存存储方面的特点：
* 数组初始化以后，长度就确定了。
* 数组中的添加的元素是依次紧密排列的，有序的，可以重复的。
* 数组声明的类型，就决定了进行元素初始化时的类型。不是此类型的变
量，就不能添加。
* 可以存储基本数据类型值，也可以存储引用数据类型的变量

数组在存储数据方面的弊端：
* 数组初始化以后，长度就不可变了，不便于扩展
* 数组中提供的属性和方法少，不便于进行添加、删除、插入、获取元素个
数等操作，且效率不高。
* 数组存储数据的特点单一，只能存储有序的、可以重复的数据


## Java 集合框架体系
Java 集合框架中的类可以用于存储多个对象，还可用于保存具有映射关系的关联数组。

Java 集合可分为 Collection 和 Map 两大体系：
* Collection 接口：用于存储一个一个的数据，也称单列数据集合。

        List 子接口：用来存储有序的、可以重复的数据（主要用来替换数组，"动态"数组）
            实现类：ArrayList(主要实现类)、LinkedList、Vector

        Set 子接口：用来存储无序的、不可重复的数据（类似于高中讲的"集合"）
            实现类：HashSet(主要实现类)、LinkedHashSet、TreeSet

* Map 接口：用于存储具有映射关系“key-value 对”的集合，即一对一对的数据，也称双列数据集合。(类似于高中的函数、映射。(x1,y1),(x2,y2) ---> y = f(x) )

        HashMap(主要实现类)、LinkedHashMap、TreeMap、Hashtable、Properties

<h1 id="2">2 Collection 接口及方法</h1><br>



<h1 id="3">3 Iterator(迭代器)接口 </h1><br>

## Iterator
与Collection、Map 接口有所不同
* Collection 接口与 Map 接口主要用于存储元素
* Iterator，被称为迭代器接口，本身并不提供存储对象的能力，主要用于
遍历 Collection 中的元素




