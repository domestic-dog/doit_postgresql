# Lesson 4  
## name: Подсытник Дмитрий Александрович  
### Result:
Создать таблицу accounts(id integer, amount numeric);  



Добавить несколько записей и подключившись через 2 терминала добиться ситуации взаимоблокировки (deadlock).  



Посмотреть логи и убедиться, что информация о дедлоке туда попала.  
```
2025-04-03 19:31:09.461 EDT [3641] postgres@postgres WARNING:  there is already a transaction in progress
```
