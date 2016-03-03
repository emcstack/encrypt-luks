Encrypt-LUKs
============

Encrypt disks with LUKs

Requirements
------------


Role Variables
--------------

| Name | Type | Required | Default | Description
|--- |--- |--- |--- |---
| hdds | list | yes | None | list of disks or partitions to encrypt (partitions must exist)
| encrypt_key_size | int | 512 | number of bits for the key
| encrypt_key_folder | string | /var/tmp | Default directory to store the key
| key_file | string | luk-keyfile | Default name of the key
| use_same_encrypt_key | boolean | true | True to encrypt all disks with the same luk key


Dependencies
------------


Example Playbook
----------------

```

- hosts:
  - nc-9
  roles:
  - encrypt-luks
  vars:
  - hdds:
    - /dev/sdb
    - /dev/sdc1

```

```

- hosts:
  - nc-9
  roles:
  - encrypt-luks
  vars:
  - encrypt_key_size: 2048
  - hdds:
    - /dev/sdb
    - /dev/sdc1

```



License
-------

GPLv3

Author Information
------------------

John Preston [John Mille]
