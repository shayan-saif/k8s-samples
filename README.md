# k8s-samples

## Imperative commands
- `kubectl ... --dry-run=client -o yaml` will output the yaml definition
- `kubectl ... | grep -i <search-term>` to search output of a command

### Pod
`kubectl run <name> --image=<image> --port=<port> --expose`
- `--expose` flag creates a service of type *ClusterIP*

### Service
`kubectl expose <resource-type> <resource-name> --port=<port> --name <svc name> --type=<service-type (i.e. NodePort)>`

### Deployment
`kubectl create deployment <name> --namespace=<namespace> --image=<image> --replicas=<replicas>`
