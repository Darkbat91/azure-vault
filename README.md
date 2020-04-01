# Hashicorp Vault Ansible role
This role has two options. A stanalone server with file based backend or the ability to store the backend and secrets in Azure

# Usage
The role has a few sane defaults that allow it to just be ran directly however if the below settings are configured it will store the backend as well as the root and unlock keys within Azure

```
vault_backend:  'Azure'
vault_azurestorageaccount: 'stvaultstorage' # Storage account must exist
vault_azurestoragekey: 'mysecretkeytoaccessvault' # Key to access the storage account 
Keyvaulturi: # Path to the Keyvault that ansible has write access to secrets on
```

This will start and inialize vault with the backend in Azure blob(object) storage and safely put the keys in azure keyvault where other systems can utilize them.

# Advanced

There are numerous other options within the [defaults/main.yml](./defaults/main.yml) that can change other parts of the behavior of the system