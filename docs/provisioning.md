# Provisioning #

We could just SSH in and install a webserver and be on our way, but then every person who used Vagrant would have to do the same thing. Instead, Vagrant has built-in support for automated provisioning. Using this feature, Vagrant will automatically install software when you vagrant up so that the guest machine can be repeatably created and ready-to-use.

## Installing Apache ##

We will just setup Apache for our basic project, and we will do so using a shell script. Create the following shell script and save it as **bootstrap.sh** in the same directory as your **Vagrantfile**:

    #!/usr/bin/env bash

    apt-get update
    apt-get install -y apache2
    if ! [ -L /var/www ]; then
      rm -rf /var/www
      ln -fs /vagrant /var/www
    fi

Next, we configure Vagrant to run this shell script when setting up our machine. We do this by editing the Vagrantfile, which should now look like this:

    Vagrant.configure("2") do |config|
      config.vm.box = "hashicorp/precise64"
      config.vm.provision :shell, path: "bootstrap.sh"
    end

The "provision" line is new, and tells Vagrant to use the shell provisioner to setup the machine, with the **bootstrap.sh** file. The file path is relative to the location of the project root (where the **Vagrantfile** is).

## Provision! ##

After everything is configured, just run **vagrant up** to create your machine and Vagrant will automatically provision it. You should see the output from the shell script appear in your terminal. If the guest machine is already running from a previous step, run **vagrant reload --provision**, which will quickly restart your virtual machine, skipping the initial import step. The provision flag on the reload command instructs Vagrant to run the provisioners, since usually Vagrant will only do this on the first **vagrant up**.

TODO
