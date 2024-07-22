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
