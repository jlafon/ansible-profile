===============
ansible-profile
===============

An Ansible plugin for timing tasks.


Usage in Ansible 2.0
^^^^^^^^^^^^^^^^^^^^

This plugin is included in Ansible 2.0, and can be enabled by adding this line to `ansible.cfg`

.. code-block:: bash

    callback_whitelist = profile_tasks

Usage in Ansible 1.x
^^^^^^^^^^^^^^^^^^^^

Make a directory called `callback_plugins` next to your playbook and put `profile_tasks.py` inside of it.

.. code-block:: bash

    mkdir callback_plugins
    cd callback_plugins
    wget https://raw.githubusercontent.com/jlafon/ansible-profile/master/callback_plugins/profile_tasks.py

Now, run your playbook just as you normally would!

.. code-block:: bash

   ansible <args here>
   <normal output here>
   PLAY RECAP ******************************************************************** 
   really slow task  | Download project packages-----------------------------11.61s
   security | Really slow security policies-----------------------------------7.03s
   common-base | Install core system dependencies-----------------------------3.62s
   common | Install pip-------------------------------------------------------3.60s
   common | Install boto------------------------------------------------------3.57s
   nginx | Install nginx------------------------------------------------------3.41s
   serf | Install system dependencies-----------------------------------------3.38s
   duo_security | Install Duo Unix SSH Integration----------------------------3.37s
   loggly | Install TLS version-----------------------------------------------3.36s

If for some reason you want to disable this temporarily, set the
environment variable `ANSIBLE_PROFILE_DISABLE` to any value (even an
empty string).
