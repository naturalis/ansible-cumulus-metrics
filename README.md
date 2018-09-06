# Ansible Role: Cumulus monitoring

Used in [network](https://github.com/naturalis/network/) repo.

Runnable with:
```bash
ansible-playbook playbooks/cumulus_provision.yml -i environments/prod
```

This role will install the prometheus node_exporter, setup snmp and configure an external rsyslog server.

Locally (on the switch) the metrics are visible on the endpoint by running:
```bash
curl http://localhost:9100/metrics
```
Or by running it against a switch from the oob-mgmt-server:
```bash
curl netdw2-spine-a:9100/metrics
```

## Requirements

None.

## Role Variables

Available variables are listed below:
```bash
node_exporter_version: 0.16.0
rsyslog_server: 172.16.200.2
rsyslog_port: 512
snmp_ro_community: public
snmp_location: Leiden
snmp_contact: infra@naturalis.nl
snmp_allowed_hosts:
  - 172.16.200.10/32
  - 172.16.200.20/32
```

## Dependencies

None.

## Example Playbook

    - hosts: switches
      roles:
        - ansible-role-cumulus-monitoring

## License

Apache2
