# KUSTOMIZE Demo for OpenShift 4.x
This is a very quick and dirty kustomize.io demo based on the [helloWorld][1] example. It adds a route to be deployed to OpenShift 4.x

## Prepare your environment
Setup your OpenShift cluster (use[code-ready/crc][2]), login into it with the user developer and create a new project

```bash
$> crc setup && crc start
$> oc login -u developer -p developer https://api.crc.testing:6443/
$> oc new-project kustomize-demo
```


### Setup kustomize on Mac
If you want to play locally, you have to setup kustomize. Either download it from the official website or install it via homebrew.
```bash
$> brew install kustomize
```

### Other OS'ses
Just read here: https://kubectl.docs.kubernetes.io/installation/kustomize/


## Installing the base app
```bash
$> kustomize build ./base | oc apply -f -
```

## Installing the staging app
```bash
$> kustomize build ./overlays/staging | oc apply -f -
```



[1]:	https://github.com/kubernetes-sigs/kustomize/tree/master/examples/helloWorld "helloWorld"
[2]:	https://github.com/code-ready/crc