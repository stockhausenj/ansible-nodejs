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
```
- hosts: all
  vars:
    ansible_port: 5986
    ansible_connection: winrm
    ansible_winrm_server_cert_validation: ignore
  tasks:
  roles:
    - include_role:
        name: stockhausenj.ansible_win_nodejs
      vars:
        nodejs_version: "8.9.1"
        npm_repos: ["@myrepo:registry=http://localhost:1234/"]
        npm_pkgs: ["express","@myrepo/just.for.fun@latest"]
```
## License

MIT
