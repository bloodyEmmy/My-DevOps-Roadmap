#flashcards/monitoring/Loki 
***
Файл формата `.yml`, в котором идет полное описание и настройка [[Loki]] в рамках рассматриваемого [[Кластер|кластера]].
- `loki-config.yml` является аналогом `docker-compose.yml` в рамках настройки [[Docker Compose]] на одном хосте или [[Docker Swarm]] на нескольких [[Сервер (Клиент Серверная Архитектура)|серверах]].
- Чаще всего пробрасывается в `docker-compose.yml` в [[Volumes раздел Compose|раздел volumes]].
```yml
volumes:
# прокидываем наш конфиг-файл внутрь контейнера Loki 
  - ./loki-config.yaml:/etc/loki/local-config.yaml
# прокидываем папку, куда Loki будет физически складывать логи 
  - loki-data:/loki
```