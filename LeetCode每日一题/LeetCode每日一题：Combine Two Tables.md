# LeetCode每日一题：Combine Two Tables

## 问题描述

> Table: `Person`
>
> ```
> +-------------+---------+
> | Column Name | Type    |
> +-------------+---------+
> | PersonId    | int     |
> | FirstName   | varchar |
> | LastName    | varchar |
> +-------------+---------+
> PersonId is the primary key column for this table.
>
> ```
>
> Table: `Address`
>
> ```
> +-------------+---------+
> | Column Name | Type    |
> +-------------+---------+
> | AddressId   | int     |
> | PersonId    | int     |
> | City        | varchar |
> | State       | varchar |
> +-------------+---------+
> AddressId is the primary key column for this table.
> ```
>
> Write a SQL query for a report that provides the following information for each person in the Person table, regardless if there is an address for each of those people:
>
> ```
> FirstName, LastName, City, State
> ```

## 问题分析

合并两个表格，且使用左连接。


![LEFT JOIN.png](http://upload-images.jianshu.io/upload_images/2210250-a7a7ed7ef5c927e3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 代码实现

```MySQL
SELECT Person.FirstName,Person.LastName,Address.City,Address.State
FROM Person LEFT OUTER JOIN Address
ON Person.PersonId=Address.PersonId;
```