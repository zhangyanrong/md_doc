#创建账号、分配权限
CREATE USER 'sky'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON \*.* TO 'sky'@'localhost' WITH GRANT OPTION;
 
CREATE USER 'sky'@'%' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON \*.* TO 'sky'@'%' WITH GRANT OPTION;
 
CREATE USER 'sky'@'localhost' IDENTIFIED BY 'password';
GRANT RELOAD,PROCESS ON \*.* TO 'sky'@'localhost';
#显示账号及权限相关信息
SHOW GRANTS FOR 'sky'@'localhost';
SHOW CREATE USER 'sky'@'localhost';