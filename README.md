# NginxVagrant
Vagrant file for Nginx

This vagrant file is to create a virtual machine with Centos 7.

It installs Docker CE and Docker compose.

Pulls the code from https://github.com/rakesh635/NginxDocker, which contains nginx flavoured Dockerfile.

Once docker image is built and container is up, modification in host file to serve,

myfirstpage.com as locahost/1.html

mysecondpage.com as locahost/2.html

mythirdpage.com as locahost/3.html

# STEPS

> Follow the installation step of Vagrant from https://www.vagrantup.com/docs/installation/ \n
> Clone the repo \n
> run "vagrant up"
> execute "vagrant ssh"
> once ssh into vagrant machine, try
  curl myfirstpage.com
  curl myfirstpage.com
  curl myfirstpage.com
> execute "exit" , to exit out from the vagrant machine.


