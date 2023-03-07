## kubernetes-mongodb-single

The content given in this repo can be used to install a stateful mongodb deployment on a kubernetes cluster.

Kubernetes Resource List:

- Deployment
- Service
- Persistent Volume and Persistent Claim

MongoDB database will be persistent. There will be no authentication nor ssl in place.

### Deployment:
MongoDb will be deployed in `default` namespaces with 1 replica. `mongo:4.2.17-bionic` will be used as the container image. If volume and claim definitions are not in place prior to outting the deployment, k8s will throw a corresponding error and mongodb pod will not go into `Running` state. When persistent storage definitions are done pod will resume.

### Service:
Service type will be `ClusterIP`. So it will be only accessible within k8s cluster

### Storage:
Static provisioning will be used. Storage type will be `Hostpath` Two volume-claim pairs will be defined as:

- Config: 1GB
- Data: 10GB

For all volumes access mode will be `ReadWriteMany`.

### Installation:
All resources can be created by using the command below:

~~~
kubectl apply -f <filename>

~~~
