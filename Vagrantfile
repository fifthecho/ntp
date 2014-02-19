# -*- mode: ruby -*-
# vi: set ft=ruby :
cookbook = 'ntp'

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  cookbook = 'ntp'
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "base"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  # config.vm.box_url = "http://domain.com/path/to/above.box"

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network :forwarded_port, guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network :private_network, ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network :public_network

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
  # config.vm.provider :virtualbox do |vb|
  #   # Don't boot with headless mode
  #   vb.gui = true
  #
  #   # Use VBoxManage to customize the VM. For example to change memory:
  #   vb.customize ["modifyvm", :id, "--memory", "1024"]
  # end
  #
  # View the documentation for the provider you're using for more
  # information on available options.

  # Enable provisioning with Puppet stand alone.  Puppet manifests
  # are contained in a directory path relative to this Vagrantfile.
  # You will need to create the manifests directory and a manifest in
  # the file base.pp in the manifests_path directory.
  #
  # An example Puppet manifest to provision the message of the day:
  #
  # # group { "puppet":
  # #   ensure => "present",
  # # }
  # #
  # # File { owner => 0, group => 0, mode => 0644 }
  # #
  # # file { '/etc/motd':
  # #   content => "Welcome to your Vagrant-built virtual machine!
  # #               Managed by Puppet.\n"
  # # }
  #
  # config.vm.provision :puppet do |puppet|
  #   puppet.manifests_path = "manifests"
  #   puppet.manifest_file  = "site.pp"
  # end

  # Enable provisioning with chef solo, specifying a cookbooks path, roles
  # path, and data_bags path (all relative to this Vagrantfile), and adding
  # some recipes and/or roles.
  #
  # config.vm.provision :chef_solo do |chef|
  #   chef.cookbooks_path = "../my-recipes/cookbooks"
  #   chef.roles_path = "../my-recipes/roles"
  #   chef.data_bags_path = "../my-recipes/data_bags"
  #   chef.add_recipe "mysql"
  #   chef.add_role "web"
  #
  #   # You may also specify custom JSON attributes:
  #   chef.json = { :mysql_password => "foo" }
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
  # config.vm.provision :chef_client do |chef|
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


  config.omnibus.chef_version = :latest

  config.vm.define :centos6 do |centos6|
    centos6.vm.box      = 'opscode-centos-6.5'
    centos6.vm.box_url  = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5_chef-provisionerless.box'
    centos6.vm.hostname = "#{cookbook}-centos-6"
  end

  config.vm.define :centos5 do |centos5|
    centos5.vm.box      = 'opscode-centos-5.10'
    centos5.vm.box_url  = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-5.10_chef-provisionerless.box'
    centos5.vm.hostname = "#{cookbook}-centos-5"
  end
  
  config.vm.define :opensuse12 do |osuse12|
    osuse12.vm.box	= 'opensuse-12.3'
    osuse12.vm.box_url	= 'http://sourceforge.net/projects/opensusevagrant/files/12.3/opensuse-12.3-64.box/download'
    osuse12.vm.hostname	= 'ntp-opensuse'
  end
  
  config.vm.define :sles11 do |sles11|
    sles11.vm.box	= 'sles-11sp1'
    sles11.vm.box_url	= 'http://puppet-vagrant-boxes.puppetlabs.com/sles-11sp1-x64-vbox4210-nocm.box'
    sles11.vm.hostname	= 'ntp-sles'
  end

  config.vm.define :debian7 do |debian7|
    debian7.vm.box      = 'opscode-debian-7.2.0'
    debian7.vm.box_url  = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_debian-7.2.0_chef-provisionerless.box'
    debian7.vm.hostname = "#{cookbook}-debian-7"
  end

  config.vm.define :debian6 do |debian6|
    debian6.vm.box      = 'opscode-debian-6.0.8'
    debian6.vm.box_url  = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_debian-6.0.8_chef-provisionerless.box'
    debian6.vm.hostname = "#{cookbook}-debian-6"
  end

  config.vm.define :freebsd9 do |freebsd9|
    freebsd9.vm.box      = 'opscode-freebsd-9.2'
    freebsd9.vm.box_url  = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_freebsd-9.2_chef-provisionerless.box'
    freebsd9.vm.hostname = "#{cookbook}-freebsd-9"
  end

  config.vm.define :ubuntu1204 do |ubuntu1204|
    ubuntu1204.vm.box      = 'opscode-ubuntu-12.04'
    ubuntu1204.vm.box_url  = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-12.04_chef-provisionerless.box'
    ubuntu1204.vm.hostname = "#{cookbook}-ubuntu-1204"
  end

  config.vm.define :ubuntu1004 do |ubuntu1004|
    ubuntu1004.vm.box      = 'opscode-ubuntu-10.04'
    ubuntu1004.vm.box_url  = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-10.04_chef-provisionerless.box'
    ubuntu1004.vm.hostname = "#{cookbook}-ubuntu-1004"
  end

  config.vm.provision :chef_solo do |chef|
    chef.log_level = :debug
    chef.add_recipe("apt")
    chef.json = {
      "ntp" => {
        "servers" => ["dc1.fifthecho.com", "pool.ntp.org"]
      }
    }
    chef.run_list = [
      "recipe[apt]",
      "recipe[#{cookbook}]"
    ]
  end

end
