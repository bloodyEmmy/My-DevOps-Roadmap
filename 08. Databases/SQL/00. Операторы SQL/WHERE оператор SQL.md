#flashcards/databases 
***
Используется для фильтрации строк (в отличие от [[SELECT оператор SQL|SELECT]], который смотрит столбцы).
- Нужен для фильтрации данных по заданному условию.
- Пишется всегда после [[FROM оператор SQL|FROM]].
***
***Синтаксис.***
```SQL
SELECT <столбцы>
FROM <таблица>
WHERE <условие>;
```
***
- ***Операторы:*** `=`, `!=` или `<>`, `>` и `<`, `>=` и `<=`.
- ***Числа:*** `WHERE id = 5`.
- ***Текст и даты*** - в одинарных кавычках! `WHERE name = 'Anna'` или `WHERE visit_date = '2022-01-01'`.
***
***Логические операторы.***
1. AND - несколько условий выполняются одновременно.
```SQL
SELECT * FROM person WHERE gender = 'male' AND age > 18;
```
2. OR - выполняется хотя бы одно из условий.
```SQL
SELECT * FROM person WHERE city = 'Moscow' OR city = 'Kazan';
```
3. Скобки `()` - для расстановки приоритетов.
```SQL
SELECT * FROM person
WHERE gender = 'male' AND (city = 'Moscow' OR city = 'Kazan');
```