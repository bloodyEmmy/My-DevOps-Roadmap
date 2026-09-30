#flashcards/automation/Ansible 
***
Директория, которая по умолчанию создается при задании новой [[Роль в Ansible|роли]].
- В ней содержится реализация [[Хендлер в Ansible|хендлеров]].
- Создается один файл `main.yml` по умолчанию, но может быть добавлено несколько других файлов, которые будут импортироваться в главный - прямо как в [[Tasks папка роли Ansible|tasks]].
***
***Пример реализации.***
1. Пусть у нас есть три файла в директории: `main.yml`, `nginx.yml` (для [[Nginx]]) и `postgresql.yml` (для базы данных [[PostgreSQL]]).
2. И пусть в `nginx.yml` описана работа Nginx через [[Module (Модуль) в Ansible|модуль]] [[Service модуль Ansible|service]]:
```yml
- name: Restart Nginx
  service:
    name: nginx
    state: restarted
```
3. Тогда в `main.yml` мы импортируем оба файла:
```yml
- name: Импорт хендлеров для Nginx
  import_tasks: nginx.yml
  
- name: Импорт хендлеров для PostgreSQL
  import_tasks: postgresql.yml
```