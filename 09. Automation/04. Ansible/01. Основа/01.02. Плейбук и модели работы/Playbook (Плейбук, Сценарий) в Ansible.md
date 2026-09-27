#flashcards/automation/Ansible
***
Текстовый файл с расширением `.yml` (или `.yaml`), в котором идет описание того, как именно должна быть настроена инфраструктура при помощи [[Ansible]].
- По сути, это просто набор инструкций, требуемое состояние к набору хостов, перечисленных в [[Inventory (Инвентарь) в Ansible|инвентаре]].
- Состоит из нескольких [[Play (Плей) в Ansible|плеев]], которые и отвечают за то, что настраивать и как именно.
- Каждый плей содержит в себе [[Tasks (Таски) в Ansible|таски]].
- А они, в свою очередь, реализованы при помощи [[Module (Модуль) в Ansible|модулей]].
***
***Пример.***
```yaml
- name: Установка Nginx
  hosts: webservers
  become: yes
  
  tasks:
    - name: Обновить кэш
      apt:
        update_cache: yes
    - name: Установить Nginx
      apt:
        name: nginx
        state: present
    - name: Запуск Nginx
      service:
        name: nginx
        state: started
        enabled: yes
```
- В примере идет работа с [[Nginx]] при помощи модулей [[Apt модуль Ansible|apt]] и [[Service модуль Ansible|service]].
<!--SR:!2026-08-11,9,250-->