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
If one of these programs has been installed, then you'll see something like:

    Bringing machine 'default' up with 'virtualbox' provider...
    ==> default: Box 'hashicorp/precise64' could not be found. Attempting to find and install...
        default: Box Provider: virtualbox
        default: Box Version: >= 0
    ==> default: Loading metadata for box 'hashicorp/precise64'
        default: URL: https://atlas.hashicorp.com/hashicorp/precise64
    ==> default: Adding box 'hashicorp/precise64' (v1.1.0) for provider: virtualbox
        default: Downloading: https://atlas.hashicorp.com/hashicorp/boxes/precise64/versions/1.1.0/providers/virtualbox.box
        default: Progress: 3% (Rate: 574k/s, Estimated time remaining: 0:09:09)-)
