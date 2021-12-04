# k8s-samples

## Imperative commands
- `kubectl ... --dry-run=client -o yaml` will mock a command execution and output the yaml definition
- `kubectl ... | grep -i <search-term>` to search output of a command

## Explain
- `kubectl explain <resource> --recursive | less` will explain the YAML structure, type '/searchterm' to search for something (i.e. volumes)
#### Example
- `kubectl explain pods --recursive | less`

### Pod
`kubectl run <name> --image=<image> --port=<port> --expose`
- `--expose` flag creates a service of type *ClusterIP*
#### Example
- `kubectl run nginx-pod --image=nginx:alpine --port=80`

### Service
`kubectl expose <resource-type> <resource-name> --name <svc name> --type=<service-type (i.e. NodePort)>  --port=<port> --target-port`
#### Example
`kubectl expose deploy app-deploy --name=app-svc --type="NodePort" --port=80 --target-port=80`

### Ingress
`kubectl create ingress <ingress-name> --rule="<host/path=service:port>"`

#### Example
`kubectl create ingress app-ingress --rule="app.com/*=app-svc:80"`

### Deployment
`kubectl create deploy <name> -n=<namespace> --image=<image> --replicas=<replicas> -port=<port>`
`kubectl create deploy app-deploy --image=nginx:alpine --replicas=3 --port=80`

### ConfigMap
`kubectl create configmap <name> --from-literal=<key=value>`
#### Example
`kubectl create configmap nginx-config --from-literal=DB_HOST=postgres --from-literal=DB_USER=postgres --from-literal=DB_PORT=5432`

### Secrets
`kubectl create secret generic <name> --from-literal=<key=value>`
`kubectl create secret generic db-secret --from-literal=POSTGRES_PASSWORD=postgres`

### Node Affinity
- `kubectl describe node <node-name> | head` displays labels and annotations for given node
- `kubectl label node <node-name> <key>=<value>` labels a node

### Node/Pod level metrics
- `kubectl top node` or `kubectl top pod` to see resource consumption
