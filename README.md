<h1> 8-mega-kubernetes-mongodb-single </h1>

The content given in this repo can be used to install a stateful mongodb deployment on a kubernetes cluster.

Kubernetes Resource List:

<ul>
    <li>Deployment</li>
    <li>Service</li>
    <li>Persistent Volume and Persistent Claim</li>
</ul>

MongoDB database will be persistent. There will be no authentication nor ssl in place.

<h2><u>Deployment:</u></h2>
<p>MongoDb will be deployed in <i><font face="Arial" color="#FFD700">default</font></i> namespaces with 1 replica. <i><font face="Arial" color="#FFD700">mongo:4.2.17-bionic</font></i> will be used as the container image.<br>
If volume and claim definitions are not in place prior to outting the deployment, k8s will throw a corresponding error and mongodb pod will not go into <i><font face="Arial" color="#FFD700">Running</font></i> state. When persistent storage definitions are done pod will resume.</p>

<h2><u>Service:</u></h2>
<p>Service type will be <i><font face="Arial" color="#FFD700">ClusterIP</font></i>. So it will be only accessible within k8s cluster</p>

<h2><u>Storage:</u></h2>
<p>Static provisioning will be used. Storage type will be <i><font face="Arial" color="#FFD700">Hostpath</font></i> Two volume-claim pairs will be defined as:
<ul>
    <li>Config: 1GB</li>
    <li>Data: 10GB</li>
</ul>
For all volumes access mode will be <i><font face="Arial" color="#FFD700">ReadWriteMany</font></i>.
</p>

<h2><u>Installation:</u></h2>
<p>All resources can be created by using <br><font face="Consolas" color="#00BFFF">kubectl apply -f <filename></font><br> command.</p>