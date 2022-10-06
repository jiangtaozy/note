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

- 打印

      --第一个存储过程：打印Hello World
      /*
           调用存储过程2种方式：
           1、exec sayhelloworld();
           2、begin
                  sayhelloworld();
                  sayhelloworld();
              end;
              /
      */
      create or replace procedure sayhelloworld  --假设这个存储过程存在就replace替换否则create创建，这里创建无參数的存储过程
      as --不可省略

      begin
         dbms_output.put_line('Hello World');--注意不是双引號而是单引號，否则调用存储过程会报错
      end;

      exec sayhelloworld();
      begin
        sayhelloworld();
      end;

      // 有时，存储过程执行成功后，未看到输出的结果，原因可能是没有打开输出开关，执行一下下面语句即可
      set serveroutput on;

- Oracle保存带&的数据

      在SQL*Plus中默认的"&"表示替代变量，也就是说，只要在命令中出现该符号，SQL*Plus就会要你输入替代值。这就意味着你无法将一个含有该符号的字符串输入数据库或赋给变量，如字符串“SQL&Plus”系统会理解为以“SQL”打头的字符串，它会提示你输入替代变量Plus的值，如果你输入ABC，则最终字符串转化为“SQLABC”。
      set define off 则关闭该功能，"&"将作为普通字符，如上例，最终字符就为“SQL&Plus”

- Oracle 导入sql文件

      在工作表中运行
      start C:\Users\jemo\Downloads\sqldeveloper-20.4.1.407.0006-x64\sqldeveloper\sqldeveloper\bin\sql

- 显示日期时分秒

      select to_char(col9,'YYYY-MM-DD HH24:MI:SS') from ele_5;

- windows中nodejs使用oracledb连接oracle

      下载 oracle instantclient:
      instantclient-basic-windows.x64-12.1.0.1.0.zip 和 instantclient-sdk-windows.x64-12.1.0.1.0.zip;
      下载完成后把它们解压到 D:\db\oracle\instantclient_12_2 文件夹中(可自定义目录)
      系统环境变量新增以下3个：
        OCI_LIB_DIR=D:\db\oracle\instantclient_12_2\sdk\lib\msvc
        OCI_INC_DIR=D:\db\oracle\instantclient_12_2\sdk\include
        OCI_VERSION=12
      path环境变量 里加上 以下两个，注意先后顺序
        D:\db\oracle\instantclient_12_2\vc14
        D:\db\oracle\instantclient_12_2



        OCI_LIB_DIR=C:\Users\jemo\src\oracle\instantclient_19_11\sdk\lib\msvc
        OCI_INC_DIR=C:\Users\jemo\src\oracle\instantclient_19_11\sdk\include
        OCI_VERSION=19

        C:\Users\jemo\src\oracle\instantclient_19_11\vc14
        C:\Users\jemo\src\oracle\instantclient_19_11

