# k8s-samples

## Imperative commands
- `kubectl ... --dry-run=client -o yaml` will output the yaml definition
- `kubectl ... | grep -i <search-term>` to search output of a command

## Explain
- `kubectl explain <resource> --recursive | grep -i -A<lines> <query>` will explain the YAML structure

### Pod
`kubectl run <name> --image=<image> --port=<port> --expose`
- `--expose` flag creates a service of type *ClusterIP*

### Service
`kubectl expose <resource-type> <resource-name> --port=<port> --name <svc name> --type=<service-type (i.e. NodePort)>`

### Ingress
`kubectl create ingres <ingress-name> --rule="<host/path=service:port>"`

### Deployment
`kubectl create deployment <name> --namespace=<namespace> --image=<image> --replicas=<replicas>`

### ConfigMap
`kubectl create configmap <name> --from-literal=<key=value>`

### Secrets
`kubectl create secret generic <name> --from-literal=<key=value>`

### Node Affinity
- `kubectl describe node <node-name> | head` displays labels and annotations for given node
- `kubectl label node <node-name> <key>=<value>` labels a node
