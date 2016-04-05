#Instructions for building a Greenplum 4.3.4.0 environment with Vagrant

This Vagrant build will create four ( 4 ) Greenplum Database nodes.

The four ( 4 ) nodes are:

  mdw-->greenplum master

  smdw-->greenplum standby master

  sdw-->greenplum segment host 1

  sdw-->greenplum segment host 2


The scripts that get executed are:

Vagrantfile -- Vagrant script to define the build process

install_applications.sh -- script to install required applications ( non Greenplum Applications ) onto the nodes

setup_host.sh -- on each host creates minimal /etc/hosts file, creates /data directory and populates .bashrc file

setup_master.sh -- generates ssh keys, pushes keys to other nodes, sets kernel and security limits parameters and copies them to other hosts

change_password.sh -- changes root password from 'vagrant' to 'Piv0tal'

install_lab_data_on_sdw1.sh -- copies files required for lab exercises to sdw1

install_lab_data_on_mdw.sh -- copies files required for lab exercises to mdw ( including Greenplum Database & Command Center installation files )

unmount_vagrant.sh -- unmounts /vagrant directory

This build DOES NOT install / configure Greenplum 4.3.4.0 or Greenplum Command Center 1.3.0.0

Once built this environment can be used to install / configure Greenplum 4.3.4.0 and Greenplum Command Center 1.3.0.0

------------------
------------------

1. Install Virtualbox from -- https://www.virtualbox.org/wiki/Downloads
2. Install latest version of Vagrant from -- http://downloads.vagrantup.com/
3. Download 'VM-Bits-4-3-4-0.7z' from -- https://drive.google.com/open?id=0B0GuXbbUzfoWVEswa2Z6aWR2Nnc

Building the Greenplum 4.3.4.0 Environment

--------------
--------------

Enter following commands in a terminal window

$ git init

$ git clone https://github.com/danabrenn/greenplum-4-3-4-0_no_install.git

$ cd greenplum-4-3-4-0_no_install

Unzip 'VM-Bits-4-3-4-0.7z' to 'greenplum-4-3-4-0_no_install'


$ vagrant up

Once the vagrant build process is completed you have a Greenplum Cluster on which you can install the Greenplum Database version 4-3-4-0 and the Greenplum Command Center 1.3.0.0
