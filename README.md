# podman_vagrant_libvirt_ansible

Vagrant-libvirt setup that creates a VM and installs [Podman](podman.io) on it.

If your host has a file `~/.config/containers/auth.json`, this will be copied
into the VM. Same holds true for the ``~/.config/containers/registries.conf`
file.

Default OS is Fedora 40, but that can be changed in the Vagrantfile.
Please be aware, that this might break the Ansible provisioning. Also, using
other operating systems might give you an older version of podman, e.g.
AlmaLinux9/RockyLinux9/RHEL9 have Podman 4.9.

## Vagrant

1. You need `vagrant`, obviously. And `git`. And Ansible...
1. Fetch the box, per default this is `fedora/40-cloud-base`, using
   `vagrant box add fedora/40-cloud-base`.
1. Make sure the git submodules are fully working by issuing
   `git submodule init && git submodule update`
1. Run `vagrant up`
1. Log into the VM using `vagrant ssh` and run a podman command:

   ```
   podman container ls -a
   ```

1. Party!

## Cleaning up

The VM can be torn down after playing around using `vagrant destroy`.

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
