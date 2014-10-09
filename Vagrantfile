# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/trusty64"
    master.vm.hostname = "salt"
    master.vm.network  "private_network",  ip: "192.168.45.45"
    master.vm.synced_folder "master/states", "/srv/salt"
    master.vm.synced_folder "master/pillar", "/srv/pillar"
  end

  config.vm.define "minion1" do |minion1|
    minion1.vm.box = "ubuntu/trusty64"
    minion1.vm.hostname = "webserver"
    minion1.vm.network  "private_network", ip: "192.168.45.50"
  end

  config.vm.define "minion2" do |minion2|
    minion2.vm.box = "chef/debian-7.4"
    minion2.vm.hostname = "elasticsearch"
    minion2.vm.network  "private_network", ip: "192.168.45.51"
  end
end
