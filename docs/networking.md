# Networking #

At this point we have a web server up and running with the ability to modify files from our host and have them automatically synced to the guest. However, accessing the web pages simply from the terminal from inside the machine is not very satisfying. In this step, we will use Vagrant's networking features to give us additional options for accessing the machine from our host machine.

## Port Forwarding ##

    Vagrant.configure("2") do |config|
      config.vm.box = "hashicorp/precise64"
      config.vm.provision :shell, path: "bootstrap.sh"
      config.vm.network :forwarded_port, guest: 80, host: 4567
    end

Run a **vagrant reload** or **vagrant up** (depending on if the machine is already running) so that these changes can take effect.

Once the machine is running again, load [http://127.0.0.1:4567](http://127.0.0.1:4567) in your browser. You should see a web page that is being served from the virtual machine that was automatically setup by Vagrant.

## Other Networking ##

Vagrant also has other forms of networking, allowing you to assign a static IP address to the guest machine, or to bridge the guest machine onto an existing network. If you are interested in other options, read the [networking](https://www.vagrantup.com/docs/networking/) page.

TODO
