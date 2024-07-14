# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
    # Configuración de la primera máquina virtual
    config.vm.define "web1" do |web1|
      web1.vm.box = "ubuntu/bionic64"
      web1.vm.network "private_network", type: "dhcp"
      web1.vm.hostname = "web1"
      
      web1.vm.provision "shell", inline: <<-SHELL
        # Actualizar repositorios e instalar Apache
        sudo apt-get update
        sudo apt-get install -y apache2
        
        # Configurar el servidor web
        echo "<html><body><h1>Hola Mundo desde web1</h1></body></html>" > /var/www/html/index.html
      SHELL
    end
    
    # Configuración de la segunda máquina virtual
    config.vm.define "web2" do |web2|
      web2.vm.box = "ubuntu/bionic64"
      web2.vm.network "private_network", type: "dhcp"
      web2.vm.hostname = "web2"
      
      web2.vm.provision "shell", inline: <<-SHELL
        # Actualizar repositorios e instalar Apache
        sudo apt-get update
        sudo apt-get install -y apache2
        
        # Configurar el servidor web
        echo "<html><body><h1>Hola Mundo desde web2</h1></body></html>" > /var/www/html/index.html
      SHELL
    end
    
    # Compartir carpeta local con el servidor web
    config.vm.synced_folder "./codigo_html", "/var/www/html"
    
  end
  