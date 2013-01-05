Vagrant::Config.run do |config|
  config.vm.box = "precise32"
  config.vm.box_url = "http://files.vagrantup.com/precise32.box"
  #config.vm.network :hostonly, "33.33.33.10"
  config.vm.forward_port 3000,3000
 
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks"]
    chef.add_recipe "apt"
    chef.add_recipe "build-essential"
    chef.add_recipe "rvm::vagrant"
    chef.add_recipe "rvm::system"
		chef.json = {
		'rvm' => {
			'rubies'       => ['1.9.3-p327'],
			'default_ruby' => '1.9.3-p327',
			'global_gems'  => [
				{'name'    => 'bundler'},
				{'name'    => 'rake', 'version' => '0.9.2'},
				{'name'    => 'rails'}
			],
#			'vagrant' => {
#				'system_chef_solo' => '/opt/vagrant_ruby/bin/chef-solo'
#			}
		}
	}
    chef.add_recipe "git"
  end
  
  # TODO: Workaround for user permission (installing gems..etc). Should be fixed properly
  config.vm.provision :shell, :inline => 'chown -R vagrant:vagrant /usr/local/rvm/'
end