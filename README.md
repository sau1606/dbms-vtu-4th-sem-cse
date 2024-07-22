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
