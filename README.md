# CLEUR2020-DEVWKS-3535
Code for Cisco Live DEVWKS-3535

This repository contains the code used for the DEVNET workshop in CLEUR 2020

Ansible Playbooks

- Running playbook to configure Tenant,EPGs, BDs, and Contracts with ansible modules (no rest module)
ansible-playbook cleurmodulesconf.yaml -e IPapic="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt"

- Remove tenant with ansible module a tenant (no rest module)
ansible-playbook cleurmoduleremovetenant.yaml -e IPapic="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt"

- Running playbook with ansible rest to configure Tenant,EPGs, BDs, and Contracts
ansible-playbook cleurrestconf.yaml -e IPapic="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt"

- Remove tenant with ansible rest
ansible-playbook cleurrestremovetenant.yaml -e IPapic="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt"

- Running again playbook to configure Tenant,EPGs, BDs, and Contracts
ansible-playbook cleurrestconf.yaml -e IPapic="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt"

- Query the EPG params by REST
ansible-playbook cleurrestquery.yaml -e IPapic="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt" -e pathurl="/api/node/mo/uni/tn-CLEUR_Tenant/ap-CLEUR_ap/epg-CLEUR_egp1.json?query-target=children&target-subtree-class=fvRsBd"

- Query the EPG params by REST and selecting only the BD in an specific EPG
ansible-playbook cleurrestquerynested.yaml -e IPapic="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt" -e pathurl="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt" -e pathurl="/api/node/mo/uni/tn-CLEUR_Tenant/ap-CLEUR_ap/epg-CLEUR_egp1.json?query-target=children&target-subtree-class=fvRsBd"

- Running playbook to automate the BD removal
ansible-playbook cleurrestremoveautobd.yaml -e IPapic="sandboxapicdc.cisco.com" -e userapic="admin" -e passapic="ciscopsdt"