#flashcards/automation/Vagrant
***
Самый базовый вариант [[Provisioner (Провижионер) в Vagrant|провижионера]].
- Прочитать про него можно [[Shell Provisioner в Vagrant|здесь]].
***
***Синтаксис.***
```Ruby
config.vm.provision "shell", inline: <<-SHELL
  apt-get update
  apt-get install -y nginx
SHELL
```
- В примере использовано скачивание [[Nginx]].
***
Также можно подключить готовый [[Bash]]-скрипт, в котором прописана инструкция.
```Ruby
config.vm.provision "shell", path: "filename.sh"
```
- Файл должен лежать там же, где и [[Vagrantfile]].
<!--SR:!2026-08-09,8,250-->