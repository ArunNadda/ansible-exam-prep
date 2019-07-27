## Handling Errors
##### Ignore the failed task using "ignore_errors"
```
- name: using ignore_erros
  package:
    name: nopkg
    state: present
  ignore_errors: yes
```

##### Force execute handlers, use force_handlers

```
```  

##### failed_when

##### changed_when



### Ansible blocks and Error handling

##### use block - rescue - always


```
---
- name: playbook name
  hosts: all
  tasks:
    - block:
        - shell:
            cmd: /bin/upgrade_db
    
    - rescue:
        - shell:
            cmd: /bin/create_user

    - always:
        - service:
            name: mysql
            state: restarted
