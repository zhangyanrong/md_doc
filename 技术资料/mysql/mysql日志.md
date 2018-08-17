* 一、通用查询日志
    1. show variables like '%verision%'
        * 显示数据库版本号，存储引擎等信息
    2. show variables like '%general%'
        * 查看当前的通用日志是否开启
    3. set global general_log = on
        * 开启通用日志查询
    4. set global general_log = off
        * 关闭通用日志查询
    5. show variables like '%log_output%'
        * 查看当前慢文件的格式
    6. set global log_output = 'file'
        * 设置通用日志输出为表方式
    7. set global log_output = 'file,table'
        * 设置通用日志输出为表和文件方式

* 二、慢查询日志
    1. show variables like '%query%'
        * 查看当前慢查询日志的开启情况:
        *   1）slow_query_log 的值为ON 为开启慢查询日志，off表示关闭慢查询日志
            2）slow_query_log_file 的值是记录的慢查询日志到文件中（默认为主机 名.log）
            3）long_query_time 指定了慢查询的阈值，即执行语句的时间若超过这个值则为慢查询语句
            4）log_queries_not_using_indexes 如果该值是ON，则会记录所有没有利用索引来进行查询的语句，前提是slow_query_log 的值也是ON
    2. show global status like '%slow%'
        * 查询当前慢查询的语句个数
    1. select * from mysql.slow_log
        * 可以通过查询语句查看慢查询的语句

* 三、错误日志
    1. show variables like '%log_err%
        * 查看错误日志的详细信息

* 四、二进制日志
    1. reset master
        * 删除所有二进制文件
    2. purge master logs
        * 删除部分二进制文件
    3. show variables like '%log_bin%'
        * 查看是否启用二进制日志
    4. show variables like '%binlog%'
        * 查看所有的二进制参数
    5. show variables like '%datadir%'
        * 查看文件的位置

        
    
    
##### 修改配置文件
* 一、通用查询my.cnf配置
    1. general_log=ON
    2. general_log_file=/data/mysql/query.log