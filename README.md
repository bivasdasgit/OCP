# OCP Insecure Registry:

Add Insecure Registry 
```
/etc/docker/daemon.json

{
  "insecure-registries" : ["default-route-openshift-image-registry.apps.fusees.cp.fyre.ibm.com"]
}
------------------------------------------------------------------------------------------------
{
  "insecure-registries" : ["9.30.118.39:5000/justme/webapps"]
}

service docker restart
```
Allowing on OpenShift (Assuming hostname to be localregistry-x86.fyre.ibm.com):
```
oc edit image.config.openshift.io/cluster
Add below lines:
::
spec:
  registrySources:
    insecureRegistries:
    - localregistry-x86.fyre.ibm.com:5000
 ```
