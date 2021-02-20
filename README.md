# KUSTOMIZE Demo for OpenShift 4.x
This is a very quick and dirty kustomize.io demo based on the ___helloWorld___ example. It adds a route to be deployed to OpenShift 4.x

## Prepare your environment
Setup your OpenShift cluster (use code-ready/crc), login into it with the user developer and create a new project
```bash
$> crc setup && crc start
$> oc login -u developer -p developer https://api.crc.testing:6443/
$> oc new-project kustomize-demo

```
## Installing the base app
```bash
$> kustomize build ./base | oc apply -f -
```

## Installing the staging app
```bash
$> kustomize build ./overlays/staging | oc apply -f -
```


