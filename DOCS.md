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

then one of programs (VirtualBox, VMware, etc) should be installed first.
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

After download is finished you'll see the text:

          default: Progress: 100% (Rate: 722k/s, Estimated time remaining: --:--:--)
      ==> default: Successfully added box 'hashicorp/precise64' (v1.1.0) for 'virtualbox'!
      ==> default: Importing base box 'hashicorp/precise64'...
      ==> default: Matching MAC address for NAT networking...
      ==> default: Checking if box 'hashicorp/precise64' is up to date...
      ==> default: Setting the name of the VM: vagrant_default_1485567897150_51937
      ==> default: Clearing any previously set network interfaces...
      ==> default: Preparing network interfaces based on configuration...
          default: Adapter 1: nat
      ==> default: Forwarding ports...
          default: 22 (guest) => 2222 (host) (adapter 1)
      ==> default: Booting VM...
      ==> default: Waiting for machine to boot. This may take a few minutes...
          default: SSH address: 127.0.0.1:2222
          default: SSH username: vagrant
          default: SSH auth method: private key
          default:
          default: Vagrant insecure key detected. Vagrant will automatically replace
          default: this with a newly generated keypair for better security.
          default:
          default: Inserting generated public key within guest...
          default: Removing insecure key from the guest if it's present...
          default: Key inserted! Disconnecting and reconnecting using new SSH key...
      ==> default: Machine booted and ready!
      ==> default: Checking for guest additions in VM...
          default: The guest additions on this VM do not match the installed version of
          default: VirtualBox! In most cases this is fine, but in rare cases it can
          default: prevent things such as shared folders from working properly. If you see
          default: shared folder errors, please make sure the guest additions within the
          default: virtual machine match the version of VirtualBox you have installed on
          default: your host and reload your VM.
          default:
          default: Guest Additions Version: 4.2.0
          default: VirtualBox Version: 5.1
      ==> default: Mounting shared folders...
          default: /vagrant => C:/Users/marbug/cpp/marbug/vagrant

Now run

    vagrant ssh

to SSH into this machine.

If VM is not needed then sign out from SSH and run:

    vagrant destroy

to terminate it. Or just stop it by:

    vagrant halt

[next page - Project setup](docs/project-setup.md)
