# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "box-cutter/ubuntu1404-desktop"

  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    # update
    sudo apt-get update

    # install build-essential, git, vim and curl
    sudo apt-get install -y build-essential git vim gitk wget nano
	
	# install p4merge
	wget http://cdist2.perforce.com/perforce/r15.2/bin.linux26x86_64/p4v.tgz
	tar zxvf p4v.tgz
	sudo mv p4v-* /opt/p4v
	sudo ln -s /opt/p4v/bin/p4merge /usr/local/bin/p4merge
	
	# configure git
	git config --global core.editor nano
	git config --global alias.l "log --decorate --oneline --graph"
	git config --global alias.st status
	git config --global alias.ci commit
	git config --global merge.keepBackup false
	git config --global merge.tool p4merge
	git config --global mergetool.prompt false
	git config --global mergetool.p4merge.cmd 'p4merge "$BASE" "$LOCAL" "$REMOTE" "$MERGED"'
	git config --global mergetool.p4merge.keepTemporaries false
	git config --global mergetool.p4merge.trustExitCode false
	git config --global mergetool.p4merge.keepBackup false
	git config --global diff.tool p4merge
	git config --global difftool.prompt false
	git config --global difftool.p4merge.cmd 'p4merge "$LOCAL" "$REMOTE"'
	git config --global difftool.p4merge.keepTemporaries false
	git config --global difftool.p4merge.trustExitCode false
	git config --global difftool.p4merge.keepBackup false
	
  SHELL
end
