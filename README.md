# Introduction
This is my personal playbook for configuring grafana with rhel system roles.

# Pre-requisites
Install `rhel-system-roles`.

```
dnf install -y rhel-system-roles
```


# Configure `inventory.yml`

Add the hosts that you want to monitor in this section in `inventory.yml`.

```
children:
    servers:
      hosts:
        ip-172-31-22-201.us-west-1.compute.internal:
```

Add the host you want to configure as the grafana server in this section in `inventory.yml`.

```
metrics_monitor:
      hosts:
        ip-172-31-18-95.us-west-1.compute.internal:
```

# Run the playbook.

Run the following command as a non-root user.
```
ansible-playbook metrics.yml -b -i inventory.yml
```