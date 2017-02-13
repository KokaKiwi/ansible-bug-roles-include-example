
## System informations

```
Operating System: Arch Linux
Ansible version:
    ansible 2.2.1.0
      config file = /etc/ansible/ansible.cfg
      configured module search path = Default w/o overrides
```

## Run it

```
$ ansible-playbook -vv test.yml
statically included: /tmp/ansible/roles/test/tasks/subdir/a.yml

PLAYBOOK: test.yml *************************************************************
1 plays in test.yml

PLAY [localhost] ***************************************************************

TASK [setup] *******************************************************************
ok: [localhost]

TASK [test : include] **********************************************************
task path: /tmp/ansible/roles/test/tasks/subdir/a.yml:2
fatal: [localhost]: FAILED! => {"failed": true, "reason": "the file_name '/tmp/ansible/otherdir/b.yml' does not exist, or is not readable"}
fatal: [localhost]: FAILED! => {"failed": true, "reason": "the file_name '/tmp/ansible/otherdir/b.yml' does not exist, or is not readable"}
fatal: [localhost]: FAILED! => {"failed": true, "reason": "the file_name '/tmp/ansible/otherdir/b.yml' does not exist, or is not readable"}
        to retry, use: --limit @/tmp/ansible/test.retry

PLAY RECAP *********************************************************************
localhost                  : ok=1    changed=0    unreachable=0    failed=3
```
