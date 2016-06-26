# My Docker Stacks

Some frequently used docker compose stacks. Very handy when testing containers outside of a platform such as Rancher.

I use alpine flavour when possible to be minimalistic.

## Prerequisites

The databases map to a volume called `/var/lib/data/`. If you are using boot2docker, you will need to mount it in the VM. 

On windows:

	VBoxManage.exe sharedfolder add local --name mydata --hostpath D:\data --automount

On Linux:

 	VBoxManage sharedfolder add local --name mydata --hostpath /data --automount

Everytime boot2docker is restarted:

	docker-machine ssh default
	docker@default:~$ sudo mkdir /var/lib/data
	docker@default:~$ sudo mount -t vboxsf mydata /var/lib/data

A good reference article here: [mounting windows folders to boot2docker vm](http://tuhrig.de/mount-windows-folder-to-boot2docker-vm/)

## Usage

Simply go into the relevant directory and run `docker-compose up -d`