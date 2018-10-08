# ansible-mastodon-amznlinux

Ansible construction script of mastodon instance

### AmazonLinux Version

* Amazon Linux 2018.03.0
* Amazon Lightsail ready

### Mastodon Version
* 2.5.0 ready

## SETUP

1. please rewrite group_vars file. `group_vars/production.yml`
2. let try `ansible-playbook -i localhost localhost.yml -vv`
3. start supervisord `nohup /usr/bin/python2.7 /usr/bin/supervisord -n -c /etc/supervisord.conf >/dev/null 2>&1  &`
