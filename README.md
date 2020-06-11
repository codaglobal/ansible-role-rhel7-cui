# Unclassified Information in Non-Federal Information Systems and Organizations (NIST 800-171)

[![Build Status](https://travis-ci.org/RedHatOfficial/ansible-role-rhel7-cui.svg?branch=master)](https://travis-ci.org/RedHatOfficial/ansible-role-rhel7-cui)
[![Ansible Role](https://img.shields.io/ansible/role/39711.svg)](https://galaxy.ansible.com/RedHatOfficial/rhel7_cui)
[![GitHub release](https://img.shields.io/github/release/RedHatOfficial/ansible-role-rhel7-cui.svg)](https://github.com/RedHatOfficial/ansible-role-rhel7-cui/releases/latest)

## Profile Description
#### From NIST 800-171, Section 2.2
Security requirements for protecting the confidentiality of Controlled Unclassified Information (CUI) in non-federal
information systems and organizations have a well-defined structure that consists of:
(i) a basic security requirements section;
(ii) a derived security requirements section.

The basic security requirements are obtained from FIPS Publication 200, which provides the high-level and fundamental security requirements for federal
information and information systems. The derived security requirements, which supplement the basic security requirements, are taken from the security controls in NIST Special Publication 800-53.

This profile configures Red Hat Enterprise Linux 7/8 to the NIST Special Publication 800-53 controls identified for securing Controlled Unclassified
Information (CUI). The tasks that are used in this role are generated using OpenSCAP. See the OpenSCAP project for more details on Ansible playbook generation at [https://github.com/OpenSCAP/openscap](https://github.com/OpenSCAP/openscap).

To submit a fix or enhancement for an Ansible task that is failing or missing, see the ComplianceAsCode project at [https://github.com/ComplianceAsCode/content](https://github.com/ComplianceAsCode/content).

## Requirements
- Ansible v2.5+

## Role Variables
To customize the role to your liking, check out the [list of variables](vars/main.yml) and [defaults](defaults/main.yml).

## Dependencies
N/A

## Example Playbook
#### Using Ansible Galaxy
Run `ansible-galaxy install RedHatOfficial.rhel7_cui` to download and install the role. Then, you can use the following playbook snippet to run the Ansible role:
```
- hosts: all
  roles:
    - { role: RedHatOfficial.rhel7_cui }
```

Next, check the playbook using (on the localhost) the following example:
```
ansible-playbook -i 'localhost' -c local --check playbook.yml
```

To deploy it (this may change configuration of your local machine):
```
ansible-playbook -i 'localhost' -c local playbook.yml
```

#### Using the Local Source
```
mkdir roles
git clone git@github.com:mkorejo/ansible-role-rhel7-cui.git -d roles/

cat << EOF > ansible.cfg
[defaults]
roles_path=/Users/muradkorejo/git/roles
EOF

cat << EOF > playbook.yaml
- hosts: all
  become: true
  roles:
    - { role: ansible-role-rhel7-cui }
EOF

cat << EOF > inventory
<aws-rhel-host>.compute-1.amazonaws.com ansible_user=ec2-user
EOF

ansible-playbook -i inventory --check playbook.yaml -vv
```

## License
BSD-3-Clause

## Author Information
This Ansible remediation role has been generated from the body of security policies developed by the ComplianceAsCode project. Please see [https://github.com/complianceascode/content/blob/master/Contributors.md](https://github.com/complianceascode/content/blob/master/Contributors.md) for an updated list of authors and contributors.