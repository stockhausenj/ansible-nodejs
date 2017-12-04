# Ansible Role: Windows Node.js

Installs Node.js on Windows.

## Requirements

Requires the following to be executed in Powershell on the target machine(s):
```
> Set-ExecutionPolicy RemoteSigned
```
Download and execute this Powershell script: [ConfigureRemotingForAnsible.ps1](https://github.com/ansible/ansible/blob/devel/examples/scripts/ConfigureRemotingForAnsible.ps1)

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):
```
nodejs_version: "8.9.1"
npm_registries: []
npm_pkgs: []
```

## Dependencies

None.

## Example Playbook
```
$ ansible-galaxy install stockhausenj.ansible_win_nodejs
$ ansible-playbook -i inventory.yaml setup-nodejs.yaml -u admin --ask-pass
```
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
        npm_registries: ["@myrepo:registry=http://localhost:1234/"]
        npm_pkgs: ["express","@myrepo/just.for.fun@latest"]
```
## License

MIT
