- Sqlplus connect to remote database

      sqlplus "user/pass@(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(Host=hostname.network)(Port=1521))(CONNECT_DATA=(SID=remote_SID)))"

- Show databases

      SELECT USERNAME FROM ALL_USERS;

- Show tables

      SELECT table_name FROM user_tables;

- Sqlformat

      SET SQLFORMAT JSON
      SELECT * FROM emp;
