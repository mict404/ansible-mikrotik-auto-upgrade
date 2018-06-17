{
/system identity set name="ansible-mikrotik-auto-upgrade"
:put ("Hello World, welcome to ".[/system identity get name]." Repository")
}

Run ansible-mikrotik-auto-upgrade.sh one by one (each new command are separated by new line :D) don't run with:
"chmod +x ansible-mikrotik-auto-upgrade.sh && ./ansible-mikrotik-auto-upgrade.sh"
and by the way this repo just a self note for me :) and you also need some improvement and adjustment if you want to deploy in your network
