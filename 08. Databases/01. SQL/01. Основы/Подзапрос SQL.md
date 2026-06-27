#flashcards/databases  
***
Полноценный запрос [[SELECT оператор SQL|SELECT]], который вложен внутрь другого (внешнего) запроса.
- Берется в круглые скобки `()`.
- База проваливается в самые глубокие скобки, полностью выполняет внутренний запрос, подставляет его на место скобок и выполняет внешний запрос.
***
***Примеры.***
1. Подзапрос с [[WHERE оператор SQL|WHERE]]: найти пиццы, стоящие больше среднего.
```SQL
SELECT pizza_name, price
FROM menu
WHERE price > (SELECT AVG(price) FROM menu);
```
2. Подзапрос с `SELECT` - ***должен возвращать одно значение (ячейку)!***
```SQL
SELECT
	name,
	(SELECT COUNT(*) FROM person_visits WHERE person_visits.person_id = person_id)
AS total_visits
FROM person;
```