# Lesson 5  
## name: Подсытник Дмитрий Александрович  
### Result:

Протестироват падение производителности при исползовании pgbouncer в разных режимах: statement, transaction, session
## Session
```
/usr/lib/postgresql/17/bin/pgbench -c 8 -j 4 -T 10 -f /workload.sql -n -U postgres -p 6432 -h 127.0.0.1 thai
Password: 
pgbench (17.4 (Debian 17.4-1.pgdg120+2))
transaction type: /workload.sql
scaling factor: 1
query mode: simple
number of clients: 8
number of threads: 4
maximum number of tries: 1
duration: 10 s
number of transactions actually processed: 348467
number of failed transactions: 0 (0.000%)
latency average = 0.229 ms
initial connection time = 34.238 ms
tps = 34962.439660 (without initial connection time)
```
## Transaction
```
/usr/lib/postgresql/17/bin/pgbench -c 8 -j 4 -T 10 -f /workload.sql -n -U postgres -p 6432 -h 127.0.0.1 thai
Password: 
pgbench (17.4 (Debian 17.4-1.pgdg120+2))
transaction type: /workload.sql
scaling factor: 1
query mode: simple
number of clients: 8
number of threads: 4
maximum number of tries: 1
duration: 10 s
number of transactions actually processed: 349589
number of failed transactions: 0 (0.000%)
latency average = 0.228 ms
initial connection time = 34.232 ms
tps = 35075.730242 (without initial connection time)
```
## Statement
```
/usr/lib/postgresql/17/bin/pgbench -c 8 -j 4 -T 10 -f /workload.sql -n -U postgres -p 6432 -h 127.0.0.1 thai
Password: 
pgbench (17.4 (Debian 17.4-1.pgdg120+2))
transaction type: /workload.sql
scaling factor: 1
query mode: simple
number of clients: 8
number of threads: 4
maximum number of tries: 1
duration: 10 s
number of transactions actually processed: 353440
number of failed transactions: 0 (0.000%)
latency average = 0.226 ms
initial connection time = 31.570 ms
tps = 35451.766279 (without initial connection time)
```