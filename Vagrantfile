# -*- mode: ruby -*-
# vi: set ft=ruby :

boxes = [
  {
    :name => "debian-jessie",
    :box => "debian/jessie64",
    :version => "8.8.0",
    :ip => '10.10.10.10',
    :cpu => "50",
    :ram => "256"
  }
]

Vagrant.configure("2") do |config|
  boxes.each do |box|
    config.vm.define box[:name] do |vms|
      vms.vm.box = box[:box]
      vms.vm.box_version = box[:version]
      vms.vm.hostname = "ansible-#{box[:name]}"

      vms.vm.provider "virtualbox" do |v|
        v.customize ["modifyvm", :id, "--cpuexecutioncap", box[:cpu]]
        v.customize ["modifyvm", :id, "--memory", box[:ram]]
      end

      vms.vm.network :private_network, ip: box[:ip]

      vms.vm.provision :ansible do |ansible|
        ansible.playbook = "tests/test.yml"
      end
    end
  end
end
