# Ansible role: AWS VPC CGW

This role handles the creation of any number of customer gateways.

[![Build Status](https://travis-ci.org/Flaconi/ansible-role-aws-vpc-cgw.svg?branch=master)](https://travis-ci.org/Flaconi/ansible-role-aws-vpc-cgw)
[![Version](https://img.shields.io/github/tag/Flaconi/ansible-role-aws-vpc-cgw.svg)](https://github.com/Flaconi/ansible-role-aws-vpc-cgw/tags)
<!-- [![Ansible Galaxy](https://img.shields.io/ansible/role/d/25919.svg)](https://galaxy.ansible.com/Flaconi/aws-vpc-cgw/) -->

## Requirements

* Ansible 2.5


## Additional variables

Additional variables that can be used (either as `host_vars`/`group_vars` or via command line args):

| Variable                     | Description                  |
|------------------------------|------------------------------|
| `aws_vpc_vgw_profile`        | Boto profile name to be used |
| `aws_vpc_cgw_default_region` | Default region to use        |


## Example definition

#### Required parameter only

```yml
aws_vpc_cgws:
  - name: playground-cgw-provider-ext
    ip_address: 185.28.50.12
  - name: playground-cgw-office-hq
    ip_address: 185.28.50.10
```

#### All available parameter
```yml
aws_vpc_cgws:
  - name: playground-cgw-provider-ext
    ip_address: 185.28.50.12
    bgp_asn: 65000
    routing: dynamic
    region: eu-central-1
    tags:
      - key: env
        val: playground
      - key: department
        val: devops
  - name: playground-cgw-office-hq
    ip_address: 185.28.50.10
    bgp_asn: 65000
    routing: dynamic
    region: eu-central-1
    tags:
      - key: env
        val: playground
      - key: department
        val: devops
```
