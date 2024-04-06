# Cloud-Continuum-seamless-connection-of-home-resources-with-the-cloud

Some recent projects, such as [casaos.io](https://casaos.io/), aim at creating a software framework that facilitates the creation of a domestic server, simplifying applications install, maintenance, monitoring, and data management. However, such projects can run applications that are limited by the amount of resources available on the selected server; furthermore, data may be at risk if not properly backed-up.

This project tackes this problem by adopting the "cloud continuum" paradigm (such as in the [FLUIDOS European Project](https://www.fluidos.eu/)),  creating a unique virtual space of resources and services spanning across the domestic server and a set of selected cloud providers. Services (and data) can be executed (and stored) in any place of the continuum, either on the local server or on the cloud, depending on the selected policies, facilitating cloud bursting (i.e., the cloud can be used as an "overflow" server in case of necessity), as well as data redundancy (i.e., data can be automatically replicated locally and remotely).

This project will heavily rely on Kubernetes (e.g., [K3d](https://github.com/k3d-io/k3d)) and [Liqo](https://liqo.io/) as building blocks, and it may require the creation of a minimal dashboard to facilitate the users in the edge-to-cloud interaction.

## Verify your Inventory

```bash
ansible-inventory -i Ansible/Inventory/inventory.ini --list
```

## Ping the myhosts group in your inventory

```bash
ansible myhosts -m ping -i Ansible/Inventory/inventory.ini
```

## Execution

### NOTICE: the users used in the two machine should have root privileges in order to work properly

```bash
ansible-playbook Ansible/Playbook/env-setup.yaml -i Ansible/Inventory/inventory.ini
```
