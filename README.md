# dbms-vtu-4th-sem-cse
dbms-vtu-4th-sem-cse


# 1st program
    
    SQL*Plus: Release 11.2.0.2.0 Production on Mon Jul 22 21:35:32 2024
    
    Copyright (c) 1982, 2014, Oracle.  All rights reserved.
    
    SQL> create table employee(eid number(10), ename char(20), job char(20),manager_no number, sal number(10,2), comm number(10,2));
    SP2-0640: Not connected
    SQL> connect system
    Enter password:
    Connected.
    SQL> create table employee(eid number(10), ename char(20), job char(20),manager_no number, sal number(10,2), comm number(10,2));
    
                                                                   Table created.
    
    SQL> create user sau1606
      2  identified by password;
    
    User created.
    
    SQL> grant connect, resource, DBA
      2  to sau1606;
    
    Grant succeeded.
    
    SQL> insert all
      2  into employee values(1,'sau','manager',null,5000,1000)
      3  into employee values(2,'sham','dev',1,4000,null)
      4  into employee values(3,'jaanu','wife',2,3000,500) select *
    from dual;
    
    3 rows created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             1 sau                  manager
         5000
          1000
    
             2 sham                 dev                           1       4000
    
    
             3 jaanu                wife                          2       3000
           500
    
    
    SQL> insert into employee values (4, 'vivek','brother',3,4000,500);
    
    1 row created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             1 sau                  manager
         5000
          1000
    
             2 sham                 dev                           1       4000
    
    
             3 jaanu                wife                          2       3000
           500
    
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             4 vivek                brother                       3       4000
           500
    
    
    SQL> rollback;
    
    Rollback complete.
    
    SQL> select * from employee;
    
    no rows selected
    
    SQL> alter table employee
      2  ;
    
    *
    ERROR at line 2:
    ORA-02210: no options specified for ALTER TABLE
    
    
    SQL> insert all
      2  into employee values(1,'sau','manager',null,5000,1000)
      3  into employee values(2,'sham','dev',1,4000,null)
      4  into employee values(3,'jaanu','wife',2,3000,500) select * from dual;
    
    3 rows created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             1 sau                  manager                               5000
          1000
    
             2 sham                 dev                           1       4000
    
    
             3 jaanu                wife                          2       3000
           500
    
    
    SQL> insert into employee values (4, 'vivek','brother',3,4000,500);
    
    1 row created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             1 sau                  manager                               5000
          1000
    
             2 sham                 dev                           1       4000
    
    
             3 jaanu                wife                          2       3000
           500
    
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             4 vivek                brother                       3       4000
           500
    
    
    SQL> rollback;
    
    Rollback complete.
    
    SQL> select * from employee;
    
    no rows selected
    
    SQL> into employee values(1,'sau','manager',null,5000,1000);
    SP2-0734: unknown command beginning "into emplo..." - rest of line ignored.
    SQL> insert into employee values(1,'sau','manager',null,5000,1000);
    
    1 row created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             1 sau                  manager                               5000
          1000
    
    
    SQL> insert into employee values(2,'sham','dev',1,4000,null);
    
    1 row created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             1 sau                  manager                               5000
          1000
    
             2 sham                 dev                           1       4000
    
    
    
    SQL> insert into employee values (4, 'vivek','brother',3,4000,500);
    
    1 row created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             1 sau                  manager                               5000
          1000
    
             2 sham                 dev                           1       4000
    
    
             4 vivek                brother                       3       4000
           500
    
    
    SQL> rollback;
    
    Rollback complete.
    
    SQL> select * from employee;
    
    no rows selected
    
    SQL> insert into employee values(2,'sham','dev',1,4000,null);
    
    1 row created.
    
    SQL> savepoint sp1;
    
    Savepoint created.
    
    SQL> insert into employee values (4, 'vivek','brother',3,4000,500);
    
    1 row created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             2 sham                 dev                           1       4000
    
    
             4 vivek                brother                       3       4000
           500
    
    
    SQL> rollback;
    
    Rollback complete.
    
    SQL> select * from employee;
    
    no rows selected
    
    SQL> insert into employee values(2,'sham','dev',1,4000,null);
    
    1 row created.
    
    SQL> savepoint sp1;
    
    Savepoint created.
    
    SQL> insert into employee values (4, 'vivek','brother',3,4000,500);
    
    1 row created.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             2 sham                 dev                           1       4000
    
    
             4 vivek                brother                       3       4000
           500
    
    
    SQL> rollback to sp1;
    
    Rollback complete.
    
    SQL> select * from employee;
    
           EID ENAME                JOB                  MANAGER_NO        SAL
    ---------- -------------------- -------------------- ---------- ----------
          COMM
    ----------
             2 sham                 dev                           1       4000
    
    
    
    SQL> alter table employee
      2  add constraint primary key(eid);
    add constraint primary key(eid)
                              *
    ERROR at line 2:
    ORA-00902: invalid datatype
    
    
    SQL> alter table employee
      2  add constraint pk_employee primary key(eid);
    
    Table altered.
    
    SQL> alter table employee
      2  modify ename varchar(20) not null;
    
    Table altered.
    
    SQL> insert into employee values (null, 'vivek','brother',3,4000,500);
    insert into employee values (null, 'vivek','brother',3,4000,500)
                                 *
    ERROR at line 1:
    ORA-01400: cannot insert NULL into ("SYSTEM"."EMPLOYEE"."EID")
    
    
    SQL> insert into employee values (4, null,'brother',3,4000,500);
    insert into employee values (4, null,'brother',3,4000,500)
                                    *
    ERROR at line 1:
    ORA-01400: cannot insert NULL into ("SYSTEM"."EMPLOYEE"."ENAME

# 2nd program

        SQL*Plus: Release 11.2.0.2.0 Production on Mon Jul 22 22:46:17 2024
        
        Copyright (c) 1982, 2014, Oracle.  All rights reserved.
        
        SQL> connect system
        Enter password:
        Connected.
        SQL> desc employee;
         Name                                      Null?    Type
         ----------------------------------------- -------- ----------------------------
         EID                                       NOT NULL NUMBER(10)
         ENAME                                     NOT NULL VARCHAR2(20)
         JOB                                                CHAR(20)
         MANAGER_NO                                         NUMBER
         SAL                                                NUMBER(10,2)
         COMM                                               NUMBER(10,2)
        
        SQL> select * from employee;
        
               EID ENAME                JOB                  MANAGER_NO        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 2 sham                 dev                           1       4000
        
        
        
        SQL> delete from table employee where eid=2;
        delete from table employee where eid=2
                    *
        ERROR at line 1:
        ORA-00903: invalid table name
        
        
        SQL> delete from employee where eid=2;
        
        1 row deleted.
        
        SQL> select * from employee;
        
        no rows selected
        
        SQL> desc epmloyee;
        ERROR:
        ORA-04043: object epmloyee does not exist
        
        
        SQL> desc employee;
         Name                                      Null?    Type
         ----------------------------------------- -------- ----------------------------
         EID                                       NOT NULL NUMBER(10)
         ENAME                                     NOT NULL VARCHAR2(20)
         JOB                                                CHAR(20)
         MANAGER_NO                                         NUMBER
         SAL                                                NUMBER(10,2)
         COMM                                               NUMBER(10,2)
        
        SQL> alter table employee
          2  drop column comm;
        
        Table altered.
        
        SQL> desc employee;
         Name                                      Null?    Type
         ----------------------------------------- -------- ----------------------------
         EID                                       NOT NULL NUMBER(10)
         ENAME                                     NOT NULL VARCHAR2(20)
         JOB                                                CHAR(20)
         MANAGER_NO                                         NUMBER
         SAL                                                NUMBER(10,2)
        
        SQL> alter table employee
          2  add comm number(10,2);
        
        Table altered.
        
        SQL> desc employee;
         Name                                      Null?    Type
         ----------------------------------------- -------- ----------------------------
         EID                                       NOT NULL NUMBER(10)
         ENAME                                     NOT NULL VARCHAR2(20)
         JOB                                                CHAR(20)
         MANAGER_NO                                         NUMBER
         SAL                                                NUMBER(10,2)
         COMM                                               NUMBER(10,2)
        
        SQL> insert all
          2  into employee values(1,'sau','dev',1,100,5)
          3  into employee values(2,'sham','dev',null,200,6)
          4  into employee values(3,'shamu','dev',2,300,7)
          5  into employee values(4,'shambhavi','dev',null,400,8)
          6  into employee values(5,'sausham','dev',null,400,9)
          7  select * from dual;
        
        5 rows created.
        
        SQL> select * from employee;
        
               EID ENAME                JOB                  MANAGER_NO        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 1 sau                  dev                           1        100
                 5
        
                 2 sham                 dev                                    200
                 6
        
                 3 shamu                dev                           2        300
                 7
        
        
               EID ENAME                JOB                  MANAGER_NO        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 4 shambhavi            dev                                    400
                 8
        
                 5 sausham              dev                                    400
                 9
        
        
        SQL> update employee
          2  set job='analyst'
          3  where eid=4;
        
        1 row updated.
        
        SQL> select * from employee;
        
               EID ENAME                JOB                  MANAGER_NO        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 1 sau                  dev                           1        100
                 5
        
                 2 sham                 dev                                    200
                 6
        
                 3 shamu                dev                           2        300
                 7
        
        
               EID ENAME                JOB                  MANAGER_NO        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 4 shambhavi            analyst                                400
                 8
        
                 5 sausham              dev                                    400
                 9
        
        
        SQL> alter table employee rename column manager_no to mgr;
        
        Table altered.
        
        SQL> select * from employee;
        
               EID ENAME                JOB                         MGR        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 1 sau                  dev                           1        100
                 5
        
                 2 sham                 dev                                    200
                 6
        
                 3 shamu                dev                           2        300
                 7
        
        
               EID ENAME                JOB                         MGR        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 4 shambhavi            analyst                                400
                 8
        
                 5 sausham              dev                                    400
                 9
        
        
        SQL> delete from employee where eid=4;
        
        1 row deleted.
        
        SQL> select * from employee;
        
               EID ENAME                JOB                         MGR        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 1 sau                  dev                           1        100
                 5
        
                 2 sham                 dev                                    200
                 6
        
                 3 shamu                dev                           2        300
                 7
        
        
               EID ENAME                JOB                         MGR        SAL
        ---------- -------------------- -------------------- ---------- ----------
              COMM
        ----------
                 5 sausham              dev                                    400
                 9
        
        
        SQL>

# 5th program
            
    SQL*Plus: Release 11.2.0.2.0 Production on Mon Jul 22 23:09:15 2024
    
    Copyright (c) 1982, 2014, Oracle.  All rights reserved.
    
    SQL> connect system
    Enter password:
    Connected.
    SQL> desc emp;
     Name                                      Null?    Type
     ----------------------------------------- -------- ----------------------------
     EID                                       NOT NULL NUMBER(10)
     ENAME                                              CHAR(20)
     AGE                                       NOT NULL NUMBER(10)
     SALARY                                             NUMBER(10,3)
    
    SQL> select * from emp;
    
    no rows selected
    
    SQL> show tables;
    SP2-0158: unknown SHOW option "tables"
    SQL> show table;
    SP2-0158: unknown SHOW option "table"
    SQL> insert all
      2  into emp values(1,'sau',20,100)
      3  into emp values(2,'sham',21,200)
      4  into emp values(3,'saurav',22,300) select * from dual;
    
    3 rows created.
    
    SQL> select * from emp;
    
           EID ENAME                       AGE     SALARY
    ---------- -------------------- ---------- ----------
             1 sau                          20        100
             2 sham                         21        200
             3 saurav                       22        300
    
    SQL> set serveroutput on;
    SQL> declare
      2  cursor empl is select salary, ename from emp;
      3  salary number(10,3);
      4  ename char(20);
      5  begin
      6  open empl;
      7  if empl%isopen then
      8  dbms_output.put_line('cursor is open');
      9  end if;
     10  loop
     11  fetch empl into salary, ename;
     12  exit when empl%notfound;
     13  dbms_output.put_line(salary||' '||ename);
     14  end loop;
     15  dbms_output.put_line(empl%rowcount||'row has been returned');
     16  close empl;
     17  end;
     18  /
    cursor is open
    100 sau
    200 sham
    300 saurav
    3row has been returned
    
    PL/SQL procedure successfully completed.
    
    SQL>
# 6th program


    SQL*Plus: Release 11.2.0.2.0 Production on Mon Jul 22 23:33:50 2024
    
    Copyright (c) 1982, 2014, Oracle.  All rights reserved.
    
    SQL> connect system
    Enter password:
    Connected.
    SQL> create table o_rollcall(roll int, name varchar(20));
    
    Table created.
    
    SQL> create table n_rollcall(roll int, name varchar(20));
    
    Table created.
    
    SQL> insert all
      2  into n_rollcall values(1,'archana')
      3  into n_rollcall values(2,'bhanu')
      4  into n_rollcall values(3,'naman')
      5  into n_rollcall values(4,'anu')
      6  into o_rollcall values(2,'bhanu')
      7  into o_rollcall values(5,'sanchana')
      8  into o_rollcall values(6,'sanvi')
      9  select * from dual;
    
    7 rows created.
    
    SQL> select * from n_rollcall;
    
          ROLL NAME
    ---------- --------------------
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    SQL> select * from 0_rollcall;
    select * from 0_rollcall
                  *
    ERROR at line 1:
    ORA-00903: invalid table name
    
    
    SQL> select * from o_rollcall;
    
          ROLL NAME
    ---------- --------------------
             2 bhanu
             5 sanchana
             6 sanvi
    
    SQL> set autoprint on;
    SQL> set serveroutput on;
    SQL> set verify off;
    SQL> declare cursor cu1 is select roll,name from n_rolllcall;
      2  cursor cu2 is select roll,name from o_rolllcall;
      3  roll int;
      4  name varchar(20);
      5  roll2 int;
      6  ;
      7  ;
      8  /
    ;
    *
    ERROR at line 6:
    ORA-06550: line 6, column 1:
    PLS-00103: Encountered the symbol ";" when expecting one of the following:
    begin function pragma procedure subtype type <an identifier>
    <a double-quoted delimited-identifier> current cursor delete
    exists prior
    
    
    SQL> declare cursor cu1 is select roll,name from n_rolllcall;
      2  cursor cu2 is select roll from o_rolllcall;
      3  rno1 int;
      4  nm varchar(20);
      5  rno2 int;
      6  begin
      7  open cu1;
      8  open cu2;
      9  loop
     10  fetch cu1 into rno1,nm;
     11  fetch cu2 into rno2;
     12  exit when cu1%notfound=false;
     13  if rno2 <> rno1 then
     14  insert into o_rollcall values(rno1,nm);
     15  end if;
     16  end loop;
     17  close cu1;
     18  close cu2;
     19  end;
     20  /
    declare cursor cu1 is select roll,name from n_rolllcall;
                                                *
    ERROR at line 1:
    ORA-06550: line 1, column 45:
    PL/SQL: ORA-00942: table or view does not exist
    ORA-06550: line 1, column 23:
    PL/SQL: SQL Statement ignored
    ORA-06550: line 2, column 32:
    PL/SQL: ORA-00942: table or view does not exist
    ORA-06550: line 2, column 15:
    PL/SQL: SQL Statement ignored
    
    
    SQL> drop cursor cu1;
    drop cursor cu1
         *
    ERROR at line 1:
    ORA-00950: invalid DROP option
    
    
    SQL> declare cursor cu1 is select roll,name from n_rolllcall;
      2  cursor cu2 is select roll from o_rolllcall;
      3  rno1 int;
      4  nm varchar(20);
      5  rno2 int;
      6  begin
      7  open cu1;
      8  open cu2;
      9  loop
     10  fetch cu1 into rno1,nm;
     11  fetch cu2 into rno2;
     12  exit when cu1%notfound=false;
     13  if rno2 <> rno1 then
     14  insert into o_rollcall values(rno1,nm);
     15  end if;
     16  end loop;
     17  close cu1;
     18  close cu2;
     19  end;
     20  /
    declare cursor cu1 is select roll,name from n_rolllcall;
                                                *
    ERROR at line 1:
    ORA-06550: line 1, column 45:
    PL/SQL: ORA-00942: table or view does not exist
    ORA-06550: line 1, column 23:
    PL/SQL: SQL Statement ignored
    ORA-06550: line 2, column 32:
    PL/SQL: ORA-00942: table or view does not exist
    ORA-06550: line 2, column 15:
    PL/SQL: SQL Statement ignored
    
    
    SQL> select * from n_rollcall;
    
          ROLL NAME
    ---------- --------------------
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    SQL> select * from 0_rollcall;
    select * from 0_rollcall
                  *
    ERROR at line 1:
    ORA-00903: invalid table name
    
    
    SQL> select * from o_rollcall;
    
          ROLL NAME
    ---------- --------------------
             2 bhanu
             5 sanchana
             6 sanvi
    
    SQL> set autoprint on;
    SQL> set serveroutput on;
    SQL> set verify off;
    SQL> declare
      2  cursor cu1 is
      3  select roll,name from n_rollcall;
      4  cursor cu2 is
      5  select roll from o_rollcall;
      6  rno int;
      7  nm varchar(20);
      8  rno1 int;
      9  begin
     10  open cu1;
     11  open cu2;
     12  loop
     13  fetch cu1 into rno,nm;
     14  fetch cu2 into rno1;
     15  exit when cu1%notfound = false;
     16  if rno1<>rno then
     17  insert into o_rollcall values(rno,nm);
     18  end if;
     19  end loop;
     20  close cu1;
     21  close cu2;
     22  end;
     23  /
    
    PL/SQL procedure successfully completed.
    
    SQL> select * from n_rollcall;
    
          ROLL NAME
    ---------- --------------------
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    SQL> select * from o_rollcall;
    
          ROLL NAME
    ---------- --------------------
             2 bhanu
             5 sanchana
             6 sanvi
    
    SQL> drop cursor cu1;
    drop cursor cu1
         *
    ERROR at line 1:
    ORA-00950: invalid DROP option
    
    
    SQL> declare
      2    2  cursor c1 is select roll,name from n;
      3    3  cursor c2 is select roll from o;
      4    4  rno int;
      5    5  nm varchar(20);
      6    6  rno2 int;
      7    7  begin
      8    8  open c1;
      9    9  open c2;
     10   10  loop
     11   11  fetch c1 into rno,nm;
     12   12  fetch c2 into rno2;
     13   13  exit when c1% found=false;
     14   14  if rno2<>rno then
     15   15  insert into o values(rno,nm);
     16   16  end if;
     17   17  end loop;
     18   18  close c2;
     19   19  close c1;
     20   20  end;
     21   21  /
     22
     23
     24
     25
     26
     27
     28  ;
     29  /
      2  cursor c1 is select roll,name from n;
      *
    ERROR at line 2:
    ORA-06550: line 2, column 3:
    PLS-00103: Encountered the symbol "2" when expecting one of the following:
    begin function pragma procedure subtype type <an identifier>
    <a double-quoted delimited-identifier> current cursor delete
    exists prior
    The symbol "2" was ignored.
    ORA-06550: line 3, column 3:
    PLS-00103: Encountered the symbol "3" when expecting one of the following:
    begin function pragma procedure subtype type <an identifier>
    <a double-quoted delimited-identifier> current cursor delete
    exists prior
    The symbol "3" was
    ORA-06550: line 4, column 3:
    PLS-00103: Encountered the symbol "4" when expecting one of the following:
    begin function pragma procedure subtype type <an identifier>
    <a double-quoted delimited-identifier> current cursor delete
    exists prior
    
    
    SQL> declare
      2  cursor cu1 is
      3  select roll,name from n_rollcall;
      4  cursor cu2 is
      5  select roll from o_rollcall;
      6  rno int;
      7  nm varchar(20);
      8  rno1 int;
      9  begin
     10  open cu1;
     11  open cu2;
     12  loop
     13  fetch cu1 into rno,nm;
     14  fetch cu2 into rno1;
     15  exit when cu1%found = false;
     16  if rno1<>rno then
     17  insert into o_rollcall values(rno,nm);
     18  end if;
     19  end loop;
     20  close cu1;
     21  close cu2;
     22  end;
     23  /
    
    PL/SQL procedure successfully completed.
    
    SQL> select * from n_rollcall;
    
          ROLL NAME
    ---------- --------------------
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    SQL> select * from o_rollcall;
    
          ROLL NAME
    ---------- --------------------
             2 bhanu
             5 sanchana
             6 sanvi
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    7 rows selected.
    
    SQL> declare
      2  cursor cu1 is
      3  select roll,name from n_rollcall;
      4  cursor cu2 is
      5  select roll from o_rollcall;
      6  rno int;
      7  nm varchar(20);
      8  rno1 int;
      9  begin
     10  open cu1;
     11  open cu2;
     12  loop
     13  fetch cu1 into rno,nm;
     14  fetch cu2 into rno1;
     15  exit when cu1%found = true;
     16  if rno1<>rno then
     17  insert into o_rollcall values(rno,nm);
     18  end if;
     19  end loop;
     20  close cu1;
     21  close cu2;
     22  end;
     23  /
    
    PL/SQL procedure successfully completed.
    
    SQL> select * from o_rollcall;
    
          ROLL NAME
    ---------- --------------------
             2 bhanu
             5 sanchana
             6 sanvi
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    7 rows selected.
    
    SQL> select * from n_rollcall;
    
          ROLL NAME
    ---------- --------------------
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    SQL> declare
      2  cursor cu1 is
      3  select roll,name from n_rollcall;
      4  cursor cu2 is
      5  select roll,name from o_rollcall;
      6  rno int;
      7  nm varchar(20);
      8  rno1 int;
      9  nm1 varchar(20);
     10  begin
     11  open cu1;
     12  open cu2;
     13  loop
     14  fetch cu1 into rno,nm;
     15  fetch cu2 into rno1,nm1;
     16  exit when cu1%notfound = false;
     17  if nm <> nm1 then
     18  insert into o_rollcall values(rno1,nm1);
     19  end if;
     20  end loop;
     21  close cu1;
     22  close cu2;
     23  end;
     24  /
    
    PL/SQL procedure successfully completed.
    
    SQL> select * from n_rollcall;
    
          ROLL NAME
    ---------- --------------------
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    SQL> select * from o_rollcall;
    
          ROLL NAME
    ---------- --------------------
             2 bhanu
             5 sanchana
             6 sanvi
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    7 rows selected.
    
    SQL> declare
      2  cursor cu1 is
      3  select roll,name from n_rollcall;
      4  cursor cu2 is
      5  select roll from o_rollcall;
      6  rno int;
      7  nm varchar(20);
      8  rno1 int;
      9  begin
     10  open cu1;
     11  open cu2;
     12  loop
     13  fetch cu1 into rno,nm;
     14  fetch cu2 into rno1;
     15  exit when cu1%notfound;
     16  if rno <> rno1 then
     17  insert into o_rollcall values(rno,nm);
     18  end if;
     19  end loop;
     20  close cu1;
     21  close cu2;
     22  end;
     23  /
    
    PL/SQL procedure successfully completed.
    
    SQL> select * from n_rollcall;
    
          ROLL NAME
    ---------- --------------------
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    SQL> select * from o_rollcall;
    
          ROLL NAME
    ---------- --------------------
             2 bhanu
             5 sanchana
             6 sanvi
             1 archana
             2 bhanu
             3 naman
             4 anu
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    11 rows selected.
    
    SQL> declare
      2  cursor cu1 is
      3  select roll,name from n_rollcall;
      4  cursor cu2 is
      5  select roll from o_rollcall;
      6  rno int;
      7  nm varchar(20);
      8  rno1 int;
      9  begin
     10  open cu1;
     11  open cu2;
     12  loop
     13  fetch cu1 into rno,nm;
     14  fetch cu2 into rno1;
     15  exit when cu1%found;
     16  if rno <> rno1 then
     17  insert into o_rollcall values(rno,nm);
     18  end if;
     19  end loop;
     20  close cu1;
     21  close cu2;
     22  end;
     23  /
    
    PL/SQL procedure successfully completed.
    
    SQL> select * from n_rollcall;
    
          ROLL NAME
    ---------- --------------------
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    SQL> select * from o_rollcall;
    
          ROLL NAME
    ---------- --------------------
             2 bhanu
             5 sanchana
             6 sanvi
             1 archana
             2 bhanu
             3 naman
             4 anu
             1 archana
             2 bhanu
             3 naman
             4 anu
    
    11 rows selected.
    
    SQL>
