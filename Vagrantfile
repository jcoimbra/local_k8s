Vagrant.configure("2") do |config|
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.groups = {
      "kubernetes-master" => ["master"],
      "kubernetes-worker" => ["worker1", "worker2"]
    }
    ansible.force_remote_user = false
  end

  config.vm.define "master" do |master|
    master.vm.box = "centos/stream8"
    master.vm.box_version = "20210210.0"
    master.vm.hostname = "master"
    master.vm.network "private_network", ip: "192.168.56.10"
    master.vm.provider "virtualbox" do |v|
      v.memory = 4096
      v.cpus = 2
    end
  end

  config.vm.define "worker1" do |worker|
    worker.vm.box = "centos/stream8"
    worker.vm.box_version = "20210210.0"
    worker.vm.hostname = "worker1"
    worker.vm.network "private_network", ip: "192.168.56.11"
    worker.vm.provider "virtualbox" do |v|
      v.memory = 4096
      v.cpus = 2
    end
  end

  config.vm.define "worker2" do |worker|
    worker.vm.box = "centos/stream8"
    worker.vm.box_version = "20210210.0"
    worker.vm.hostname = "worker2"
    worker.vm.network "private_network", ip: "192.168.56.12"
    worker.vm.provider "virtualbox" do |v|
      v.memory = 4096
      v.cpus = 2
    end
  end
end
