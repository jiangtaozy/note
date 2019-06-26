- Sqlplus connect to remote database

      sqlplus "user/pass@(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(Host=hostname.network)(Port=1521))(CONNECT_DATA=(SID=remote_SID)))"

- Show databases

      SELECT USERNAME FROM ALL_USERS;

- Show tables

      SELECT table_name FROM user_tables;

- Sqlformat

      SET SQLFORMAT JSON
      SELECT * FROM emp;

- Cannot locate a 64-bit Oracle Client library: libnsl.so.1

      sudo dnf install libnsl

- Execute the .sql file as a script in the SQL Developer

      @C:\Users\13213\Downloads\ASSETPHOTO_ATTACHMENT.sql;
