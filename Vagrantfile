# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
   config.vm.boot_mode = :gui
   config.vm.box_url = "https://dl.dropbox.com/u/527582/stackops-distro-base-v2.box"

   config.vm.box = "stackops-distro-base-v2"
   config.vm.forward_port 22, 2222
   config.vm.forward_port 80, 8000
   config.vm.forward_port 443, 8443
   config.vm.forward_port 6080, 6080
   config.vm.network :hostonly, "192.168.11.2", :adapter => 2
   config.vm.network :hostonly, "192.168.12.2", :adapter => 3
   config.vm.network :hostonly, "192.168.13.2", :adapter => 4
   config.vm.customize ["modifyvm",:id, "--memory", 1024]

   config.vm.provision :shell, :inline => <<-EOF
     #!/bin/sh
     export DEBIAN_FRONTEND=noninteractive
     apt-get -q -y install fabric
     wget https://www.dropbox.com/s/3hn7dy4ldwqy3lr/folsom.tar.gz
     tar zxvf folsom.tar.gz
   EOF

end



