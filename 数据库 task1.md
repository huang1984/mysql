


MySQL 软件安装及数据库基础

#任务时间#
请于3月31日22:00前完成，在本文章评论打卡。逾期尚未打卡的会被清退。

#学习内容#
1.软件安装及服务器设置。
教程 http://www.runoob.com/mysql/mysql-install.htm

2.(选做，但是强烈建议) 使用图形界面软件 Navicat for SQL
群里提供破解版Navicat for SQL，看群公告或聊天记录搜索888查找。
简易步骤:
解压缩文件，复制key
打开文件夹中的navicat.e
用户名随意，输入key，然后连d接数据库
输入密码，连接名改成自己喜欢的
剩下的自己探索，怎么在navicat中创建数据库、表等等

3.数据库基础知识
数据库定义
关系型数据库
二维表
行
列
主键
外键

4.MySQL数据库管理系统
数据库
数据表
视图
存储过程


**mysql之前就安装了，还有sqlyog**


**数据库定义**：将大量数据保存起来，通过计算机加工而成的可以进行高效访问的数据集合。如：大型-银行存储的信息，小型-电话簿。

**关系型数据库**：目前应用最广泛的数据库。

**二维表**：二维表就是由行列组成的，知道行号列号就可以确定一个表中的数据，这是二维表的特点。在关系数据库中,存放在数据库中的数据的逻辑结构以二维表为主.

在二维表中惟一标识元组的最小属性值称为该表的键或码。二维表中可能有若干个健，它们称为表的侯选码或侯选健。从二维表的所有侯选键选取一个作为用户使用的键称为主键或主码。表A中的某属性集是某表B的键，则称该属性值为A的外键或外码。

**行**：表中的一个记录

**列**：表中的一个字段。所有表都是由一个或多个列组成。

**主键**：一列（一组列），其值能够唯一识别表中每一行。

**外键**：如果公共关键字在一个关系中是主关键字，那么这个公共关键字被称为另一个关系的外键。由此可见，外键表示了两个关系之间的相关联系。以另一个关系的外键作主关键字的表被称为主表，具有此外键的表被称为主表的从表。**外键又称作外关键字**

4.MySQL数据库管理系统

**数据库**：将大量数据保存起来，通过计算机加工而成的可以进行高效访问的数据集合

**数据表**：数据表(或称表)是数据库最重要的组成部分之一。数据库只是一个框架，数据表才是其实质内容。

**视图**：视图是虚拟的表。与包含数据的表不一样，视图只包含使用时动态检索数据的查询。

**存储过程**：存储过程就是为以后使用而保存的一条或多条SQL语句。可以将其视为批文件，虽然他们的作用不仅限于批处理
