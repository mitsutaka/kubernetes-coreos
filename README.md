# kubernetes-coreos
Kubernetes configuration on CoreOS. This is sample config files that running Kubernetes on CoreOS

# Expected system
- Service is exposed by nodePort + External NAT(Test with pfSense)
- Kuberenetes nodes are connected by http instead of https
- 5 CoreOS, 1 Master, 4 Nodes
 - 172.16.0.100 (node-100, master)
 - 172.16.0.101 (node-101)
 - 172.16.0.102 (node-102)
 - 172.16.0.103 (node-103)
 - 172.16.0.104 (node-104)
