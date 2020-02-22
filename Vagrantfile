Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"

  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end

  config.vm.provision "docker"

end
