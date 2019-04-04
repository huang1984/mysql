
1. MySQL表数据类型

2. 用SQL语句创建表

    语句解释
    
    设定列类型 、大小、约束
    
    
    设定主键
    
3. 用SQL语句向表中添加数据

    语句解释
    
    多种添加方式（指定列名；不指定列名）
    
4. 用SQL语句删除表

    语句解释
    
    DELETE
    
    DROP
    
    TRUNCATE
    
    
    不同方式的区别
    
5. 用SQL语句修改表

    修改列名
    
    修改表中数据
    
    删除行
    
    删除列
    
    新建列
    
    新建行 

### MySQL 数据类型

MySQL中定义数据字段的类型对你数据库的优化是非常重要的。

MySQL支持多种类型，大致可以分为三类：数值、日期/时间和字符串(字符)类型。
#### 数值类型

MySQL支持所有标准SQL数值数据类型。

这些类型包括严格数值数据类型(INTEGER、SMALLINT、DECIMAL和NUMERIC)，以及近似数值数据类型(FLOAT、REAL和DOUBLE PRECISION)。

关键字INT是INTEGER的同义词，关键字DEC是DECIMAL的同义词。

BIT数据类型保存位字段值，并且支持MyISAM、MEMORY、InnoDB和BDB表。

作为SQL标准的扩展，MySQL也支持整数类型TINYINT、MEDIUMINT和BIGINT。下面的表显示了需要的每个整数类型的存储和范围。 
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

#### 日期和时间类型
表示时间值的日期和时间类型为DATETIME、DATE、TIMESTAMP、TIME和YEAR。
每个时间类型有一个有效值范围和一个"零"值，当指定不合法的MySQL不能表示的值时使用"零"值。
TIMESTAMP类型有专有的自动更新特性
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)


#### 字符串类型

字符串类型指CHAR、VARCHAR、BINARY、VARBINARY、BLOB、TEXT、ENUM和SET。
![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

CHAR 和 VARCHAR 类型类似，但它们保存和检索的方式不同。它们的最大长度和是否尾部空格被保留等方面也不同。在存储或检索过程中不进行大小写转换。

BINARY 和 VARBINARY 类似于 CHAR 和 VARCHAR，不同的是它们包含二进制字符串而不要非二进制字符串。也就是说，它们包含字节字符串而不是字符字符串。这说明它们没有字符集，并且排序和比较基于列值字节的数值值。

BLOB 是一个二进制大对象，可以容纳可变数量的数据。有 4 种 BLOB 类型：TINYBLOB、BLOB、MEDIUMBLOB 和 LONGBLOB。它们区别在于可容纳存储范围不同。

有 4 种 TEXT 类型：TINYTEXT、TEXT、MEDIUMTEXT 和 LONGTEXT。对应的这 4 种 BLOB 类型，可存储的最大长度不同，可根据实际情况选择。 

### MySQL 创建数据表

创建MySQL数据表需要以下信息：

    表名
    
    表字段名
    
    定义每个表字段

语法

以下为创建MySQL数据表的SQL通用语法：

CREATE TABLE table_name (column_name column_type);

以下例子中我们将在 RUNOOB 数据库中创建数据表runoob_tbl：

CREATE TABLE IF NOT EXISTS `runoob_tbl`(
   `runoob_id` INT UNSIGNED AUTO_INCREMENT,
   `runoob_title` VARCHAR(100) NOT NULL,
   `runoob_author` VARCHAR(40) NOT NULL,
   `submission_date` DATE,
   PRIMARY KEY ( `runoob_id` )
)ENGINE=InnoDB DEFAULT CHARSET=utf8;

实例解析：

    如果你不想字段为 NULL 可以设置字段的属性为 NOT NULL， 在操作数据库时如果输入该字段的数据为NULL ，就会报错。
    AUTO_INCREMENT定义列为自增的属性，一般用于主键，数值会自动加1。
    PRIMARY KEY关键字用于定义列为主键。 您可以使用多列来定义主键，列间以逗号分隔。
    ENGINE 设置存储引擎，CHARSET 设置编码。

通过命令提示符创建表

通过 mysql> 命令窗口可以很简单的创建MySQL数据表。你可以使用 SQL 语句 CREATE TABLE 来创建数据表。


 MySQL中删除数据表是非常容易操作的， 但是你再进行删除表操作时要非常小心，因为执行删除命令后所有数据都会消失。
语法

以下为删除MySQL数据表的通用语法：

**DROP TABLE table_name ;**

在命令提示窗口中删除数据表

在mysql>命令提示窗口中删除数据表SQL语句为 DROP TABLE ：
实例

以下实例删除了数据表runoob_tbl:

root@host# mysql -u root -p
Enter password:*******
mysql> use RUNOOB;
Database changed
mysql> DROP TABLE runoob_tbl
Query OK, 0 rows affected (0.8 sec)
mysql>



**DELETE**

DELETE FROM table_name;

    

或者

DELETE * FROM table_name;
 

    **TRUNCATE**

TRUNCATE TABLE table_name

DROP：删除表数据和表本身。真正意义上的删除表，操作前一定要小心。

DELETE：删除一行或者多行数据，不删除表本身。

TRUNCATE：仅删除表内数据，不删除表本身。

    小结

    DROP TABLE table_name : 删除表全部数据和表结构，立刻释放磁盘空间，不管是 Innodb 和 MyISAM;
        
    TRUNCATE TABLE table_name : 删除表全部数据，保留表结构，立刻释放磁盘空间 ，不管是 Innodb 和 MyISAM;
        
    DELETE FROM table_name : 删除表全部数据，表结构不变，对于 MyISAM 会立刻释放磁盘空间，InnoDB 不会释放磁盘空间;
        
    DELETE FROM table_name WHERE XXX : 带条件的删除，表结构不变，不管是 innodb 还是 MyISAM 都不会释放磁盘空间;
        
    DELETE 操作以后，使用 optimize TABLE table_name 会立刻释放磁盘空间，不管是 innodb 还是 myisam;
    
    DELETE FROM 表以后虽然未释放磁盘空间，但是下次插入数据的时候，仍然可以使用这部分空间。


###    修改列名及字段类型
    
    如果需要修改字段类型及名称, 你可以在ALTER命令中使用 MODIFY 或 CHANGE 子句。
    语法

-- 修改字段类型,修改字段c的类型为CHAR(10)
ALTER TABLE table_name MODIFY c CHAR(10);
-- 修改列名, 在 CHANGE 关键字之后，紧跟着的是你要修改的字段名，然后指定新字段名及类型,
ALTER TABLE table_name CHANGE col_old col_new type;

   

注意类型不能省略。

    新建列
    MySQL 中使用 ADD 子句来向数据表中添加列，必须指定类的数据类型。

-- 新建列
ALTER TABLE table_name ADD col_name type [字段位置];

  

    删除列

-- 删除列
ALTER TABLE table_name DROP column;

    

    更新字段值

UPDATE table_name
SET column1=value1,column2=value2,...
WHERE some_column=some_value;

    

5.3 修改行操作

    新建行

-- 新建行
INSERT INTO table_name (column1,column2...)
VALUES (value1,value2,...);

   
    删除行

-- 指定WHERE子句删除特定的行
DELETE RROM table_name [WHERE Clause];


![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)

![%E5%9B%BE%E7%89%87.png](attachment:%E5%9B%BE%E7%89%87.png)
