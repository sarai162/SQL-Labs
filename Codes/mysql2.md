## 📝 Notes (Quick Reference)

- Logged into MySQL using the root account.
- Ran `select database();` — result was **NULL**, meaning no database was currently selected.
- Switched to the existing database **miaowtube** using `use miaowtube;`.
- Verified the switch by running `select database();` — now shows **miaowtube**.
- Created a `users` table with:
  - `user_id` (auto‑increment primary key)
  - `username` (varchar 100, required)
  - `email` (varchar 255, required)
- Created a `videos` table with:
  - `video_id` (auto‑increment primary key)
  - `user_id` (foreign key referencing `users.user_id`, cascades on delete)
  - `title` (varchar 255, required)
  - `link` (varchar 500, required)
  - `upload_date` (date)
- Table creation completed successfully; both tables now exist inside the `miaowtube` database.

``

```console
$bash
bob@mysql-host ~ ➜  sudo mysql -u root -pp@sSw0Rd
mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 10
Server version: 8.0.43-0ubuntu0.24.04.2 (Ubuntu)

Copyright (c) 2000, 2025, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> select database();
+------------+
| database() |
+------------+
| NULL       |
+------------+
1 row in set (0.00 sec)

mysql> use miaowtube;
Database changed
mysql> select database();
+------------+
| database() |
+------------+
| miaowtube  |
+------------+
1 row in set (0.00 sec)

mysql> create table users (
    -> user_id int primary key auto_increment,
    -> username varchar(100) not null,
    -> email varchar(255) not null
    -> );

Query OK, 0 rows affected (0.01 sec)

mysql> create table videos (
    -> video_id int primary key auto_increment,
    -> user_id int,
    -> title varchar (255) not null,
    -> link varchar (500) not null,
    -> upload_date date,
    -> foreign key (user_id) references users(user_id) on delete cascade
    -> );

Query OK, 0 rows affected (0.01 sec)
```
