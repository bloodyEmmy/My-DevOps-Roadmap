#flashcards/automation/Ansible 
***
Инструмент для отправки уведомлений [[Хендлер в Ansible|хендлерам]].
- Именно он связывает обычные [[Tasks (Таски, Задачи) в Ansible|таски]] и обработчики, показывая, что задача внесла изменения на [[Сервер (Клиент Серверная Архитектура)|сервер]] и нам нужно выполнить хендлер.
- Работает по принципу [[Идемпотентность|идемпотентности]] - хендлер работает только тогда, когда были внесены изменения в настройку и работу хоста (статус `changed`).
***
***Пример.***
```yml
- name: Скопировать новый конфиг Nginx
  template:
    src: nginx.conf.j2
    dest: /etc/nginx/nginx.conf
    notify: Restart Nginx Service # ставим название хендлера

- name: Restart Nginx Service
  service:
    name: nginx
    state: restarted
```
- Используются [[Module (Модуль) в Ansible|модули]] [[Template модуль Ansible|template]] и [[Service модуль Ansible|service]] для работы с [[Nginx]].
***
Можно прописывать запуск сразу нескольких хендлеров:
```yml
notify:
  - Restart Rsyslog
  - Clear App Cache
```