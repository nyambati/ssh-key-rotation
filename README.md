
# ssh Key Rotation

[![Build Status](https://travis-ci.org/nyambati/ssh-key-rotation.svg?branch=master)](https://travis-ci.org/nyambati/ssh-key-rotation)
=========

This is ansible role that enables you to rotate ssh keys on your remote servers

Requirements
------------

This modules depeds on ansible 2.2.X

Role Variables
--------------

For this role to work it requires the following variables:

```yaml
# Removes the existing public keys when set to yes
is_exclusive: no

should_manage_dir: no

# The location to where the authorized_keys file existing
# .shh/authorized_keys is the deafult value
authorized_keys_path: .ssh/authorized_keys

# This is the passphrase used to encrypt your new ssh key
passphrase: 83g!8bfu5M5yy84x

# The number of bits you want to assign the key
ssh_key_bits: 2048

# The comment that accompanies the key
ssh_key_comment: domain@example.com

# The user of the host keys are added to
ssh_host_user: ubuntu

# The location to store the keys to. (warning it should not begin with /)
ssh_key_path: ".ssh/new-ssh-key"

# if you already have generated you keys add the following variables.

# Set to true by default
generate_new_key: True
ssh_connection_key: "some key"

# add this if you want to add deployment key for your server,
ssh_deployment_key: "deployment key"

```

The above variables and values are the default inputs to this role. You can check the default folder. Make sure you upate them with your own.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
---
- hosts: all
  remote_user: vagrant
  vars:
    host_user: vagrant
    ssh_key_path: .ssh/some-new-secure
  roles:
    - ssh-key-rotation


```

License
-------
MIT License

Copyright (c) 2017 Nyambati Thomas <thomasnyambati@gmal.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Author Information
------------------
Thomas Nyambati <thomasnyambati@gmail.com>

