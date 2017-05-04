# ansible-cmdb-freebsd-template
html_fancy template to gather extra information from FreeBSD hosts

Extra features:
* Detailed information about the Zpools and its health
* List of zfs volumes and their configuration
* List of running jails
* Ezjail configuration
* Installed packages
* Vulnerable packages
* Vulnerable packaes in the jails

Requeriments:
 * ansible-cmdb from https://github.com/fboender/ansible-cmdb
 * ezjail (the custom facts may crash and you will need to hack the code)

Installing
 * cp html_fancy_freebsd.tpl to lib/ansiblecmdb/data/tpl
 * Upload facts.d to /usr/usr/local/etc/ansible/facts.d/ in your servers


Running
 * Refresh your Ansible cache: ansible all -m setup -a "fact_path=/usr/local/etc/ansible/facts.d" --tree cache
 * Generate the html page from your Ansible project: ansible-cmdb -p collapsed=1 -t html_fancy_freebsd  -f ./cache/ > cmdb.html

