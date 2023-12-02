---
layout: post
title: "java-collection_map"
date: 2023-11-14
permalink: /tech/javase/java-collection_map/
---
<div align="center">
    <h1>Collection</h1>

</div>
 
<!-- TOC -->

- [0 补充](#0-补充)
    - [泛型](#泛型)
    - [多态](#多态)
- [1 集合框架概述](#1-集合框架概述)
    - [Java 集合框架体系](#java-集合框架体系)
- [2 Collection 接口及方法](#2-collection-接口及方法)
    - [List接口(对付顺序的好帮手): 存储的元素是有序的、可重复的](#list接口对付顺序的好帮手-存储的元素是有序的可重复的)
        - [ArrayList](#arraylist)
        - [LinkedList --是一个双向链表（只是没有用 DoubleLinkedList 这个类名）](#linkedlist---是一个双向链表只是没有用-doublelinkedlist-这个类名)
        - [Vector](#vector)
    - [Set接口(注重独一无二的性质): 存储的元素不可重复的。](#set接口注重独一无二的性质-存储的元素不可重复的)
    - [Queue接口(实现排队功能的叫号机)](#queue接口实现排队功能的叫号机)
- [3 Map接口](#3-map接口)
    - [Map接口(用 key 来搜索的专家)](#map接口用-key-来搜索的专家)
        - [HashMap](#hashmap)
        - [LinkedHashMap](#linkedhashmap)
        - [Hashtable](#hashtable)
        - [TreeMap](#treemap)
- [4 Iterator(迭代器)接口](#4-iterator迭代器接口)
    - [Iterator](#iterator)

<!-- /TOC -->



# 0 补充
## 泛型

尖括号中的类型参数可以是任何合法的Java类型，包括原始类型（如 int、char 等）和自定义类、接口等。

## 多态

# 1 集合框架概述

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

        Queue

* Map 接口：用于存储具有映射关系“key-value 对”的集合，即一对一对的数据，也称双列数据集合。(类似于高中的函数、映射。(x1,y1),(x2,y2) ---> y = f(x) )

        HashMap(主要实现类)、LinkedHashMap、TreeMap、Hashtable、Properties

# 2 Collection 接口及方法
<a href="https://javaguide.cn/java/collection/java-collection-questions-01.html" target="_blank">Java集合常见面试题总结————JavaGuide</a>

## List接口(对付顺序的好帮手): 存储的元素是有序的、可重复的
```
// 继承于 Collection
public interface List<E> extends Collection<E> {}
```
### ArrayList
线程不安全。不需要线程安全的特性，推荐使用 ArrayList，因为它在大多数情况下具有更好的性能。
```
public class ArrayList<E> 
    extends AbstractList<E>
    implements List<E>, RandomAccess, Cloneable, java.io.Serializable {}
```

```
// Creating an object of List interface
// implemented by the ArrayList class
// 多态性
List<Integer> l1 = new ArrayList<Integer>();
ArrayList<Integer> l11 = new ArrayList<Integer>();
// 虽然 ArrayList 实现了多个接口，但 List 接口是其中一个核心接口，它提供了对列表的常见操作和方法。从列表操作的角度来看，这两种方式是等效的。
```

### LinkedList --是一个双向链表（只是没有用 DoubleLinkedList 这个类名）
```
public class LinkedList<E> 
    extends Abstract SequentialList<E>
    implements List<E>, Deque<E>, Cloneable, java.io.Serializable {}
```

### Vector
线程安全
```
public class Vector<E>
    extends AbstractList<E>
    implements List<E>, RandomAccess, Cloneable, java.io.Serializable {}
``` 

## Set接口(注重独一无二的性质): 存储的元素不可重复的。


## Queue接口(实现排队功能的叫号机)


# 3 Map接口
## Map接口(用 key 来搜索的专家)
使用键值对（key-value）存储，类似于数学上的函数 y=f(x)，"x" 代表 key，"y" 代表 value，key 是无序的、不可重复的，value 是无序的、可重复的，每个键最多映射到一个值

```
public interface Map<K, V> {}
```

### HashMap
```
public class HashMap<K,V> 
    extends AbstractMap<K,V>
    implements Map<K,V>, Cloneable, Serializable {}
```

### LinkedHashMap

### Hashtable

### TreeMap





# 4 Iterator(迭代器)接口

## Iterator
与Collection、Map 接口有所不同
* Collection 接口与 Map 接口主要用于存储元素
* Iterator，被称为迭代器接口，本身并不提供存储对象的能力，主要用于
遍历 Collection 中的元素






