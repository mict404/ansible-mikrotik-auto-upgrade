Run this script one by one, by the way this repo just a self note for me :)

#Clear Log
ansible all -m raw -a ':put "Clear Log";quit' -u admin -k
#Download New RouterOS Package
ansible all -m raw -a 'system package update set channel=current;system package update check-for-updates;system package update download;delay 1;quit' -u admin -k
#System Reboot
ansible all -m raw -a ':put "Reboot by Ansible";:execute {/system reboot;delay 1;quit}' -u admin -k
#Crosscheck, do this after few minutes
ansible all -m raw -a 'local version value=[/system resource get version];local id value=[/system identity get name];:put "$id was Upgraded with RouterOS $version";quit' -u admin -k
#You're done :)
