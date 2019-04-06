
1、导入

（1）数据文件导入：

LOAD DATA INFILE '文件路径和文件名' INTO TABLE 表名字;
1

（2）用SQL语句导入：

source *.sql

   

两者之间的不同是：数据文件导入方式只包含数据，导入规则由数据库系统完成；SQL 文件导入相当于执行该文件中包含的 SQL 语句，可以实现多种操作，包括删除，更新，新增，甚至对数据库的重建。
2、导出

导出与导入是相反的过程，是把数据库某个表中的数据保存到一个文件之中。导出语句基本格式为：

SELECT 列1，列2 INTO OUTFILE '文件路径和文件名' FROM 表名字;

  

**练习1**
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

**练习2**
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

**练习3**
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

**练习4**
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

**练习5**
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

**练习6**
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)
