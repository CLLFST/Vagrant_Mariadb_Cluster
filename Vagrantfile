
Vagrant.configure("2") do |config|
	config.vm.box = "debian/jessie64"
	config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/playMe.yml"
	end

	config.vm.define "SQL0" do |master|
		master.vm.hostname = "sql0"
		master.vm.network "private_network", ip:"192.168.2.2"
		master.vm.provider "virtualbox" do |v|
			v.name   = "sql0"
			v.memory = 256
		end
	end

	config.vm.define "SQL1" do |first_slave|
		first_slave.vm.hostname = "sql1"
		first_slave.vm.network "private_network", ip:"192.168.2.3"
		first_slave.vm.provider "virtualbox" do |v|
			v.name   = "sql1"
			v.memory = 256
		end
	end

	config.vm.define "SQL2" do |second_slave|
		second_slave.vm.hostname = "sql2"
		second_slave.vm.network "private_network", ip:"192.168.2.4"
		second_slave.vm.provider "virtualbox" do |v|
			v.name   = "sql2"
			v.memory = 256
		end
	end

	config.vm.define "LB" do |master|
		master.vm.hostname = "lb"
		master.vm.network "private_network", ip:"192.168.2.10"
		master.vm.provider "virtualbox" do |v|
			v.name   = "lb"
			v.memory = 256
		end
	end	
end
