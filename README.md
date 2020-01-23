# Ubuntu VM containerized development for .NET Core

Packer scripts for creating an Ubunto 16.04.3 amd64 VM based container for use as a .NET Core development environment. For VMware Workstation on Windows. 

## Setup

* [VirtualBox][virtual-box].
* [Vagrant][vagrant].
* [Packer][packer].
* [VMware Workstation][vmware-workstation].
* [Vagrant VMware plugin][vagrant-vmware-plugin] for VMware Workstation.
* [Vagrant-cachier][vagrant-cachier]

## Packer Build

Run the command `packer build [TEMPLATE]` where [TEMPLATE] is one of the JSON files listed below.

## JSON Templates

### ubuntu-16.04-vagrant.json

Packer scripts for creating an Ubunto 16.04.3 amd64 VM based container. 
For VMware Workstation on Windows.

```console
packer build ubuntu-16.04-vagrant.json
```
```console
vagrant box add --name ubuntu-16.04-vagrant ubuntu-16.04-vagrant.vmware.box
```
```console
vagrant init ubuntu-16.04-vagrant
```

### ubuntu-18.04-vagrant.json

Packer scripts for creating an Ubunto 16.04.3 amd64 VM based container. 
For VMware Workstation on Windows.

```console
packer build ubuntu-18.04-vagrant.json
```
```console
vagrant box add --name ubuntu-18.04-vagrant ubuntu-18.04-vagrant.vmware.box
```
```console
vagrant init ubuntu-18.04-vagrant
```

### ubuntu-16.04-dotnet-sdk.json

Packer scripts for creating an Ubunto 16.04.3 amd64 VM based container for use as a .NET Core development 
environment using [Docker][docker] (-swarm, and -compose). 
The script will install the version 2.2.0 of .NET Core into Docker. For VMware Workstation on Windows.

* [Docker][docker]
* [Docker Machine][docker-machine]
* [Docker Compose][docker-compose]
* [ngnix][nginx]

### Commands
  
```console
packer build ubuntu-16.04-dotnet-sdk.json
```
```console
vagrant box add --name ubuntu-16.04-dotnet-sdk ubuntu-16.04-dotnet-sdk.vmware.box
```
```console
vagrant init ubuntu-16.04-dotnet-sdk
```

### ubuntu-18.04-dotnet-sdk.json

Packer scripts for creating an Ubunto 18.04 amd64 VM based container for use as a .NET Core development 
environment using [Docker][docker] (-swarm, and -compose). 
The script will install the latest version of .NET Core into Docker. For VMware Workstation on Windows.

* [Docker][docker]
* [Docker Machine][docker-machine]
* [Docker Compose][docker-compose]
* [ngnix][nginx]

### Commands
  
```console
packer build ubuntu-18.04-dotnet-sdk.json
```
```console
vagrant box add --name ubuntu-18.04-dotnet-sdk ubuntu-18.04-dotnet-sdk.vmware.box
```
```console
vagrant init ubuntu-16.04-dotnet-sdk
```

[docker-dotnet]: https://andrewlock.net/exploring-the-net-core-2-1-docker-files-dotnet-runtime-vs-aspnetcore-runtime-vs-sdk/
[virtual-box]: https://www.virtualbox.org/
[vagrant]: https://www.vagrantup.com/downloads.html
[vagrant-vmware-plugin]: https://www.vagrantup.com/vmware/
[vagrant-esxi-plugin]: https://github.com/josenk/vagrant-vmware-esxi
[vagrant-cachier]: http://fgrehm.viewdocs.io/vagrant-cachier/
[vagrant-winnfsd]: https://github.com/winnfsd/vagrant-winnfsd
[packer]: https://www.packer.io/
[docker]: https://www.docker.com/get-docker
[docker-machine]: https://docs.docker.com/machine/overview/
[docker-compose]: https://docs.docker.com/compose/
[vmware-workstation]: https://www.vmware.com/products/workstation-pro.html
[vmware-ovf]: https://www.vmware.com/support/developer/ovf/
[kubernetes]: https://kubernetes.io/
[minikube]: https://kubernetes.io/docs/setup/minikube/
[kompose]: https://kompose.io/
[nginx]: https://nginx.com
[microk8s]: https://microk8s.io/