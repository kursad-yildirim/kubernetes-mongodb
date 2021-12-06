# 8-mega-kubernetes-mongodb-single

The content given in this repo can be used to install a stateful mongodb deployment on a kubernetes cluster.

Kubernetes Resource List:

<ul>
    <li>Deployment</li>
    <li>Service of type <i>ClusterIP</i> </li>
    <li>Persistent Volume and Persistent Claim of type <i>Hostpath</i></li>
</ul>

MongoDB database will be persistent. There will be no authentication nor ssl in place.