### 错误：Client does not support authentication protocol requested by server; consider upgrading MySQL client

1. 先登录： mysql -u root -p
2. 接着输入你的密码
3. 解决:更改加密方式 [1.caching_sha2_password(mysql8采用的加密方式)   2.mysql_native_password]
    1. 修改加密方式
        * ALTER USER 'root'@'%' IDENTIFIED WITH (caching_sha2_password或mysql_native_password) BY '你的密码';
        * ALTER USER 'root'@'localhost' IDENTIFIED WITH (caching_sha2_password或mysql_native_password) BY '你的密码';
    2. 查看是否修改成功
        *  select host, user, authentication_string, plugin from mysql.user where User='root';  
    3. 刷新
        *  FLUSH PRIVILEGES;
