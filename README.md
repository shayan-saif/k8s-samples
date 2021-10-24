# k8s-samples

## Imperative commands
At the end of a command  `kubectl ... --dry-run=client -o yaml` will output the yaml definition

### Pod
`kubectl run <name> --image=<image> --port=<port> --expose`
- --expose creates a service of type *ClusterIP*

### Service
`kubectl expose <resource-type> <resource-name> --port=<port> --name <svc name>`

### Deployment
`kubectl create deployment <name> --namespace=<namespace> --image=<image> --replicas=<replicas>`
