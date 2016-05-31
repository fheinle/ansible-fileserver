# ansible-fileserver
Samba fileserver

## Description

Installs Samba and ``cryptsetup`` for LUKS encryption. 

## Installation

Clone this repo to your roles directory:

    mkdir roles
    git clone git@github.com:fheinle/ansible-fileserver.git

## Configuration

Pass ``samba_shares`` as a list of dictionaries to the role:

    samba_shares:
      - {'name': 'Video', 'path':'/media/video'}
      - {'name': 'dev', 'path':'/media/dev'}
      - {'name': 'Backups', 'path':'/media/backups'}

Pass ``samba_users`` as a list of dictionaries to the role:

    samba_users:
      - {'name': 'admin', 'password':'demo'}
      - {'name': 'user', 'password':demo'}

You should really use [Ansible's vault](http://docs.ansible.com/ansible/playbooks_vault.html) to keep your credentials safe.

## Usage

This creates both system and samba users prefixed with ``samba-``, i.e. ``admin`` in config becomes ``samba-admin`` to avoid name conflicts.
