# Hikoru

Schematic id : factory.talos.dev/installer/5752376e3fc9335bef047fa9591181a45535bceadf525689f005305b4bea1ebd:v1.7.4

```
customization:
    systemExtensions:
        officialExtensions:
            - siderolabs/amd-ucode
            - siderolabs/amdgpu-firmware
            - siderolabs/qemu-guest-agent
            - siderolabs/util-linux-tools
```

# usefull commands

```bash
# force update flux
flux reconcile source git home-kubernetes
# get flux objects status
flux get all -A --status-selector ready=false
# token for the dashboard
kubectl -n kubernetes-dashboard create token admin-user
# to connect to primary database
kubectl -n database port-forward "$(kubectl -n database get pods -l postgres-operator.crunchydata.com/role=master -o name)" 5432:5432
```

# todolist

- monitoring stack
  - loki
- keystore
- kyverno blocking unknown storage class ?
