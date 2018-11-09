# Ansible polaybook for configurating nginx templates
## Three action types
```
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook manage_template.yml -e action=add -e domain=test.com -e cert=/tmp/test.crt -e key=/tmp/test.pem

ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook manage_template.yml -e action=remove -e domain=test.com

ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook manage_template.yml -e action=refresh_all
```
## Nginx dir structure example
```
/opt/nginx/records/test.com - template
/opt/nginx/ssl/test.com/test.crt
                       /test.pem
```
## Main variables
```
conf_path: "/tmp/nginx/records" - path to all records configs
ssl_path: "/tmp/nginx/ssl" - path to all cert/key pairs
records_file: "/tmp/all" - path to records source file for refresh action
```