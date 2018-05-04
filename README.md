# Settup Vagrant Box

Isolated portable development environment

### Installation

You need to install Virtualbox and Vagrant

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com)

  After installing vagrant to your computer check the version

```
vagrant -v
```

its good practice to create a directory to work on

```
mkdir vagrant
```

To initialize vagrant write

```
vagrant init ubuntu/trusty64
```

to start the box

```
vagrant up
```

you can change box settings using vagrantfile for example
if you want to change the memory and cpu of the box

```
 config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
    vb.cpus = 2

  end
```

after excuting or uncommenting this you need to restart your box

```
vagrant relaod
```

And you can install software and packages using inline provision(with in Vigrantfile) or through path in this settup we have used a file install.sh

```
  config.vm.provision "shell", path: "install.sh"
end
```

all the packages are in install.sh

```
vagrant provision
```

above command installs the provision from install.sh which includes apache2, PHP and Mysql

now login to your box through ssh

```
vagrant ssh
```

## Creating Mysql database

```
mysql -u root - p
```

```
CREATE DATABASE box;
```

```
use box;
```

### CREATE TABLE

We are going to create table users

```
create table users (id INT AUTO_INCREMENT, username VARCHAR(50), email VARCHAR(50), password VARCHAR(250), primary key (id));
```

## Finally

to destroy your box write

```
vagrant destroy
```
