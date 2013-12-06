Vagrant::Config.run do |config|
  config.vm.box = "lucid32"
  config.vm.box_url = "http://files.vagrantup.com/lucid32.box"
  config.vm.provision :shell, :path => "bootstrap.sh"

  # Alfresco starts up on port 8080
  config.vm.forward_port 8080, 8080

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "alfresco"
  
    # You may also specify custom JSON attributes:
    # chef.json = { :mysql_password => "foo" }
  end
end
