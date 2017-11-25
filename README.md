# Ansible Role: Windows Node.js

Installs Node.js on RHEL/CentOS or Debian/Ubuntu.

## Requirements

Requires the following to be executed in Powershell on the target machine(s):
```
Set-ExecutionPolicy RemoteSigned
https://github.com/ansible/ansible/blob/devel/examples/scripts/ConfigureRemotingForAnsible.ps1
```

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):
```
nodejs_version: "8.9.1"
npm_repos: [""]
```

## Dependencies

None.

## Example Playbook

- hosts: all
  roles:
    - role

## License

MIT
