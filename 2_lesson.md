### Lesson2
## name: Подсытник Дмитрий Александрович
## Result
Открыть консоль и зайти по ssh на ВМ в ЯО/любое другое подключение

MacOS vagrant+ wmvare_fusion provider

Открыть вторую консоль и также зайти по ssh на ту же ВМ в WB cloud или ЯО
Запустить везде psql из под пользователя postgres к одному кластеру ПГ
Сделать в первой сессии новую таблицу и наполнить ее данными
Посмотреть текущий уровень изоляции
Начать новую транзакцию в обоех сессиях с дефолтным (не меняя) уровнем изоляции
В первой сессии добавить новую запись
Сделать запрос на выбор всех записей во второй сессии
### Видите ли вы новую запись и если да то почему? После задания можете сверить правильный ответ с эталонным
```
Нет не вижу
```
Завершить транзакцию в первом окне
Сделать запрос на выбор всех записей второй сессии
### Видите ли вы новую запись и если да то почему?
```
Вижу, это неповторяющее чтение
```
Завершите транзакцию во второй сессии
Начать новые транзакции, но уже на уровне repeatable read в ОБЕИХ сессиях
В первой сессии добавить новую запись
Сделать запрос на выбор всех записей во второй сессии
### Видите ли вы новую запись и если да то почему?
```
Не вижу
```
Завершить транзакцию в первом окне
Сделать запрос во выбор всех записей второй сессии
### Видите ли вы новую запись и если да то почему?
```
Не вижу, фантомное чтение не работает.
``` 
