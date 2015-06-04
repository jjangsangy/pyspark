# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

ipythonPort = 8001

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.define "pyspark" do |master|
      master.vm.box_download_insecure = true
      master.vm.boot_timeout = 900
      master.vm.network :forwarded_port, host: ipythonPort, guest: ipythonPort, auto_correct: true   # IPython port (set in notebook config)
      master.vm.hostname = "pyspark"
      master.vm.usable_port_range = 4040..4090

      master.vm.provider :virtualbox do |v|
          v.name = master.vm.hostname.to_str
      end
  end
end
