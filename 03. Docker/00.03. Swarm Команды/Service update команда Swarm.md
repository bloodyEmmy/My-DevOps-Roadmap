#flashcards
***
Обновляет параметры работающего [[Сервис в Swarm|сервиса]].
***Синтаксис.***
```bash
docker service update <флаги> <сервис>
```
***
***Флаги***:
1. `--image <образ>` - обновить [[Образ контейнера (Docker Image)|образ]].
2. `--replicas <N>` - изменить число реплик.
3. `--label-add <Ключ>=<Значение>` - Добавить [[Метка (Label)|метку]] сервиса.
4. `--label-rm <Ключ>` - Удалить метку.
5. `--mount-add type=<type>,source=<source>,target=<target>` - Добавить [[Bind Mount (Монтирование каталогов с хоста)|бинд]].
6. `--mount-rm <target>` - Удалить бинд.
7. `--rollback` - Откатить к предыдущей версии. По сути - [[Service rollback команда Swarm|rollback]].
