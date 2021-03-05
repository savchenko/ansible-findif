# ansible-findif

Given an ip address, returns the interface name that owns that address.

Based on the [prototype](https://github.com/larsks/stackoverflow-example-45659201), all in attempt to answer a [stackoverflow question](https://stackoverflow.com/questions/45659201/).

## Installation

```sh
$ mkdir -pv $HOME/.ansible/plugins/modules/
$ curl --location -s "https://github.com/savchenko/ansible-findif/raw/master/plugins/modules/findif.py" -o $HOME/.ansible/plugins/modules/findif.py
```

Or, better, clone this repository and symlink from it.

## Usage

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

### Example output

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
