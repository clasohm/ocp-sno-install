Usage:

```
ansible-playbook sno-install.yaml \
  -e base_domain=example.com \
  -e cluster_name=ocp1 \
  -e machine_network=192.168.122.0/24 \
  -e pull_secret=PULL_SECRET
```

The pull secret can be retrieved from https://console.redhat.com/openshift/install/pull-secret

After installing the cluster, leave it running for 24 hours. Otherwise, the initial client certificate 
for the Kubelet will expire and cannot be renewed. The current expiration can be checked by running 
the following command on the cluster node:

```
openssl x509 -text -noout -in /var/lib/kubelet/pki/kubelet-client-current.pem | less
```
