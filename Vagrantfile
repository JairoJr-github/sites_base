# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
  ## Base
  config.vm.box = "ubuntu/bionic64"
  config.vm.hostname = "ubuntu"

  config.vm.define "wordpress" do |wordpress|
    ## Rede
      wordpress.vm.network "forwarded_port", guest: 80, host: 8080
      wordpress.vm.network "public_network", ip: "192.168.15.82"  
  
    ## Compartilhamento de pastas
      wordpress.vm.synced_folder "./configs", "/configs"

      wordpress.vm.provision "shell", path: "provision.sh"

    end


end

# senha wordpress: VT5mCFvLXvGSkz(Ia!

# $1t&-@ptuR&
# docker exec -it configs_wordpress_1 /bin/bash
# docker restart configs_wordpress_1

# passos wordpress
# 1- Acessar a vm, entrar na pasta /configs e executar o comando:
#   docker-compose up
# 2- Acessar container com o comando:
#   docker exec -it configs_wordpress_1 /bin/bash
# 3- Fazer apt-get update e upgrade
# 4- liberar acesso na pasta /var/www/html com o comando
#   chmod -R 777 html
# 5- alterar o arquivo .htaccess para liberar o upload_file_size
#     php_value upload_max_filesize 64M
#     php_value post_max_size 64M
# 6- Instalar o plugin do Elementor free na loja e baixar o 
# pro elements no site https://proelements.org/ 
# 

