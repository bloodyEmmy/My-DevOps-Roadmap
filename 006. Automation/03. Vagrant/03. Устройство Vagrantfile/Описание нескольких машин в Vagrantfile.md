#flashcards/automation/Vagrant 
***
Все описание происходит в одном [[Vagrantfile]], каждая [[Виртуальная машина|виртуалка]] описывается последовательно с помощью `congig.vm.define`.
***Пример.***
```Ruby
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  
  config.vm.define "web" do |web|
    web.vm.hostname = "web-server"
    web.vm.network "private_network", ip: "192.168.50.10"
    web.vm.provision "shell", inline: "apt-get install -y nginx"
  end
  
  config.vm.define "db" do |db|
    db.vm.hostname = "db-server"
    db.vm.network "private_network", ip: "192.168.50.20"
    db.vm.provision "shell", inline: "apt-get install -y postgresql"
  end
end
```
- Здесь ВМ в одной [[Подсеть|подсети]] (то есть подключены к одному виртуальному [[Коммутатор (switch)|коммутатору]] [[Гипервизор|гипервизора]]), выбран режим [[Private Network в Vagrantfile|private_network]].
- В качестве [[Provisioner (Провижионер) в Vagrant|провижионера]] выбран [[Shell Provisioner в Vagrant|shell]].
- При старте через [[Up команда Vagrant|up]] поднимутся обе ВМ, теперь использовать команды нужно будет упоминая имя конкретной ВМ.