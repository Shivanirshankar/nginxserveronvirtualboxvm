Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/focal64" # Ubuntu 20.04
    config.vm.network "private_network", type: "dhcp"
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.cpus = 2
    end
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt update -y
      sudo apt install -y nginx
      echo "<h1>Hello from Vagrant Nginx Server!</h1>" | sudo tee /var/www/html/index.html
      sudo systemctl enable nginx
      sudo systemctl start nginx
    SHELL
  end
  