# kubernetes-coreos
Kubernetes configuration on CoreOS. This is sample config files that running Kubernetes on CoreOS
Configuration is based on https://coreos.com/kubernetes/docs/latest

# Expected system
- Tested with VMWare Guestinfo Interface (https://coreos.com/os/docs/latest/vmware-guestinfo.html)
- Service is exposed by nodePort + External NAT or HA Proxy(Tested with pfSense)
- Kuberenetes nodes are connected by http instead of https
- 5 CoreOS, 1 Master, 4 Nodes
 - 172.16.0.100 (node-100, master)
 - 172.16.0.101 (node-101)
 - 172.16.0.102 (node-102)
 - 172.16.0.103 (node-103)
 - 172.16.0.104 (node-104)
- Enabled Calico network
- Enabled 1GiB swap
- Pod network: 10.2.0.0/16
- Service IP range: 10.3.0.0/24
- DNS service IP: 10.3.0.1

You need to create namespace "calico-system" after launch kubernetes.
`````
$ curl -H "Content-Type: application/json" -XPOST -d'{"apiVersion":"v1","kind":"Namespace","metadata":{"name":"calico-system"}}' "http://172.16.0.100:8080/api/v1/namespaces"
`````
