Lightweight Vagrant VM for Rails Development
============================================

Using The VM
------------

-Install VirtualBox

-Install Vagrant

-Import VM into Vagrant

`$ vagrant box add bastli_box http://www.bastli.ethz.ch/dev/package.box`

-Go into working directory and Init the VM

`$ vagrant init bastli_box`

`$ vagrant up`

-SSH into VM 

`$ vagrant ssh`

-Suspend VM

`$ vagrant suspend`

-Resume VM

`$ vagrant resume`

-Halt VM

`$ vagrant halt`

-Start VM

`$ vagrant up`


Building and Packaging VM
-------------------------------
-Install VirtualBox

-Install Vagrant

-Install Ruby

-Install Librarian Gem

`$ gem install librarian`

-Install git

-Clone Git Repo

-Setup Cookbooks

`librarian-chef install`

-Build VM

`$ vagrant up`

-Make updates and changes if necessary

-Package VM

`$ vagrant package --vagrantfile Vagrantfile.pkg`








