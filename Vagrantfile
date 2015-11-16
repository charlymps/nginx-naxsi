# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Beginning of vm "nginx" configuration section
  config.vm.define "nginx" do |server|
    server.vm.box = "centos64"
    server.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.4.2/centos64-x86_64-20140116.box"
    server.vm.network :private_network, ip: "10.10.0.40"
    server.vm.hostname = "nginx.charlymps.com"
    server.vm.provision :ansible do |ansible|
      ansible.playbook = "ansible/nginx.yml"
      # This is required because to prevent Host key checking errors when the vagrant machine is recreated with another key
      ansible.host_key_checking = false
    end
  end

end
