- 使用root权限登陆

      mysql -u root -p

- 添加用户命令

      CREATE USER 'jemo'@'localhost' IDENTIFIED BY '123456';

- 创建数据库

      CREATE DATABASE mydb CHARACTER SET utf8;

- 用户授权命令

      GRANT ALL PRIVILEGES ON mydb.* TO 'jemo'@'localhost';

- import an SQL file using the command line in MySQL.

      mysql -u username -p database_name < file.sql

