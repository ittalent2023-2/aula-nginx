Vagrant.configure("2") do |config|
  config.vm.define "server" do |server|
    server.vm.box = "ubuntu/focal64"
    server.vm.hostname = "server"
    config.vm.network "public_network"
    server.vm.synced_folder "C:/Users/Viviana/it-talent/aula-nginx/data", "/data"
    server.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end

    # Instalação do Git e Curl
    server.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y git curl
      curl -fsSL https://get.docker.com -o get-docker.sh     
      sudo sh get-docker.sh
      sudo usermod -aG docker vagrant
    SHELL
  end
end
