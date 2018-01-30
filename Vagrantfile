# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  config.vm.define "bob-jenkins", autostart: true do |jenkins|
    jenkins.vm.hostname = "bob.vagrant.dev"
    jenkins.vm.network "forwarded_port",
      guest: 8080,
      host: 8080,
      auto_correct: true
    jenkins.vm.provider "virtualbox" do |vb|
      vb.memory = "4096"
      vb.cpus = "4"
    end
    jenkins.vm.provision "setup jenkins master",
      type: "ansible_local" do |ansible|

      ansible.playbook = "/vagrant/playbook.yml"
      ansible.limit = "all"
      ansible.inventory_path = "/vagrant/inventory.ini"
      ansible.config_file = "/vagrant/ansible.cfg"
      ansible.galaxy_role_file = "/vagrant/requirements.yml"
      ansible.galaxy_roles_path = "/vagrant/roles"
      ansible.galaxy_command = "ansible-galaxy install --role-file=%{role_file} --roles-path=%{roles_path}"

    end
  end
end
