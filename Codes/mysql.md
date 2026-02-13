# 📝 Notes (Quick Reference)

- Logged into MySQL using the root account  
- Created a database named **miaowtube**  
- Verified that the database appears in `show databases`  
- Switched to the database with `use miaowtube`  
- Confirmed active database using `select database()`  
- No tables created yet — this is just database initialization  

```console
$bash
bob@mysql-host ~ ➜  sudo mysql -u root -pp@sSw0Rd
mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.43-0ubuntu0.24.04.2 (Ubuntu)

Copyright (c) 2000, 2025, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> create database miaowtube;
Query OK, 1 row affected (0.00 sec)

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| miaowtube          |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> use miaowtube;
Database changed
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| miaowtube          |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> select database();
+------------+
| database() |
+------------+
| miaowtube  |
+------------+

1 row in set (0.00 sec)

mysql>

```
