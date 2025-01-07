# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Use the official Kali Linux rolling box
  config.vm.box = "kalilinux/rolling"

  # VirtualBox-specific settings
  config.vm.provider "virtualbox" do |vb|
    # Show the VirtualBox GUI when booting
    vb.gui = true

    # Allocate some memory. Adjust as you like, but stay within your 7.3GB budget.
    vb.memory = "4096"   # 4GB RAM
    vb.cpus   = 2        # 2 CPU cores
  end

  # Provision with Ansible inside the Kali guest (ansible_local)
  config.vm.provision "ansible_local" do |ansible|
    # The playbook to run on the Kali VM
    ansible.playbook = "ansible/main.yml"

    # Installs Ansible on the guest if not present
    ansible.install = true

    # Compatible with Ansible 2.0+ syntax
    ansible.compatibility_mode = "2.0"
  end
end
