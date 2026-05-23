#flashcards
***
Создает новый [[Сервис в Swarm|сервис]].
***Синтаксис.***
```bash
docker service create <флаги> <образ> <команда> <аргументы>
```
***
***Флаги.***
1. `--name <имя>` - Имя сервиса.
2. `--replicas <N>` - Количество реплик (если сервис реплицированный).
3. `--mode <replicated|global>` - Тип сервиса. По умолчанию `replicated`.
4. `--mount type=<volume|bind>,source=<source>,target=<target>` - [[Bind Mount (Монтирование каталогов с хоста)|Монтирование]] [[Том Docker|тома]].
5. `--network < network>` - Подключение к [[Сеть Docker|сети]].
