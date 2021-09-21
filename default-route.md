# Default Route
```
oc get route default-route -n openshift-image-registry
oc patch configs.imageregistry.operator.openshift.io/cluster --type merge -p '{"spec":{"defaultRoute":true
```
```
oc new-project <project_name> || true
oc policy add-role-to-group system:image-puller system:serviceaccounts --namespace=<project_name> || true
HOST=$(oc get route default-route -n openshift-image-registry --template='{{ .spec.host }}')
docker tag <image_name>:<tag> $HOST/<namespace>/<image_name>:<tag>

docker login -u kubeadmin -p $(oc whoami -t) $HOST
docker push $HOST/<namespace>/<image_name>:<tag>

oc describe is/<resources>
./build.sh -t che-devfile-registy:7.20.0 --rhel
```
```
oc clusterinfo 
oc login -u kubeadmin https://api.salutes.cp.fyre.ibm.com:6443
```
