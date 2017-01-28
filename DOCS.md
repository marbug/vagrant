# vagrant official manual #

## Getting started ##
In command-line/shell run:

    mkdir vagrant
    cd vagrant

Then run:

    vagrant init hashicorp/precise64

The following or similar text should be shown:

    A `Vagrantfile` has been placed in this directory. You are now
    ready to `vagrant up` your first virtual environment! Please read
    the comments in the Vagrantfile as well as documentation on
    `vagrantup.com` for more information on using Vagrant.

After this please run:

    vagrant up

If you see text like:

    No usable default provider could be found for your system.

    Vagrant relies on interactions with 3rd party systems, known as
    "providers", to provide Vagrant with resources to run development
    environments. Examples are VirtualBox, VMware, Hyper-V.

    The easiest solution to this message is to install VirtualBox, which
    is available for free on all major platforms.

    If you believe you already have a provider available, make sure it
    is properly installed and configured. You can see more details about
    why a particular provider isn't working by forcing usage with
    `vagrant up --provider=PROVIDER`, which should give you a more specific
    error message for that particular provider.

then one of programs (VirtualBox, VMware, etc) should be installed.
