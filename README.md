
```bash
git clone https://github.com/CiscoDevNet/aci_ansible_learning_labs_code_samples
cd aci_ansible_learning_labs_code_samples

docker run --rm -it -v $(pwd):/ansible -v ~/.ssh/id_rsa:/root/id_rsa willhallonline/ansible:centos /bin/sh    <-- HAS TO BE CENTOS?

ansible-galaxy collection install cisco.aci
```
https://github.com/CiscoDevNet/ansible-aci

## Use
Once the collection is installed, you can use it in a playbook by specifying the full namespace path to the module, plugin and/or role.

```
- hosts: aci
  gather_facts: no

  tasks:
  - name: Add a new EPG
    cisco.aci.aci_epg:
      hostname: apic
      username: admin
      password: SomeSecretPassword
      tenant: production
      ap: intranet
      epg: web_epg
      description: Web Intranet EPG
      bd: prod_bd
    delegate_to: localhost
```

https://github.com/CiscoDevNet/aci_ansible_learning_labs_code_samples

	• APIC URL: https://sandboxapicdc.cisco.com
	• Username: admin 
	• Password: ciscopsdt
