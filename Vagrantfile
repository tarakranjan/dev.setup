# -*- mode: ruby -*-
# vi: set ft=ruby :

# Load in custom vagrant settings
require "yaml"
settings = File.file?("vagrant.yml") ? YAML.load_file("vagrant.yml") : {}
puts "== Using Settings From vagrant.yml =="
puts settings.inspect

VAGRANTFILE_API_VERSION = "2".freeze
$box = settings["vagrant-name"]
$ip = settings["network"]["ip"]
$hostname = settings["network"]["hostname"]


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  ### Work Around to Fix Vagrant Bug in
  # correctly assigning the provided name to the box
  config.vm.define settings["vagrant-name"] do |t|
  end
  config.vm.provider "virtualbox" do |v|
    v.name = $box
    v.memory = 2048
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--usb", "off"]
  end
  ### Workaround Ends ###

  config.vm.box = "minimal/trusty64"
  config.vm.hostname = $hostname
  config.vbguest.auto_update = true

  required_plugins = %w( vagrant-hostsupdater vagrant-vbguest )
  required_plugins.each do |plugin|
    system "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin
  end

  config.vm.network "private_network", ip: $ip
  config.hostsupdater.aliases = [$hostname]

  config.vm.synced_folder "#{ENV['KC_DIR']}/kc-web/src/main/webapp",
                                    "/usr/share/nginx/knowledgecenter",
                                    owner: "root",
                                    group: "root"


  ## Create Control Center as a Vagrant Box
  config.vm.provision "ansible" do |ansible|
     ansible.verbose = "v"
     ansible.playbook       = "provision/vagrant.yml"
     ansible.raw_arguments  = "--user=vagrant"
     ansible.raw_arguments  = "--vault-password-file=./.vault_pass"
  end
end
