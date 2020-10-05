ROLE COPY
=========

Get data from one role, setup a new role with that data and a new name.

This plugin will actively refuse to create a role with a name that already exists.

Installation
=======

    $ git clone git@github.com:jaketyo/knife_role_copy.git
    $ mkdir -p ~/.chef/plugins/knife/
    $ cp knife_role_copy/role_copy.rb ~/.chef/plugins/knife/

Usage
=====

Help output:

    $ knife role copy
    USAGE: knife role copy ROLE NEW_ROLE (options)

Example
=======

This example begins with the following role.

    $ knife role show -Fj SOME-ROLE-NAME
    {
      "name": "SOME-ROLE-NAME",
      "description": "Some Role Description",
      "json_class": "Chef::Role",
      "default_attributes": {
        
      },
      "override_attributes": {
        
      },
      "chef_type": "role",
      "run_list": [
        
      ],
      "env_run_lists": {
        
      }
    }

Execute `knife role copy` to copy the role.

    $ knife role copy SOME-ROLE-NAME SOME-ROLE-NAME-2
    # This opens an editor as defined by your $EDITOR environment variable.

After the editor is saved and closed, you can print the new role to inspect the changes.

    $ knife role show -Fj SOME-ROLE-NAME-2
    {
      "name": "SOME-ROLE-NAME-2",
      "description": "Some Role Description (Copy from SOME-ROLE-NAME)",
      "json_class": "Chef::Role",
      "default_attributes": {

      },
      "override_attributes": {

      },
      "chef_type": "role",
      "run_list": [

      ],
      "env_run_lists": {

      }
    }
