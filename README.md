
# TechXchange-SEE: IBM Cloud Pak for Integration installation


Box folder with additional information (available only to the workshop attendees)<br>
[https://ibm.ent.box.com/folder/224564672852](https://ibm.ent.box.com/folder/224564672852)


## IBM Documentation

Adding catalog sources to a cluster:
[https://www.ibm.com/docs/en/cloud-paks/cp-integration/2023.2?topic=images-adding-catalog-sources-cluster](https://www.ibm.com/docs/en/cloud-paks/cp-integration/2023.2?topic=images-adding-catalog-sources-cluster)


## Tasks

- [01. Install OpenShift CLI](tasks/01-Install-OpenShift-CLI.md)
- [02. Install IBM Pak](tasks/02-Install-IBM-Pak.md)
- [03. Login to OpenShift](tasks/03-Login-to-OpenShift.md)
- [04. Import Platform UI catalog](tasks/04-Import-Platform-UI-catalog.md)
- [05. Import capabilities catalogs using CASE files](tasks/05-Import-capabilities-catalogs.md)



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

**TODO:** Screenshots for operator subscription and creating instances. 



















---

