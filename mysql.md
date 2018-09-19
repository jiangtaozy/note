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

- SQL DELETE Statement

      DELETE FROM table_name WHERE condition;

- Delete all records from a table

      truncate table table_name

- Clone an SQL Record

      CREATE TEMPORARY TABLE chan2 ENGINE=MEMORY SELECT * FROM channel WHERE chanid=21051;
      UPDATE chan2 SET chanid=21109; // Change the unique key
      // Update anything else that needs to be updated.
      INSERT INTO channel SELECT * FROM chan2;
      DROP TABLE chan2;

- Remove Null Records

      DELETE FROM myTable WHERE myColumn IS NULL

- Show procedure

      show procedure status\G;
      show create procedure proc_name\G;

- Count

    select count(*) from myTable;

- replace function

    REPLACE(str, find_string, replace_with)

    SELECT pub_city,country,
    REPLACE(country,'K','SA') 
    FROM publisher 
    WHERE country='UK';
