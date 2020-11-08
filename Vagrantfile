Vagrant.configure(2) do |config|
  # образ системы Ubuntu 18/04 LTS (Bionic Beaver)
  config.vm.box = "bento/ubuntu-18.04"
  # не проверять репозиторий на наличие обновлений
  config.vm.box_check_update = false
  # создание ssh-ключа
  config.ssh.insert_key = true

  # ПЕРВАЯ ВИРТУАЛЬНАЯ МАШИНА
  config.vm.define "web-server" do |subconfig|
    # имя виртуальной машины
    subconfig.vm.provider "virtualbox" do |vb|
      vb.name = "apache-server"
    end
    # hostname виртуальной машины
    subconfig.vm.hostname = "apache-server"
    # настройки сети
    subconfig.vm.network "private_network", ip: "192.168.53.3"
   
  end

  # ВТОРАЯ ВИРТУАЛЬНАЯ МАШИНА
  config.vm.define "sql-server" do |subconfig|
    # имя виртуальной машины
    subconfig.vm.provider "virtualbox" do |vb|
      vb.name = "mysql-server"
    end
    # hostname виртуальной машины
    subconfig.vm.hostname = "mysql-server"
    # настройки сети
    subconfig.vm.network "private_network", ip: "192.168.53.4"
   
    end
   config.vm.provision "ansible" do |ansible|
     ansible.verbose = "v"
     ansible.playbook = "provisioning/playbook.yml"
   end
    
end

