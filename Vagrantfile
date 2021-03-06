# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|


  #
  # Centos
  #
  config.vm.define "centos-5.5" do |v|
    v.vm.box = "hansode/centos-5.5-x86_64"
    v.vm.box_url = "https://vagrantcloud.com/hansode/boxes/centos-5.5-x86_64"
    v.vm.hostname = "boundary-plugin-dev-centos-5-5"
    v.vm.provision "shell", :path => "centos.sh"
    v.vm.post_up_message = "TO LOGIN: vagrant ssh centos-5.5"
  end

  config.vm.define "centos-5.8" do |v|
    v.vm.box = "altenwald/centos-5.8-puppet"
    v.vm.box_url = "https://vagrantcloud.com/altenwald/boxes/centos-5.8-puppet"
    v.vm.hostname = "boundary-plugin-dev-centos-5-8"
    v.vm.provision "shell", :path => "centos.sh"
    v.vm.post_up_message = "TO LOGIN: vagrant ssh centos-5.8"
  end

  config.vm.define "centos-5.10" do |v|
    v.vm.box = "chef/centos-5.10"
    v.vm.box_url = "https://vagrantcloud.com/chef/boxes/centos-5.10"
    v.vm.hostname = "boundary-plugin-dev-centos-5-10"
    v.vm.provision "shell", :path => "centos.sh"
    v.vm.post_up_message = "TO LOGIN: vagrant ssh centos-5.10"
  end

  config.vm.define "centos-6.5" do |v|
    v.vm.box = "chef/centos-6.5"
    v.vm.box_url = "https://vagrantcloud.com/chef/centos-6.5"
    v.vm.hostname = "boundary-plugin-dev-centos-6-5"
    v.vm.provision "shell", :path => "centos.sh"
    v.vm.post_up_message = "TO LOGIN: vagrant ssh centos-6.5"
  end

  config.vm.define "centos-7.0" do |v|
    v.vm.box = "chef/centos-7.0"
    v.vm.box_url = "https://vagrantcloud.com/chef/centos-7.0"
    v.vm.hostname = "boundary-plugin-dev-centos-7-0"
    v.vm.provision "shell", :path => "centos.sh"
    v.vm.post_up_message = "TO LOGIN: vagrant ssh centos-7.0"
  end

  #
  # Debian
  #
  config.vm.define "debian-7.6" do |v|
    v.vm.box = "chef/debian-7.6"
    v.vm.box_url = "https://vagrantcloud.com/chef/boxes/debian-7.6"
    v.vm.provision "shell", :path => "debian.sh"
  end

  #
  # RedHat
  #
  config.vm.define "fedora-19" do |v|
    v.vm.box = "chef/fedora-19"
    v.vm.box_url = "https://vagrantcloud.com/chef/boxes/fedora-19"
    v.vm.provision "shell", :path => "fedora.sh"
  end

  config.vm.define "fedora-20" do |v|
    v.vm.box = "chef/fedora-20"
    v.vm.box_url = "https://vagrantcloud.com/chef/boxes/fedora-20"
    v.vm.provision "shell", :path => "fedora.sh"
  end

  #
  # Mac OS X
  #
  config.vm.define "mac" do |v|
    v.vm.box = "mac-osx-10.9"
    v.vm.box_url = "https://vagrantcloud.com/stopiccot/boxes/osx-10.9"
    v.vm.provision "shell", :path => "macosx.sh"
  end

  #
  # Ubuntu
  #
  config.vm.define "ubuntu-12.04" do |v|
    v.vm.box = "hashicorp/precise64"
    v.vm.hostname = "ubuntu-12.04"
    v.vm.provision "shell", :path => "ubuntu.sh"
    v.vm.post_up_message = "Run vagrant ssh ubuntu-12.04 to login"
  end

  config.vm.define "ubuntu-12.10" do |v|
    v.vm.box = "chef/ubuntu-12.10"
    v.vm.hostname = "ubuntu-12.10"
    v.vm.provision "shell", :path => "ubuntu.sh"
    v.vm.post_up_message = "Run vagrant ssh ubuntu-12.10 to login"
  end

  config.vm.define "ubuntu-14.04" do |v|
    v.vm.box = "ubuntu/trusty64"
    v.vm.hostname = "ubuntu-14.04"
    v.vm.provision "shell", :path => "ubuntu.sh"
    v.vm.post_up_message = "Run vagrant ssh ubuntu-14.04 to login"
  end

  #
  # Windows
  #
  config.vm.define "windows-7" do |v|
    v.vm.box = "win_7_x64_eng"
    # Name shortened due to limitation of Windows
    v.vm.hostname = "plugin-win-7"
    v.vm.communicator = "winrm"
    v.vm.network "forwarded_port", guest: 3389, host: 3389
  end

  config.vm.define "windows-2012-standard" do |v|
    v.vm.box = "opentable/win-2012-standard-amd64-nocm"
    # Name shortened due to limitation of Windows
    v.vm.hostname = "p-win-2012-stan"
    v.vm.communicator = "winrm"
    v.vm.network "forwarded_port", guest: 3389, host: 3389
  end

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # If true, then any SSH connections made will enable agent forwarding.
  # Default value: false
  # config.ssh.forward_agent = true

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Don't boot with headless mode
  #   vb.gui = true
  #
  #   # Use VBoxManage to customize the VM. For example to change memory:
  #   vb.customize ["modifyvm", :id, "--memory", "1024"]
  # end
  #
  # View the documentation for the provider you're using for more
  # information on available options.

  # Enable provisioning with CFEngine. CFEngine Community packages are
  # automatically installed. For example, configure the host as a
  # policy server and optionally a policy file to run:
  #
  # config.vm.provision "cfengine" do |cf|
  #   cf.am_policy_hub = true
  #   # cf.run_file = "motd.cf"
  # end
  #
  # You can also configure and bootstrap a client to an existing
  # policy server:
  #
  # config.vm.provision "cfengine" do |cf|
  #   cf.policy_server_address = "10.0.2.15"
  # end

  # Enable provisioning with Puppet stand alone.  Puppet manifests
  # are contained in a directory path relative to this Vagrantfile.
  # You will need to create the manifests directory and a manifest in
  # the file default.pp in the manifests_path directory.
  #
  # config.vm.provision "puppet" do |puppet|
  #   puppet.manifests_path = "manifests"
  #   puppet.manifest_file  = "site.pp"
  # end

  # Enable provisioning with chef solo, specifying a cookbooks path, roles
  # path, and data_bags path (all relative to this Vagrantfile), and adding
  # some recipes and/or roles.
  #
  # config.vm.provision "chef_solo" do |chef|
  #   chef.cookbooks_path = "../my-recipes/cookbooks"
  #   chef.roles_path = "../my-recipes/roles"
  #   chef.data_bags_path = "../my-recipes/data_bags"
  #   chef.add_recipe "mysql"
  #   chef.add_role "web"
  #
  #   # You may also specify custom JSON attributes:
  #   chef.json = { mysql_password: "foo" }
  # end

  # Enable provisioning with chef server, specifying the chef server URL,
  # and the path to the validation key (relative to this Vagrantfile).
  #
  # The Opscode Platform uses HTTPS. Substitute your organization for
  # ORGNAME in the URL and validation key.
  #
  # If you have your own Chef Server, use the appropriate URL, which may be
  # HTTP instead of HTTPS depending on your configuration. Also change the
  # validation key to validation.pem.
  #
  # config.vm.provision "chef_client" do |chef|
  #   chef.chef_server_url = "https://api.opscode.com/organizations/ORGNAME"
  #   chef.validation_key_path = "ORGNAME-validator.pem"
  # end
  #
  # If you're using the Opscode platform, your validator client is
  # ORGNAME-validator, replacing ORGNAME with your organization name.
  #
  # If you have your own Chef Server, the default validation client name is
  # chef-validator, unless you changed the configuration.
  #
  #   chef.validation_client_name = "ORGNAME-validator"
end
