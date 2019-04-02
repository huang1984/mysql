
创建表
CREATE TABLE World (
name VARCHAR(50) NOT NULL,
continent VARCHAR(50) NOT NULL,
area INT NOT NULL,
population INT NOT NULL,
gdp INT NOT NULL
);
-- 插入数据
INSERT INTO World
  VALUES('Afghanistan','Asia',652230,25500100,20343000);
INSERT INTO World 
  VALUES('Albania','Europe',28748,2831741,12960000);
INSERT INTO World 
  VALUES('Algeria','Africa',2381741,37100000,188681000);
INSERT INTO World
  VALUES('Andorra','Europe',468,78115,3712000);
INSERT INTO World
  VALUES('Angola','Africa',1246700,20609294,100990000);



查询
elect  name,population,area 
  from World 
 where population>25000000 or (area>3000000 and gdp>20000000);

![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

SELECT
	email AS Email 
FROM
	`email` 
GROUP BY
	email 
HAVING
	COUNT( email ) > 1


![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

2. SQL是什么？MySQL是什么？

3. 查询语句 SELECT FROM 

    语句解释
    
    去重语句
    
    前N个语句
    
    CASE...END判断语句
    
4. 筛选语句 WHERE 
    语句解释
    
    运算符/通配符/操作符
    
    
5. 分组语句 GROUP BY

    聚集函数
    
    语句解释
    
    HAVING子句
    
6. 排序语句 ORDER BY 

    语句解释
    
    正序、逆序
    
7. 函数

    时间函数
    
    数值函数
    
    字符串函数
    
8. SQL注释

9. SQL代码规范
    [SQL编程格式的优化建议] https://zhuanlan.zhihu.com/p/27466166
    [SQL Style Guide] https://www.sqlstyle.guide/

### 1.sql是什么？

SQL是Structured Query Language(结构化查询语言)的缩写。SQL是专为数据库而建立的操作命令集，是一种功能齐全的数据库语言。在使用它时，只需要发出“做什么”的命令，“怎么做”是不用使用者考虑的。SQL功能强大、简单易学、使用方便，已经成为了数据库操作的基础，并且现在几乎所有的数据库均支持SQL。

### MySQL是什么
MySQL是一个关系型数据库管理系统，由瑞典MySQL AB 公司开发，目前属于 Oracle 旗下产品。MySQL 是最流行的关系型数据库管理系统之一，在 WEB 应用方面，MySQL是最好的 RDBMS (Relational Database Management System，关系数据库管理系统) 应用软件。
MySQL是一种关系数据库管理系统，关系数据库将数据保存在不同的表中，而不是将所有数据放在一个大仓库内，这样就增加了速度并提高了灵活性。
MySQL所使用的 SQL 语言是用于访问数据库的最常用标准化语言。MySQL 软件采用了双授权政策，分为社区版和商业版，由于其体积小、速度快、总体拥有成本低，尤其是开放源码这一特点，一般中小型网站的开发都选择 MySQL 作为网站数据库。

### 查询语句 SELECT FROM 
Select productNAME

  from products；
  
  productNAME是列名，用来选需要查询的列，如查询多列，用,隔开即可，products是表名。Select和form是SQL的关键字，也叫保留字，关键字有特殊含义，不来用来做表名和列名。
  
另外，SQL不区分大小写，也没有空格、提行等要求要求。我的习惯是和英语一致，语句首字母大写，后面小写，并且有一些提行，语句结束有分号。（和一般的关键字全大写不太一样）

Select distinct productline

  from products;

distinct是实现去除重复的关键字。

Select productline

  from products
  
 limit 1,5;

   
前N行用limit实现，1,5表示从第2行开始的前5行结果，（MySQL和C，python一样也是从0开始编号）。如果从1行开始，0可以不写。

   Select checkNumber,case when amount>1e5 then'优秀' 
   
    		 			   when amount<=1e5 then'良好' 
                           
    				       end as '总计'
     from payments;

   
CASE…END判断语句，用来根据查询数据新建一列。


### 筛选语句 WHERE 语句解释



运算符/通配符/操作符：

比较运算符(大小比较)：>、>=、=、<、<=、<>、!>、!<

范围运算符(表达式值是否在指定的范围)：BETWEEN…AND… NOT BETWEEN…AND…

列表运算符(判断表达式是否为列表中的指定项)：IN (项1,项2……) NOT IN (项1,项2……)

模式匹配符(判断值是否与指定的字符通配格式相符):LIKE、NOT LIKE

空值判断符(判断表达式是否为空)：IS NULL、NOT IS NULL

逻辑运算符(用于多条件的逻辑连接)：NOT、AND、OR

1、范围运算符例：age BETWEEN 10 AND 30相当于age>=10 AND age<=30

2、列表运算符例：country IN (‘Germany’,‘China’)

3、模式匹配符例：常用于模糊查找，它判断列值是否与指定的字符串格式相匹配。可用于char、 varchar、text、ntext、datetime和smalldatetime等类型查询。

可使用以下通配字符：
百分号%：可匹配任意类型和长度的字符，如果是中文，请使用两个百分号即%%。

下划线_：匹配单个任意字符，它常用来限制表达式的字符长度。


方括号[]：指定一个字符、字符串或范围，要求所匹配对象为它们中的任一个。

[^]： 其取值也[] 相同，但它要求所匹配对象为指定字符以外的任一个字符。


### 分组语句 GROUP BY

聚集函数：对某些行运行的函数，计算并返回一个值，如AVG、COUNT、SUM、MAX、MIN等

语句解释：GROUP BY按列名排序并分组数据，对每个组进行聚集

HAVING子句：过滤分组

### 排序语句 ORDER BY
语句解释：根据列名对输出进行排序
正序、逆序：默认或ASC正序（升序）；DESC逆序（降序）

### 函数
时间函数：YEAR、DATE、TIME、DATETIME、TIMESTAMP等

数值函数：ABS、COS、EXP、SQRT等

字符串函数：文本处理函数，如LEFT、RIGHT、LOWER、UPPER、LENGTH、LTRIM、RTRIM、SOUNDEX等


[函数汇总表]（http://www.runoob.com/mysql/mysql-functions.html）

### 8 SQL注释

SQL语句中的单行注释使用--，多行注释采用/*…*/

### 9 SQL代码规范

[SQL编程格式的优化建议] https://zhuanlan.zhihu.com/p/27466166

[SQL Style Guide] https://www.dsqlstyle.guide/


```python



```
