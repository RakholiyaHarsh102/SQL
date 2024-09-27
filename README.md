// Create Table And Insert Values And Update Valuse //


SQL*Plus: Release 21.0.0.0.0 - Production on Fri Sep 27 22:42:33 2024
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.

Enter user-name: system
Enter password:
Last Successful login time: Fri Sep 27 2024 22:39:55 +05:30

Connected to:
Oracle Database 21c Express Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0

SQL> create table std_new(s_no number(5),s_name char(20),address varchar(30));

Table created.

SQL> insert into stu_new values(&s_no,'&s_name','&address');
Enter value for s_no: 1
Enter value for s_name: Harsh
Enter value for address: Vinay
old   1: insert into stu_new values(&s_no,'&s_name','&address')
new   1: insert into stu_new values(1,'Harsh','Vinay')
insert into stu_new values(1,'Harsh','Vinay')
            *
ERROR at line 1:
ORA-00942: table or view does not exist


SQL> insert into stu_new values(&s_no,'&s_name','&address');
Enter value for s_no: 1
Enter value for s_name: Harsh
Enter value for address: Ahmadabad
old   1: insert into stu_new values(&s_no,'&s_name','&address')
new   1: insert into stu_new values(1,'Harsh','Ahmadabad')
insert into stu_new values(1,'Harsh','Ahmadabad')
            *
ERROR at line 1:
ORA-00942: table or view does not exist


SQL> select * from stu_new;
select * from stu_new
              *
ERROR at line 1:
ORA-00942: table or view does not exist


SQL> insert into std_new values(&s_no,'&s_name','&address');
Enter value for s_no: 1
Enter value for s_name: Harsh
Enter value for address: Ahmadabad
old   1: insert into std_new values(&s_no,'&s_name','&address')
new   1: insert into std_new values(1,'Harsh','Ahmadabad')

1 row created.

SQL> insert into std_new values(&s_no,'&s_name','&address');
Enter value for s_no: 2
Enter value for s_name: Abhi
Enter value for address: Ahmadabad
old   1: insert into std_new values(&s_no,'&s_name','&address')
new   1: insert into std_new values(2,'Abhi','Ahmadabad')

1 row created.

SQL> insert into std_new values(&s_no,'&s_name','&address');
Enter value for s_no: 3
Enter value for s_name: Soni
Enter value for address: Ahmadabad
old   1: insert into std_new values(&s_no,'&s_name','&address')
new   1: insert into std_new values(3,'Soni','Ahmadabad')

1 row created.

SQL> insert into std_new values(&s_no,'&s_name','&address');
Enter value for s_no: 4
Enter value for s_name: Jay
Enter value for address: Surat
old   1: insert into std_new values(&s_no,'&s_name','&address')
new   1: insert into std_new values(4,'Jay','Surat')

1 row created.

SQL> select * from std_new;

      S_NO S_NAME               ADDRESS
---------- -------------------- ------------------------------
         1 Harsh                Ahmadabad
         2 Abhi                 Ahmadabad
         3 Soni                 Ahmadabad
         4 Jay                  Surat

SQL> alter table std_new add(dob date);

Table altered.

SQL> select * from std_new;

      S_NO S_NAME               ADDRESS                        DOB
---------- -------------------- ------------------------------ ---------
         1 Harsh                Ahmadabad
         2 Abhi                 Ahmadabad
         3 Soni                 Ahmadabad
         4 Jay                  Surat

SQL> update std_new set dob='23-sep-2024';

4 rows updated.

SQL> select * from std_new;

      S_NO S_NAME               ADDRESS                        DOB
---------- -------------------- ------------------------------ ---------
         1 Harsh                Ahmadabad                      23-SEP-24
         2 Abhi                 Ahmadabad                      23-SEP-24
         3 Soni                 Ahmadabad                      23-SEP-24
         4 Jay                  Surat                          23-SEP-24

SQL> update std_new set dob = '08-nov-2001' where s_no=1;

1 row updated.

SQL> update std_new set dob = '08-nov-2001' where s_no=1;

1 row updated.

SQL> select * from std_new;

      S_NO S_NAME               ADDRESS                        DOB
---------- -------------------- ------------------------------ ---------
         1 Harsh                Ahmadabad                      08-NOV-01
         2 Abhi                 Ahmadabad                      23-SEP-24
         3 Soni                 Ahmadabad                      23-SEP-24
         4 Jay                  Surat                          23-SEP-24

SQL> update std_new set dob = '25-oct-2004' where s_no=2;

1 row updated.

SQL> select * from std_new;

      S_NO S_NAME               ADDRESS                        DOB
---------- -------------------- ------------------------------ ---------
         1 Harsh                Ahmadabad                      08-NOV-01
         2 Abhi                 Ahmadabad                      25-OCT-04
         3 Soni                 Ahmadabad                      23-SEP-24
         4 Jay                  Surat                          23-SEP-24

SQL> commit;

Commit complete.

SQL>
