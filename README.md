
# TechXchange-SEE: IBM Cloud Pak for Integration installation


Box folder with additional information (available only to the workshop attendees)<br>
[https://ibm.ent.box.com/folder/224564672852](https://ibm.ent.box.com/folder/224564672852)


## IBM Documentation

Adding catalog sources to a cluster:
[https://www.ibm.com/docs/en/cloud-paks/cp-integration/2023.2?topic=images-adding-catalog-sources-cluster](https://www.ibm.com/docs/en/cloud-paks/cp-integration/2023.2?topic=images-adding-catalog-sources-cluster)


## Tasks

- [01. Install OpenShift CLI](tasks/01-Install-OpenShift-CLI.md)
- [02. Install IBM Pak](tasks/02-Install-IBM-Pak.md)

## Install IBM Pak

Check the latest version:
https://github.com/IBM/ibm-pak/releases

Download for the desired operating system.

**Linux:**
https://github.com/IBM/ibm-pak/releases/download/v1.9.0/oc-ibm_pak-linux-amd64.tar.gz

**Mac:**
https://github.com/IBM/ibm-pak/releases/download/v1.9.0/oc-ibm_pak-darwin-amd64.tar.gz

**Windows:**
https://github.com/IBM/ibm-pak/releases/download/v1.9.0/oc-ibm_pak-windows-amd64.tar.gz

Unzip and copy to the location in your PATH:

Linux example:
```
wget https://github.com/IBM/ibm-pak/releases/download/v1.9.0/oc-ibm_pak-linux-amd64.tar.gz
tar -xf oc-ibm_pak-linux-amd64.tar.gz
chmod 755 oc-ibm_pak-linux-amd64
mv oc-ibm_pak-linux-amd64 /usr/local/bin/oc-ibm_pak
```
Verify
```
oc ibm-pak --version
```

## Import catalogs using CASE files

CASE files repo base URL:
https://github.com/IBM/cloud-pak/tree/master/repo/case

Here is a list of parameters and commands for importing per CP4I capability. For each of the capabilities we show the CASE repo URL where you can check the latest CASE version and the commands for importing. 

**NOTE:** Login to the OpenShift cluster before you start.

**TODO:** Login to OpenShift screenshots

### Platform navigator

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-integration-platform-navigator
  - Prepare
    ```sh
    export CASE_NAME=ibm-integration-platform-navigator && export CASE_VERSION=7.1.2
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources.yaml
    ```

  **TODO:** Screenshots that show catalog importing process

### IBM API Connect

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-apiconnect
  - Prepare
    ```sh
    export CASE_NAME=ibm-apiconnect && export CASE_VERSION=5.0.0
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources-linux-amd64.yaml    # DataPower 
    oc apply -f catalog-sources.yaml                # API Connect
    ```

### IBM App Connect 

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-appconnect
  - Prepare
    ```sh
    export CASE_NAME=ibm-appconnect && export CASE_VERSION=9.2.0
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources.yaml
    ```

### IBM Aspera HSTS 

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-aspera-hsts-operator
  - Prepare
    ```sh
    export CASE_NAME=ibm-aspera-hsts-operator && export CASE_VERSION=1.5.11
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources.yaml
    ```

### IBM Automation foundation assets

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-integration-asset-repository
  - Prepare
    ```sh
    export CASE_NAME=ibm-integration-asset-repository && export CASE_VERSION=1.5.12
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources-linux-amd64.yaml
    ```

### IBM Cloud Pak for Integration Operations Dashboard  

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-integration-operations-dashboard
  - Prepare
    ```sh
    export CASE_NAME=ibm-integration-operations-dashboard && export CASE_VERSION=2.6.14
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources-linux-amd64.yaml
    ```

### IBM DataPower Gateway 

  - *NOTE:* This step is not necessary if you have already imported catalog source for API Connect. 
    In this case the DataPower gateway catalog is also already imported.   

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-datapower-operator
  - Prepare
    ```sh
    export CASE_NAME=ibm-datapower-operator && export CASE_VERSION=1.7.0
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources-linux-amd64.yaml
    ```

### IBM Event Endpoint Management

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-eventendpointmanagement
  - Prepare
    ```sh
    export CASE_NAME=ibm-eventendpointmanagement && export CASE_VERSION=11.0.3
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources-linux-amd64.yaml
    ```

### IBM Event Streams 

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-eventstreams
  - Prepare
    ```sh
    export CASE_NAME=ibm-eventstreams && export CASE_VERSION=3.2.3
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources.yaml
    ```

### IBM MQ

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-mq
  - Prepare
    ```sh
    export CASE_NAME=ibm-mq && export CASE_VERSION=2.4.2
    ```
  - Run
    ```sh
    oc ibm-pak get ${CASE_NAME} --version ${CASE_VERSION}
    oc ibm-pak generate mirror-manifests ${CASE_NAME} icr.io --version ${CASE_VERSION}
    cd ~/.ibm-pak/data/mirror/${CASE_NAME}/${CASE_VERSION}
    oc apply -f catalog-sources.yaml
    ```

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

