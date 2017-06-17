# Boxes #

Instead of building a virtual machine from scratch, which would be a slow and tedious process, Vagrant uses a base image to quickly clone a virtual machine. These base images are known as "boxes" in Vagrant, and specifying the box to use for your Vagrant environment is always the first step after creating a new Vagrantfile.

## Installing a Box ##

    vagrant box add hashicorp/precise64

This will download the box named "hashicorp/precise64" from HashiCorp's Atlas box catalog, a place where you can find and host boxes. While it is easiest to download boxes from HashiCorp's Atlas you can also add boxes from a local file, custom URL, etc.

## Using a Box ##

Now that the box has been added to Vagrant, we need to configure our project to use it as a base. Open the Vagrantfile and change the contents to the following:

    Vagrant.configure("2") do |config|
      config.vm.box = "hashicorp/precise64"
    end

The "hashicorp/precise64" in this case must match the name you used to add the box above. This is how Vagrant knows what box to use. If the box was not added before, Vagrant will automatically download and add the box when it is run.

You may specify an explicit version of a box by specifying **config.vm.box_version** for example:

    Vagrant.configure("2") do |config|
      config.vm.box = "hashicorp/precise64"
      config.vm.box_version = "1.1.0"
    end

You may also specify the URL to a box directly using **config.vm.box_url**:

    Vagrant.configure("2") do |config|
      config.vm.box = "hashicorp/precise64"
      config.vm.box_url = "http://files.vagrantup.com/precise64.box"
    end

## Finding More Boxes ##

The best place to find more boxes is [HashiCorp's Atlas box catalog](https://atlas.hashicorp.com/boxes/search?_ga=2.191756655.455264635.1497662025-1267076092.1496932163). HashiCorp's Atlas has a public directory of freely available boxes that run various platforms and technologies. HashiCorp's Atlas also has a great search feature to allow you to find the box you care about.

In addition to finding free boxes, HashiCorp's Atlas lets you host your own boxes, as well as private boxes if you intend on creating boxes for your own organization.

[prev page: Vagrantfile](vagrantfile.md) | TODO
