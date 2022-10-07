- 使用root权限登陆

      mysql -u root -p

- 远程登录

      mysql -h 166.78.144.191 -u username -ppassword database_name

      In this case:
      -h specifies a host. Instead of using localhost, the IP 166.78.144.191 is used.
      -u specifies a use name, in this case username
      -p specifies a password, password. Note that for passwords, unlike the other parameters, there cannot be a space between the the option (-p) and the value (password). It is also not secure to use a password in this way, as other users on the system can see it as part of the command that has been run. If you include the -p option, but leave out the password, you will be prompted for it, which is more secure.
      The database name is provided as the first argument after all the options, in this case database_name.

- 添加用户命令

      CREATE USER 'jemo'@'localhost' IDENTIFIED BY '123456';
      CREATE USER 'jemo'@'%' IDENTIFIED BY '123456';

- 创建数据库

      CREATE DATABASE mydb CHARACTER SET utf8mb4;

- 用户授权命令

      GRANT ALL PRIVILEGES ON mydb.* TO 'jemo'@'localhost';
      GRANT ALL PRIVILEGES ON mydb.* TO 'jemo'@'%';

      CREATE USER 'user' IDENTIFIED BY 'pwd';
      CREATE DATABASE IF NOT EXISTS db;
      grant all privileges on db.* to user;

      CREATE DATABASE IF NOT EXISTS mujx;
      grant all privileges on mujx.* to mjx;

- import an SQL file using the command line in MySQL.

      mysql -h 192.168.31.3 -u username -p database_name < file.sql

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

    UPDATE test set test_char = replace(test_char, 'Scott', 'Sidhu');

- Not equal to

    delete from table where id not in ( 2 );
    or
    delete from table where id <> 2;

- Drop unique

    SHOW CREATE TABLE table_name
    ALTER TABLE `table_name` DROP INDEX key_name;

- Change primary column

    alter table user modify `primary_id` int, drop primary key, add primary key (id);
    alter table user drop column primary_id;
    alter table user add primary key (id);
    alter table user modify column id int auto_increment;

- Select where column is not empty

    select from users where phone <> '';
    select from users where phone IS NOT NULL;

- Enable Remote Access

      vim /etc/mysql/my.cnf
      Comment out following lines.
      #bind-address           = 127.0.0.1
      #skip-networking

- Copy database

      mysqldump -u chslab -p haotu > haotu.sql
      mysql -u chslab -p haotu < haotu.sql

      mysqldump -u chslab -p haotu user > haotu.user.sql

- Insert

      INSERT INTO table_name (column1, column2, column3, ...)
      VALUES (value1, value2, value3, ...);

- Insert now

      INSERT INTO servers (column1) VALUES(NOW());

- Order

      SELECT expressions
      FROM tables
      [WHERE conditions]
      ORDER BY expression [ ASC | DESC ];

- Show databases

      show databases;

- Update

      UPDATE table_name
      SET column1=value, column2=value2,...
      WHERE some_column=some_value

- Show processlist

      show processlist;

- 创建索引

      ALTER table tableName ADD INDEX indexName(columnName)

- 创建多列索引

      ALTER TABLE people ADD INDEX fname_lname_age (firstname,lastname,age);

- show profiles查询SQL执行时间

      show profiles用来查询SQL执行时间，它是mysql 5.0.37之后添加的功能。
      1.查看数据库版本信息，登录数据库时显示的信息中会出现数据库版本信息：
      2.查看show profiles功能是否开启：
          show variables like "%pro%";
      3.开启show profiles功能：
          set profiling=1;
      4.查看每条执行过的SQL语句的执行时间：
          show profiles;
      5.查看一条SQL语句的详细执行时间：
          show profile for query 1;

- 查看慢查询

      show processlist;

- MySQL分组查询并统计大于某值的sql语句

      select count(id) as count, orderSn from pddAfterSalesOrder group by orderSn having count > 1;

- 清屏

      system clear

- Change Column Type

      ALTER TABLE table_name MODIFY column_name datatype;

- add column 增加列

      ALTER TABLE table
      ADD [COLUMN] column_name_1 column_1_definition [FIRST|AFTER existing_column],
      ADD [COLUMN] column_name_2 column_2_definition [FIRST|AFTER existing_column],

- where in

      SELECT book_name,dt_of_pub,no_page
      FROM book_mast
      WHERE no_page IN (300,400,500);


- mysql 备份与恢复

      #备份
      mysqldump -uuser -ppwd db > db.dump

      #上传
      scp /home/db.dump root@ip:/root/mujx.dump

      #恢复
      mysql -uuser -ppwd db < db.dump

      #登录查看
      mysql -uuser -ppwd db

- 开启外网访问

      vim /etc/mysql/my.cnf
      注释掉 bind-address = 127.0.0.1
      重启mariadb systemctl restart mariadb.service

- 查看字符集

      查看当前系统默认的字符集设置
      SHOW VARIABLES WHERE Variable_name LIKE 'character\_set\_%' OR Variable_name LIKE 'collation%';
      查看database的字符编码
      show create database polarsnow;
      查看table的字符编码
      show create table ps;
      查看column的字符编码
      show full columns from ps;

- 颜文字bug，改为utf8mb4

      CREATE DATABASE mydb CHARACTER SET utf8mb4;
      vi /etc/mysql/mariadb.cnf

          [client]
          # Default is Latin1, if you need UTF-8 set this (also in server section)
          default-character-set = utf8mb4

          [mysqld]
          # * Character sets
          # Default is Latin1, if you need UTF-8 set all this (also in client section)
          character-set-server  = utf8mb4
          collation-server      =  utf8mb4_unicode_ci
          character_set_server   =  utf8mb4
          collation_server       = utf8mb4_unicode_ci

      systemctl restart mariadb.service

      node knex connections: {
          host: 'r',
          user: 'XX',
          password: 'XXX',
          database: 'XX',
          charset: 'utf8mb4', // 指定编码
      }

- 添加列

      ALTER TABLE vendors
      ADD COLUMN vendor_group INT NOT NULL;
