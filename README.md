Usage:

```
ansible-playbook sno-install.yaml \
  -e base_domain=example.com \
  -e cluster_name=ocp1 \
  -e machine_network=192.168.122.0/24 \
  -e pull_secret=PULL_SECRET
```

The pull secret can be retrieved from https://console.redhat.com/openshift/install/pull-secret