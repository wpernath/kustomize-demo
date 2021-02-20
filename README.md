# KUSTOMIZE Demo for OpenShift 4.x
This is a very quick and dirty kustomize.io demo based on the ___helloWorld___ example. It adds a route to be deployed to OpenShift 4.x

## Prepare your environment
- Setup your OpenShift cluster (use code-ready/crc)
- Create a new project: ```oc new-project kustomize-demo`
## Installing the base app
	$> kustomize build ./base | oc apply -f -

## Installing the staging app
	$> kustomize build ./overlays/staging | oc apply -f -


