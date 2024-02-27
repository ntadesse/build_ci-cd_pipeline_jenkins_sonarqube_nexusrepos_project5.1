Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true 
  config.hostmanager.manage_host = true
  config.ssh.insert_key = false
  config.vbguest.auto_update = false
### jenkins vm  #### 
  config.vm.define "jn01" do |jn01|
    jn01.vm.box = "ubuntu/jammy64"
    jn01.vm.hostname = "jn01"
    jn01.vm.network "private_network", ip: "192.168.56.14"
	jn01.vm.network "public_network"
    jn01.vm.provider "virtualbox" do |vb|
     vb.memory = "3072"
	 vb.cpus = "2"
   end
    jn01.vm.provision "shell", path: "jenkins.sh"  
  end
### nexus vm  ####
  config.vm.define "nexus01" do |nexus01|
    nexus01.vm.box = "generic/centos7"
    nexus01.vm.hostname = "nexus01"
    nexus01.vm.network "private_network", ip: "192.168.56.15"
	nexus01.vm.network "public_network"
    nexus01.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
   end
    nexus01.vm.provision "shell", path: "nexus-setup.sh"  

  end
  
### sonar vm  #### 
  config.vm.define "sonar01" do |sonar01|
    sonar01.vm.box = "ubuntu/jammy64"
    sonar01.vm.hostname = "sonar01"
    sonar01.vm.network "private_network", ip: "192.168.56.14"
	sonar01.vm.network "public_network"
    sonar01.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
   end
    sonar01.vm.provision "shell", path: "sonar-setup.sh"  
  end
  
end
