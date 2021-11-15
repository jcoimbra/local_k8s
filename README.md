# Local k8s

This project allows to quickly create a local kubernetes cluster.

## Requirements

* [Virtual Box](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/)
* [Ansible](https://www.ansible.com/)

## How to use

Clone this repo to your computer, change directory into the project and enter the following command:

```shell
$ vagrant up
```

This will create a total of 3 virtual machines. One master and two workers. At the project root, a file with the name
`config.conf` will be created. Use that file to configure `kubectl` to access the cluster as in:

```shell
$ kubectl --kubeconfig config.conf get nodes
```

For convenience, use an alias: `$ alias lk8s="kubectl --kubeconfig config.conf"`. 