Attach
======

Manage devices (HDD, LVOL, whatever) attachment

Requirements
------------

N/A

Role Variables
--------------

See Example Playbook for variable defs, but globally a list like:

```
attach__vols:
  - name: <Human readable attachment name> # ex: "My music"
    src: <device path> # ex: "/dev/vdb1"
    path: <mount point> # ex: "/var/lib/music"
    fstype: <filesystem> # ex: ext4
    options: <mount_options> # ex: "rw,relatime"
    state: <mounting status> # ex: mounted (or absent)
```

Dependencies
------------

N/A

Example Playbook
----------------

Setting up an attachment to a machine. Use it on a playbook with:

```
- hosts: all
  name: Attach
  roles:
    - role: attach
```

Using this kind of declarations in group_vars file:

```
attach__install: True
attach__configure: True

attach__vols:
  - name: "Music volume"
    src: "/dev/xvdb1"
    path: "/var/lib/music"
    fstype: ext4
    options: "rw,relatime"
    state: mounted
  - name: "Film volume"
    src: "/dev/xvdc1"
    path: "/var/lib/film"
    fstype: ext4
    options: "rw,relatime"
    state: mounted
```

License
-------

GPL v3

Author Information
------------------

François TOURDE
