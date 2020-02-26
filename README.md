# packer-elixir-phoenix-ubuntu

Creates virtualbox and vmware boxes for Elixir and Phoenix development based on Ubuntu 18.04.4 (Bionic Beaver).

Based on Jeff Geerling's [packer-ubuntu-1404](https://github.com/geerlingguy/packer-ubuntu-1404).
Based on Percy Grunwald's [packer-elixir-phoenix-ubuntu-trusty64][https://github.com/percygrunwald/packer-elixir-phoenix-ubuntu-trusty64]

**Current Ubuntu Version Used**: 18.04.4

## Installed software

All the software required for Phoenix development.

* Erlang 22.2
* Elixir 1.10
    * Hex (latest)
    * Rebar (latest)
    * Phoenix (latest)
* PostgreSQL 12.2 (user: postgres, password: postgres)
* Node.js 12.16.1

Generates two Vagrant box files, for:

  - VirtualBox
  - VMware

The example can be modified to use more Ansible roles, plays, and included playbooks to fully configure (or partially) configure a box file suitable for deployment for development environments.

## Requirements

The following software must be installed/present on your local machine before you can use Packer to build the Vagrant box file:

  - [Packer](http://www.packer.io/)
  - [Vagrant](http://vagrantup.com/)
  - [Ansible](http://docs.ansible.com/intro_installation.html)
  - [VirtualBox](https://www.virtualbox.org/) (if you want to build the VirtualBox box)
  - [VMware Fusion](http://www.vmware.com/products/fusion/) (or Workstation - if you want to build the VMware box)

## Usage

Make sure all the required software (listed above) is installed, then cd to the directory containing this README.md file, and run:

    $ packer build elixir-phoenix-ubuntu-bionic64.json

After a few minutes, Packer should tell you the box was generated successfully.

If you want to only build a box for one of the supported virtualization platforms (e.g. only build the VMware box), add `--only=vmware-iso` to the `packer build` command:

    $ packer build --only=virtualbox-iso elixir-phoenix-ubuntu-bionic64.json
    $ packer build --only=vmware-iso elixir-phoenix-ubuntu-bionic64.json    
