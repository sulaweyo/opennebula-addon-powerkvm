# PowerKVM Hypervisor support for OpenNebula

## Description

This addon provides a driver to add the IBM PowerKVM hypervizor to OpenNebula.
PowerKVM basically provides the same functionality as kvm but for the PPC platform. It could reuse the KVM driver actions but we want to cleanly distinguish between the two types to make sure kvm vm does not accidently end on a powerkvm node or vice versa.

## Authors

* Georg Brunmayr (https://github.com/sulaweyo)
* Markus Heimbach (https://github.com/esukram)

The driver installation is based on the Xen driver written by:
* Héctor San Juan
* OpenNebula Core Team

## Features

* Extend the hypervisors supported by OpenNebula with PowerKVM

## Compatibility

This add-on is compatible with:

| OpenNebula Version |
| ------------------ |
| 5.2                |
| 5.4                |


## Installation

To install this add-on, clone it and run install.sh:

    sudo ./install.sh -u oneadmin -g oneadmin

You wil need to add the following to `/etc/one/oned.conf`: [oned.conf for PowerKVM](oned-powerkvm.conf)

## Usage

The usage guide can be found here: [PowerKVM Driver](docs/xeng.rst)

## Configuration

* ``/etc/one/vmm_exec/vmm_exec_powerkvm.conf``: Defines the default values for VM templates: ``credit``, ``os [kernel,initrd,root,kernel_cmd,hvm]``, ``vcpu``, ``features [acpi, pae, apic, device_model, localtime]``, ``disk[driver]``, ``nic[model]`` and ``raw``.

## Development

To contribute bug patches or new features, you can use the github Pull Request model. It is assumed that code and documentation are contributed under the Apache License 2.0.
