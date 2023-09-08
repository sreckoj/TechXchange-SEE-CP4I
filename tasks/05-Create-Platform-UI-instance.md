## Create instance of the Platform Navigator

Prepare the IBM Entitlement key. Normaly, the key would be obtained on the following site: https://myibm.ibm.com/products-services/containerlibrary but for the workshop it will be provided by the instructor.

Create an environment variable, for example:
```sh
export ENTITLEMENT_KEY=...YOUR_ENTITLEMENT_KEY... 
```
If you have instlled *podman* or *docker* on your machine, you can verify the key with:
```sh
podman login cp.icr.io --username cp --password $ENTITLEMENT_KEY
```
or
```sh
docker login cp.icr.io --username cp --password $ENTITLEMENT_KEY
```

We will also need a new OpenShift project. It can have whatever name. Let's name it *cp4i* 

Create another environment variable with the project name:
```sh
export PROJECT=cp4i
```

Create project:
```sh
oc new-project $PROJECT
```
Create an OpenShift secret with the entitlement key in that project. The secret name must be *ibm-entitlement-key*:
```sh
oc create secret docker-registry ibm-entitlement-key --docker-username=cp --docker-password=$ENTITLEMENT_KEY --docker-server=cp.icr.io --namespace=$PROJECT
```

We will continue in the OpenShift web console (discuss with the instructor possibilties of completing the same steps from command line).

<!-- TODO: Screenshots for operator subscription and creating instances. -->