- linux 中nodejs使用oracledb连接oracle

      1. 下载 oracle instantclient:
      oracle-instantclient-basic-21.1.0.0.0-1.x86_64.rpm
      oracle-instantclient-devel-21.1.0.0.0-1.x86_64.rpm
      2. 安装
      rpm -Uvh ./*.rpm --nodeps --force
      3. 设置PATH
      vi .bashrc
      export PATH=$PATH:/usr/lib/oracle/21/client64/bin

- 日期比较

      select * from crm_spc_station_9281_1 where insert_time < to_date('20210709', 'yyyyMMdd');

- 查看所有表

      select * from all_tab_comments where owner = 'ZJTTPOWER' order by table_name;

- 查询用户下所有的表

      select * from all_tab_comments where owner = 'ZJTTPOWER' order by table_name;

- 删除表

      drop table  表名;

- 删除数据

      DELETE FROM contacts

- windows 安装 sqlldr

      https://www.oracle.com/database/technologies/instant-client/winx64-64-downloads.html
      下载 instantclient-tools-windows.x64-19.11.0.0.0dbru.zip
      解压到C:\app\jemo\instantclient_19_11
      设置环境变量

- linux 安装 sqlldr
      下载 instantclient-tools rpm
      rpm -Uvh *.rpm --nodeps --force
      设置环境变量
      export PATH=$PATH:/usr/lib/oracle/21/client64/bin

- 创建索引

      create index IDX_SIGNLID on TW_PW_0445104001_202106 (SIGNLID)
      create index IDX_SIGNLID_FSUID on TW_PW_0445104001_202106 (SIGNLID, FSUID);

- 删除索引

      drop index 索引名;

- 查看索引

      select * from user_indexes;

- 分裂分区

      ALTER TABLE ZJTTPOWER.TW_PW_REPAIR_202108
      SPLIT PARTITION PERFDATA_REPAIR_PARTITION_MAX
      AT (TO_DATE('2021-08-11 00:00:00','YYYY-MM-DD HH24:MI:SS'))
      INTO (PARTITION PERFDATA_REPAIR_PARTITION_20210810, PARTITION PERFDATA_REPAIR_PARTITION_MAX)

- 增加分区

      ALTER TABLE ZJTTPOWER.TW_PW_REPAIR_202108
      ADD PARTITION PERFDATA_REPAIR_PARTITION_20210809
      VALUES LESS THAN (TO_DATE('2021-08-10 00:00:00','YYYY-MM-DD HH24:MI:SS'))

- 删除分区

      alter table TW_PW_REPAIR_202108  DROP partition PERFDATA_REPAIR_PARTITION_20180318; 该分区以及分区的数据都会被删掉;


- 删除分区数据

      alter table tw_pw_repair_202108 TRUNCATE PARTITION PERFDATA_REPAIR_PARTITION_20210812;

- 分区查询

      select * from tw_pw_repair_202110
      partition(perfdata_repair_partition_20211024)

- 查看当前执行语句

      SELECT b.sid oracleID,
          b.username Oracle用户,
          b.serial#,
          spid 操作系统ID,
          paddr,
          sql_text 正在执行的SQL,
          b.machine 计算机名
      FROM v$process a, v$session b, v$sqlarea c
      WHERE a.addr = b.paddr
          AND b.sql_hash_value = c.hash_value;

      SELECT A.serial#,OSUSER 电脑登录身份,
          PROGRAM 发起请求的程序,
          USERNAME 登录系统的用户名,
          SCHEMANAME,
          B.Cpu_Time 花费cpu的时间,
          STATUS,
          B.SQL_TEXT 执行的sql
      FROM V$SESSION A
      LEFT JOIN V$SQL B ON A.SQL_ADDRESS = B.ADDRESS
          AND A.SQL_HASH_VALUE = B.HASH_VALUE
      ORDER BY b.cpu_time DESC

- 终止语句

      alter system kill session '930,48986';
      注： '930,48986'是：sid和serial#字段进行拼接的

- 查询表存储大小

      select sum(bytes)/(1024*1024*1024) as "size(G)" from user_segments where segment_name = 'TW_PW_REPAIR_202108';

- 插入

      insert into tw_pw_repair_status values('20210823', 1, to_date('20210824', 'yyyyMMdd'));

      INSERT INTO table
      (column1, column2, ... column_n )
      VALUES
      (expression1, expression2, ... expression_n );

      insert into maintain_bill
      (site_name, site_num)
      values
      ('测试', '12345678');

      insert into
          pms_site_audit
      select
          project.order_num,
          project.project_num,
          project.project_name,
          project.site_num project_site_num,
          contract.site_num contract_site_num,
          contract.contract_num,
          contract.contract_name,
          nvl2(contract.site_num, nvl2(project.site_num, 1, 0), 0) is_same,
          project.city,
          project.area
      from
          communication_tower_project project
      full outer join
          property_contract contract on project.site_num = contract.site_num
      where
          (project.project_status = '验收' or project.project_status is null)
          and (contract.contract_attribute = '新签' or contract.contract_attribute is null)
          and (contract.contract_status = '有效' or contract.contract_status is null)

      insert into tbl_temp2 (fld_id)
        select tbl_temp1.fld_order_id
        from tbl_temp1 where tbl_temp1.fld_order_id > 100;

- 修改

      UPDATE table
      SET column1 = expression1,
          column2 = expression2,
          ...
          column_n = expression_n
      [WHERE conditions];


- TRUNCATE 删除数据

      TRUNCATE TABLE [schema_name.]table_name

- 修改字段类型

      alter table tb modify (name nvarchar2(20));

- 增加字段

      alter table test1 add (name varchar2(30));

- 删除字段

      alter table table_name drop column column_name;

- 日期显示

      select to_char(timestamp,'DD-MM-YYYY HH24:MI:SS') from tw_pw_repair_202108;
      select to_char(timestamp,'YYYY-MM-DD HH24:MI:SS') from tw_pw_repair_202108;

- 创建视图

      CREATE OR REPLACE VIEW tw_pw_repair_view AS
      SELECT * FROM tw_pw_repair_202104
      UNION ALL
      SELECT * FROM tw_pw_repair_202105
      UNION ALL
      SELECT * FROM tw_pw_repair_202106
      UNION ALL
      SELECT * FROM tw_pw_repair_202107
      UNION ALL
      SELECT * FROM tw_pw_repair_202108
      UNION ALL
      SELECT * FROM tw_pw_repair_202109

- group by

      SELECT MAX(city_name), region
      FROM Cities, Countries
      WHERE Cities.country_ISO_code = Countries.country_ISO_code
      GROUP BY region

- 多表查询

      select total.equipmentid, total.total, repair.repair, origin.origin from
      (select equipmentid, count(*) as total from tw_pw_repair_202109 partition (perfdata_repair_partition_20210901) group by equipmentid) total,
      (select equipmentid, count(*) as repair from tw_pw_repair_202109 partition (perfdata_repair_partition_20210901) where id = '1' group by equipmentid) repair,
      (select equipmentid, count(*) as origin from tw_pw_repair_202109 partition (perfdata_repair_partition_20210901) where id <> '1' group by equipmentid) origin
      where total.equipmentid = repair.equipmentid and total.equipmentid = origin.equipmentid

- distinct唯一值查询

      select distinct "FSUID" "fsuId", "EQUIPMENTID" "equipmentId", "SIGNLID" "signalId"
      from "ZJTTPOWER"."TW_PW_PERFDATA_YC_${yearMonthDay}"


- Oracle Distinct on one column
      I have the table structure in following way:

      ITEM  LOC  STATUS  QTY
      001   RS1    A     10
      001   JS1    I     20
      110   RS1    A     4
      I want to retrieve the results based on distinct ITEM only, regardless of that the values come with that

      So result should be

      ITEM   LOC   STATUS   QTY
      001    JS1     A      10
      110    RS1     A       4
      How to do that ?


      One method is aggregation, if the values don't need to come from the same row:

      select item, max(loc) as loc, . . .
      from t
      group by item;
      If you want all the values from the same row, use row_number():

      select t.*
      from (select t.*, row_number() over (partition by item order by item) as seqnum
            from t
           ) t
      where seqnum = 1;


- case, nvl2 check null, left join

      select
          expire_contract.contract_num,
          max(case when instr(expire_contract.contract_num, 'ZM') > 0 then 1 else 0 end) is_transfer_name,  -- 是否转名
          max(renew_contract.contract_num) renew_contract_num,
          max(nvl2(renew_contract.contract_num, 1, 0)) is_renew, -- 是否续签
          max(expire_contract.contract_status) contract_status,
          max(case when expire_contract.contract_status = '已终止' then 1 else 0 end) is_end, -- 是否终止
          max(expire_contract.contract_end_date) contract_end_date,
          max(case when instr(expire_contract.contract_num, 'ZM') > 0 or renew_contract.contract_num is not null or expire_contract.contract_status = '已终止' then 1 else 0 end) is_same
      from
          property_contract expire_contract
      left outer join
          property_contract renew_contract
          on expire_contract.contract_num = renew_contract.renew_contract_num
      where
          expire_contract.contract_end_date < sysdate
      group by expire_contract.contract_num


- limit

      SELECT * FROM
      (
          SELECT
              title
          FROM
              post
          ORDER BY
              id DESC
      )
      WHERE ROWNUM <= 50


- 查看单表存储大小

      select sum(bytes)/(1024*1024*1024) as "size(G)"
      from user_segments
      where segment_name=upper('tw_pw_perfdata_yc_20211201');

- decode
      This example decodes the value warehouse_id.
      If warehouse_id is 1, then the function returns 'Southlake';
      if warehouse_id is 2, then it returns 'San Francisco'; and so forth.
      If warehouse_id is not 1, 2, 3, or 4, then the function returns 'Non domestic'.

      SELECT product_id,
      DECODE (warehouse_id, 1, 'Southlake',
                            2, 'San Francisco',
                            3, 'New Jersey',
                            4, 'Seattle',
                               'Non domestic')
      "Location of inventory" FROM inventories
      WHERE product_id < 1775;

- 字段重命名小写

      select distinct city  "city" from maintain_bill_year_report;

- group by 条件

      SELECT  column, group_function(column)
      FROM  table
      [WHERE  condition]
      [GROUP BY group_by_expression]
      [ORDER BY column];

      SELECT department_id, AVG(salary)
      FROM employees
      GROUP BY department_id
      HAVING AVG(salary) > 8000;

- 获取系统时间

      select sysdate from dual; --获得当前系统时间
      select extract(year from sysdate) from dual; --获得系统当前年
      select extract(month from sysdate) from dual; --获得系统当前月
      select extract(day from sysdate) from dual; --获得系统当前日

- 更新字段

      -- 更新年份
      update rent_payment_query_audit set pay_time_year = (extract(year from pay_time));
      -- 更新月份
      update rent_payment_query_audit set pay_time_month = (extract(month from pay_time));

      -- 更新年份月份
      update rent_payment_query_audit
      set pay_time_year = (extract(year from pay_time)),
          pay_time_month = (extract(month from pay_time))

      -- 更新是否大于
      update maintain_bill
      set is_large_amount = case when maintain_bill_amount_value > 3000 then 1 else 0 end

      -- 更新是否多次
      update maintain_bill
      set is_maintain_times = 1
      where site_num in (
          select site_num from maintain_bill
          group by site_num, actual_maintain_date_year
          having count(*) > 2
      )

      -- 更新是否为空
      update maintain_bill
      set is_fill_complete = (
          case when city is null
          or county is null
          or LENGTH(TRIM(TRANSLATE(maintain_bill_amount, ' +-.0123456789', ' '))) > 0
          then 0 else 1 end
      )

      -- 更新字符串转数值
      update maintain_bill
      set maintain_bill_amount_value =
          case when validate_conversion(replace(maintain_bill_amount, ' ', '') as number) > 0
          then nvl(cast(replace(maintain_bill_amount, ' ', '') as number), 0)
          else 0 end

      UPDATE EMPLOYEE
        SET JOB=NULL, SALARY=0, BONUS=0, COMM=0
        WHERE WORKDEPT = 'E21' AND JOB <> 'MANAGER'

      -- 更新是否大于3000

      update MAINTAIN_BILL set IS_LARGE_AMOUNT = CASE WHEN MAINTAIN_BILL_AMOUNT_VALUE > 3000 THEN 1 ELSE 0 END;

      -- 从另一表更新字段
      UPDATE tableA
      SET tableA.someColumn = (SELECT tableB.otherColumn
      FROM tableB
      WHERE tableA.joiningColumn = tableB.joiningColumn);

      -- 从另一表更新多个字段
      update contract_renew c
      set (
       c.business_confirmation_num,
       c.crm_bill_type,
       c.crm_bill_needs_num,
       c.crm_bill_month
      ) = (
      select
       b.business_confirmation_num,
       '微站',
       b.needs_confirmation_num,
       b.bill_month
      from
       micro_site_service_end_bill b
      where
       c.site_num = b.site_num
       and b.bill_month = '${lastMonthStr}'
       and rownum < 2
      )

      -- 从多个表更新
      merge into contract_renew c
      using
      (
        select
          f.site_num,
          case when instr(n.no_need_renew_reason, '拆') > 0 or instr(n.no_need_renew_reason, '免费') > 0 or instr(n.remarks, '拆') > 0 or instr(n.remarks, '免费') > 0 then 0 else 1 end is_need_renew_audit,
          row_number() over (partition by f.site_num order by f.registration_status asc, n.remarks asc) rnk
        from
          fsu_monitor f
        left outer join
        (
        select
          site_num,
          no_need_renew_reason,
          remarks,
          row_number() over (partition by site_num order by no_need_renew_reason asc, remarks asc) rnk
        from
          no_need_renew_contract
        ) n
        on (f.site_num = n.site_num and n.rnk = 1)
        where
          f.registration_status = '在线'
      ) fn
      on (c.site_num = fn.site_num and fn.rnk = 1)
      when matched then update
        set c.is_need_renew_audit = fn.is_need_renew_audit
      where
        c.is_need_renew = '否'
        and c.contract_end_date < sysdate
        and c.is_renewed is null


- 默认插入时间

      -- 系统日期
      sys_date DATE DEFAULT sysdate

- 当天数据

      crawler_time > trunc(sysdate)

- group by 第一条

      select
        ${reduceTimes},
        min(longitude) keep(dense_rank first order by geohash) longitude,
        min(latitude) keep(dense_rank first order by geohash) latitude,
        min(geohash) geohash,
        floor(avg(basic_annual_rent))
      from (
        select *
        from contract_geohash
        where contract_status = '有效'
          and longitude > 0
          and latitude > 0
        order by geohash
      )
      group by floor((rownum - 1) / ${reduceTimes})

- 判断是否同月

      select case when trunc(sysdate, 'mm') = trunc(to_date('2022-07-02', 'YYYY-MM-DD'), 'mm') then 1 else 0 end from dual;

- 去重

      delete from door_control_event d2
      where d2.rowid in (
        select d1.rid from (
          select d.rowid rid, row_number() over(partition by d."id" order by 1) rn
          from door_control_event d
        ) d1
        where d1.rn > 1
      );

- merge

      MERGE [hint] INTO [schema .] table [t_alias] USING [schema .]
      { table | view | subquery } [t_alias] ON ( condition )
      WHEN MATCHED THEN merge_update_clause
      WHEN NOT MATCHED THEN merge_insert_clause;

      MERGE INTO T2
      USING T1
      ON (T1.NAME=T2.NAME)
      WHEN MATCHED THEN
      UPDATE
      SET T2.MONEY=T1.MONEY+T2.MONEY
      WHEN NOT MATCHED THEN
      INSERT
      VALUES (T1.NAME,T1.MONEY);

      merge into bonuses d
      using (select employee_id, salary, department_id from employees
      where department_id = 80) s
      on (d.employee_id = s.employee_id)
      when matched then update set d.bonus = d.bonus + s.salary*.01
      when not matched then insert (d.employee_id, d.bonus)
      values (s.employee_id, s.salary*0.01);
