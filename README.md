# Git Workshop VM

Vagrantfile for setting up a VM with the following specs:
- Ubuntu 14.04 Desktop
- git
- gitk
- vim
- nano (configured as core.editor in git)
- p4merge (configured as merge.tool and diff.tool in git)

## Setup

0. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
    - This is optional however if missing vagrant will install during first run.
1. Install [vagrant](https://www.vagrantup.com/downloads.html)
2. Clone this repository or simply download the [Vagrantfile](https://raw.githubusercontent.com/infusion-wro/git-workshop-vm/master/Vagrantfile)
3. Open your favorite shell and cd into the directory with the Vagrantfile
4. Run `vagrant up`