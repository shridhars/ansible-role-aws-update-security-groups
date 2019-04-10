# Ansible Role: Update security groups on AWS

## Requirements

aws cli configured on the system running ansible.
Dynamic aws inventory files for ansible, ec2.ini and ec2.py

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):
    
    aws_region: us-east-1

The region where all the security groups for all instances are to be updated.

    sg_port: 9100
    ip_address_cidr: 0.0.0.0/0
    
The ipaddress and port to whitelist in a particular security group. This could be any ip address cidr block and any port.


## Dependencies

None

## Example Playbook

    - hosts: all
      connection: local
      gather_facts: yes      
      vars:
        aws_region: us-east-1
        sg_port: 9100
        ip_address_cidr: 0.0.0.0/0
      roles:
        - { role: shridhars.aws-update-security-groups }

License
-------

MIT / BSD


