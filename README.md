# egeneralov.k3s

Install k3s cluster.

## Disclamer

Not for production use, testing purposes only.

## Requirements

Debian-based system with systemd.

## Role Variables

- **k3s_version**: `0.4.0`
- **k3s_cidr**: `10.43.0.0/16`
- **k3s_master_allow_agent**: `true`
- **k3s_install_helm**: `true`
- **k3s_install_local_provisioner**: `true`
- **k3s_helm_version**: `2.13.1`

## Example Inventory

    [all]
    k3s-master-0 ansible_host=10.199.25.181
    k3s-node-0 ansible_host=10.199.25.182
    
    [k3s:children]
    k3s-master
    k3s-node
    
    [k3s-master]
    k3s-master-0
    
    [k3s-node]
    k3s-node-0


## Example Playbook

    - hosts: k3s
      remote_user: root
      roles:
        - egeneralov.k3s

## License

MIT

## Author Information

Eduard Generalov <eduard@generalov.net>
