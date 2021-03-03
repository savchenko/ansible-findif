Based on the [prototype](https://github.com/larsks/stackoverflow-example-45659201), all in attempt to answer a [stackoverflow question](https://stackoverflow.com/questions/45659201/).

Given an ip address, returns the interface name that owns that address.

You would use it in a playbook like this:

```yaml
---
- hosts: localhost
  tasks:
    - findif:
        address: '127.0.0.1'
      register: findif

    - debug:
        var: findif
```


Example output:

```
TASK [findif] *********************************************
changed: [localhost]

TASK [debug] **********************************************
ok: [localhost] => {
    "findif": {
        "interface": "lo",
        "changed": true,
        "failed": false
    }
}
```
