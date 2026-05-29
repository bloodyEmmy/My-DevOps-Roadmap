#flashcards/Docker
***
Изменяет количество реплик, то есть копий [[Задача (Task) в Swarm|задач]] одного [[Сервис в Swarm|сервиса]].
***Синтаксис.***
```bash
docker service scale <сервис>=<реплика> ...
```
- Можно задавать несколько настроек подряд в одну строку.
***
***Примеры.***
1. `docker service scale web=5`
2. `docker service scale web=5 api=3 worker=10`
3. `docker service scale web=0` (остановить все реплики)
