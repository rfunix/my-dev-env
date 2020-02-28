Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |vbox|
    vbox.memory = 8192
    vbox.cpus = 2
  end

  config.vm.network "forwarded_port", guest: 8000, host: 8080
  config.vm.box = "hashicorp/bionic64"

  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end

  config.vm.provision "file", source: "~/.ssh/id_rsa", destination: "~/.ssh/id_rsa"
  config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/id_rsa.pub"
  config.vm.provision "docker"

end
