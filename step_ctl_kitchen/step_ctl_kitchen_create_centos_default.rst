.. This is an included how-to. 


To create the default |centos| instance, run the following:

.. code-block:: bash

   $ kitchen create default-centos-65

|centos| is downloaded the first time this command is run, after which |vagrant| is started. The output of the command is similar to:

.. code-block:: bash

   -----> Starting Kitchen (v1.3.1)
   -----> Creating <default-centos-65>...
          Bringing machine 'default' up with 'virtualbox' provider...
          ==> default: Box 'opscode-centos-6.5' could not be found. Attempting to find and install...
              default: Box Provider: virtualbox
              default: Box Version: >= 0
          ==> default: Adding box 'opscode-centos-6.5' (v0) for provider: virtualbox
              default: Downloading: https://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5_chef-provisionerless.box
          ==> default: Successfully added box 'opscode-centos-6.5' (v0) for 'virtualbox'!
          ==> default: Importing base box 'opscode-centos-6.5'...
          ==> default: Matching MAC address for NAT networking...
          ==> default: Setting the name of the VM: default-centos-65_default_1403650129063_53517
          ==> default: Clearing any previously set network interfaces...
          ==> default: Preparing network interfaces based on configuration...
              default: Adapter 1: nat
          ==> default: Forwarding ports...
              default: 22 => 2222 (adapter 1)
          ==> default: Booting VM...
          ==> default: Waiting for machine to boot. This may take a few minutes...
              default: SSH address: 127.0.0.1:2222
              default: SSH username: vagrant
              default: SSH auth method: private key
              default: Warning: Connection timeout. Retrying...
          ==> default: Machine booted and ready!
          ==> default: Checking for guest additions in VM...
          ==> default: Setting hostname...
          ==> default: Machine not provisioning because `--no-provision` is specified.
          Vagrant instance <default-centos-65> created.
          Finished creating <default-centos-65> (11m29.44s).
   -----> Kitchen is finished. (11m29.76s)
