# Ansible Examples

Ansible examples ranging from basic tasks to complex string manipulation.

All provided playbooks will run in a local environment.

# Environment

| System  | Version |
|---------|---------|
| MacOS   | 14.4.1) |
| Python  | 3.11    |
| Ansible | 2.9.9   |

# Set up

Create and activate Python 3 virtual environment:

```shell
python3.11 -m venv venv
source venv/bin/activate
```

Update PIP:

```shell
pip install --upgrade pip
```

Install requirements:

```shell
pip install -r requirements.txt
```

# Execution

Ensure that your virtual environment is active and execute an example:

```shell
PLAY [local] ***************************************************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************************************
ok: [localhost]

TASK [Debug some variables.] ***********************************************************************************************************************************************
ok: [localhost] => (item=TestVar) => {
    "ansible_loop_var": "item",
    "item": "TestVar"
}
ok: [localhost] => (item=['list item 1', 'list item 2']) => {
    "ansible_loop_var": "item",
    "item": [
        "list item 1",
        "list item 2"
    ]
}
ok: [localhost] => (item=list item 1+list item 2) => {
    "ansible_loop_var": "item",
    "item": "list item 1+list item 2"
}
ok: [localhost] => (item={'dict_item_a': 'Dict Item A', 'dict_item_b': 'Dict Item B'}) => {
    "ansible_loop_var": "item",
    "item": {
        "dict_item_a": "Dict Item A",
        "dict_item_b": "Dict Item B"
    }
}

PLAY RECAP *****************************************************************************************************************************************************************
localhost                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

# TODO:

- Support for other versions of Ansible.
