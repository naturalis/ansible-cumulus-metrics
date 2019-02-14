# Ansible Role: Cumulus metrics

This role will install the prometheus node_exporter, setup snmp and configure an external rsyslog server.

Naturalis uses this role together with a private inventory.

Locally (on the switch) the metrics are visible on the endpoint by running:
```bash
curl http://localhost:9100/metrics
```
Or by running it against a switch from e.g. an oob-mgmt-server:
```bash
curl netdw2-spine-a:9100/metrics
```

## Requirements

None.

## Role Variables

```bash
node_exporter_version: 0.16.0
node_exporter_listen: "0.0.0.0:9100"
cl_oob_server: 192.168.144.5
rsyslog_port: 514
snmp_ro_community: public
snmp_location: Leiden
snmp_contact: infra@naturalis.nl
snmp_allowed_hosts:
  - 192.168.144.5/32
snmp_listen: 127.0.0.1
jq_install: true
jq_use_apt: false
```

## Dependencies

None.

## Example Playbook

    - hosts: switches
      roles:
        - ansible-cumulus-metrics

## License

Apache2
