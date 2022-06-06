# STEP 1
========================================
$ apt-get install wget
$ wget https://packages.chef.io/files/stable/chef-workstation/22.6.973/ubuntu/20.04/chef-workstation_22.6.973-1_amd64.deb
$ sudo apt install ./chef-workstation_22.6.973-1_amd64.deb

# Check chef is installed or now
$ chef
$ chef version

# STEP 2 
========================================
Modify file with license_key - https://github.com/technical-job-support/tony/blob/master/cookbooks/newrelic-infra/attributes/default.rb

conf['license_key'] = nil

# STEP 3
========================================
$ git clone https://github.com/technical-job-support/tony
$ cd tony
$ chef-client --local-mode --runlist 'recipe[newrelic-infra]'
