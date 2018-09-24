# Ansible Role: Cumulus metrics

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

See defaults/main.yml.

## Dependencies

None.

## Example Playbook

    - hosts: switches
      roles:
        - ansible-cumulus-metrics

## License

Apache2
