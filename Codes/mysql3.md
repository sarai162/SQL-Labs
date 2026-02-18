## 📝 Notes (Quick Reference)

- Logged into MySQL using the root account.
- Selected the existing database **miaowtube** using `use miaowtube;`.
- Inserted two users (`fluffy` and `paws`) into the `users` table.
- Inserted three videos into the `videos` table, linked to users by `user_id`.
- Verified inserts by selecting all rows from `videos` and `users`.
- Updated the title of the video with `video_id = 1` to **"Flufferson on Skateboard"**.
- Confirmed the update by re‑querying the `videos` table.
- Deleted the video with `video_id = 3` from the `videos` table.
- Verified deletion — only two videos remain in the table.
- All operations (INSERT, UPDATE, DELETE, SELECT) executed successfully.

```console
$bash

bob@mysql-host ~ ➜  sudo mysql -u root -pp@sSw0Rd
mysql: [Warning] Using a password on the command line interface can be insecure.
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 9
Server version: 8.0.43-0ubuntu0.24.04.2 (Ubuntu)

Copyright (c) 2000, 2025, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> use miaowtube;
Database changed

mysql> insert into users (username, email)
    -> values
    -> ('fluffy', 'fluffy@email.com'),
    -> ('paws', 'paws@email.com');
Query OK, 2 rows affected (0.00 sec)
Records: 2  Duplicates: 0  Warnings: 0

mysql> insert into videos (user_id, title, link, upload_date)
    -> values
    -> (1, 'Cat Skateboard', 'www.miaowtube/watch1', '2025-05-25'),
    -> (2, 'Epic Cat', 'www.miaowtube/watch2', '2025-05-27'),
    -> (1, 'Cat vs Curtain', 'www.miaowtube/watch3', '2025-05-29');
Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> select * from videos;
+----------+---------+----------------+----------------------+-------------+
| video_id | user_id | title          | link                 | upload_date |
+----------+---------+----------------+----------------------+-------------+
|        1 |       1 | Cat Skateboard | www.miaowtube/watch1 | 2025-05-25  |
|        2 |       2 | Epic Cat       | www.miaowtube/watch2 | 2025-05-27  |
|        3 |       1 | Cat vs Curtain | www.miaowtube/watch3 | 2025-05-29  |
+----------+---------+----------------+----------------------+-------------+
3 rows in set (0.00 sec)

mysql> select * from users;
+---------+----------+------------------+
| user_id | username | email            |
+---------+----------+------------------+
|       1 | fluffy   | fluffy@email.com |
|       2 | paws     | paws@email.com   |
+---------+----------+------------------+
2 rows in set (0.00 sec)

mysql> UPDATE videos
    -> SET title = 'Flufferson on Skateboard'
    -> WHERE video_id = 1;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select * from videos;
+----------+---------+--------------------------+----------------------+-------------+
| video_id | user_id | title                    | link                 | upload_date |
+----------+---------+--------------------------+----------------------+-------------+
|        1 |       1 | Flufferson on Skateboard | www.miaowtube/watch1 | 2025-05-25  |
|        2 |       2 | Epic Cat                 | www.miaowtube/watch2 | 2025-05-27  |
|        3 |       1 | Cat vs Curtain           | www.miaowtube/watch3 | 2025-05-29  |
+----------+---------+--------------------------+----------------------+-------------+
3 rows in set (0.00 sec)

mysql> DELETE FROM videos
    -> WHERE video_id = 3;
Query OK, 1 row affected (0.00 sec)

mysql> select * from videos;
+----------+---------+--------------------------+----------------------+-------------+
| video_id | user_id | title                    | link                 | upload_date |
+----------+---------+--------------------------+----------------------+-------------+
|        1 |       1 | Flufferson on Skateboard | www.miaowtube/watch1 | 2025-05-25  |
|        2 |       2 | Epic Cat                 | www.miaowtube/watch2 | 2025-05-27  |
+----------+---------+--------------------------+----------------------+-------------+
2 rows in set (0.00 sec)

mysql>

```
