## Ansible Project

Ansible Repository

### Requirements



### Example Usage

    # Initialize Host
    ansible-playbook -v -i 'hostname.example.com,' -e 'ansible_host=10.10.0.10' playbooks/actions/initialize.yml

    # Deploy Host
    ansible-playbook -v --limit hostname.example.com -e 'hosts_override=all' playbooks/deployments/example.yml

    # Deinitialize Host
    ansible-playbook -v --limit hostname.example.com playbooks/actions/deinitialize.yml

## File structure

The files structure is organised this way:

```
.
├── README.md                             # Documentation entry point
├── docs                                # Advanced documentation topics
│   ├── skel-start.md
│   └── skel-tips.md
├── inventory                           # Inventory directory
│   ├── default.ini -> dev.ini            # Default inventory to use
│   ├── dev.ini                           # Dev inventory
│   ├── preprod.ini                       # Preprod inventary
│   └── prod.ini                          # Production inventory
├── playbooks                           # Playbook directory
|   └── group_vars                          # Group vars directory
    |   ├── all.yml                           # Common variables to all hosts
    |   ├── dev.yml                           # Dev env variables
    |   ├── preprod.yml                       # Preprod env variables
    |   └── prod.yml                          # Production env variables
    └── host_vars                           # Host vars directory
    ├── 0_local_requirements.yaml         # Configure local system
    ├── 1_target_test.yml                 # Test targets
    ├── 2_target_requirements.yml         # Basic configuration of targets
    └── 3_target_sysadmin.yml             # Advanced confivuration of targets
├── Collections                          # Collections directory
│   └── requirements.yml                  # Collections requirements
└── roles                               # Roles directory
    ├── local                             # Locale roles
    ├── profiles                          # Profile roles
    ├── requirements.yml                  # Vendor roles list
    └── vendors                           # Vendor roles
```
