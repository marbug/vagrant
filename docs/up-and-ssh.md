# Up and SSH #

    vagrant up

In less than a minute, this command will finish and you will have a virtual machine running Ubuntu.

    vagrant ssh

This command will drop you into a full-fledged SSH session.

Be careful about rm -rf /, since Vagrant shares a directory at /vagrant with the directory on the host containing your Vagrantfile, and this can delete all those files.
