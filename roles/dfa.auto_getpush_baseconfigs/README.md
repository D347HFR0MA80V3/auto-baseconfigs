auto_getpush_baseconfigs
=========

Tired of looking for Splunk PS Base Configs. Role automates the get and post of them to a private repo of your choosing. The destination repo should be private... These configs are in public facing drive but may or may not be "officially" supported. To save PS and yourself the headache, stash them somewhere private. 

Requirements
------------

- GitHub or other SCM account credentials
- Working Gdrive file ID's for both the base and cluster base config folders
- Working knowledge of how to vault variable values in Ansible

Role Variables
--------------

Found in role defaults/main.yml

```
splunk_gdrive_baseconfigs_fileID: 'replace_with_fileID_strings'
splunk_gdrive_clusterconfigs_fileID: 'replace_with_fileID_strings'
source_control_email: someemailaddress@foo.com
source_control_url: https://github.com/<username>
source_control_username: username
source_control_password: password
```

Dependencies
------------

- Docker... this project is baked into the docker hub image deathfromabove/splunk_config_getter
- gdrive-org gdrive utility for linux... https://github.com/gdrive-org/gdrive ... also baked into the image, but the automation utilises this to simplify the collection of the folder contents

Launch Playbook
----------------

```
- hosts: localhost
  roles:
  - dfa.auto_getpush_baseconfigs
```

License
-------

MIT

Author Information
------------------

Lee G || D347HFR0MA80V3 || CAS Cyber Security || Shad0w Synd1cate Contributor
