# Scripts

All scripts are written for **Azure CLI in Bash** (Cloud Shell or local).

| File | What it does |
|------|-------------|
| `01-foundation.azcli` | Resource group, hardened storage account (GRS, TLS 1.2, no anonymous access), three containers |
| `02-rbac.azcli` | Test users, Entra ID security groups, data-plane role assignments at container scope |
| `03-sas-policy.azcli` | Stored access policy, service SAS generation, kill-switch and resurrection commands |
| `lifecycle-policy.json` | Full lifecycle management policy — deployable via CLI |

## Full environment rebuild

```bash
bash 01-foundation.azcli
bash 02-rbac.azcli
bash 03-sas-policy.azcli

az storage account management-policy create \
  --account-name stfintrustdocs -g rg-fintrust-prod \
  --policy @lifecycle-policy.json
```

## Teardown

```bash
az group delete -n rg-fintrust-prod --yes
```
