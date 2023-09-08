## Create instance of the Platform Navigator

Prepare the IBM Entitlement key. Normaly, the key would be obtained on the following site: https://myibm.ibm.com/products-services/containerlibrary but for the workshop, it will be provided by the instructor.

Create an environment variable, for example:
- **Linux/Mac:**
  ```sh
  export ENTITLEMENT_KEY=...YOUR_ENTITLEMENT_KEY... 
  ```
- **Windows:**
  ```bat
  set ENTITLEMENT_KEY=...YOUR_ENTITLEMENT_KEY... 
  ```

If you have instlled *podman* or *docker* on your machine, you can verify the key with:
- **Linux/Mac:**
  ```sh
  podman login cp.icr.io --username cp --password $ENTITLEMENT_KEY
  ```
  or
  ```sh
  docker login cp.icr.io --username cp --password $ENTITLEMENT_KEY
  ```
- **Windows:**
  ```bat
  podman login cp.icr.io --username cp --password %ENTITLEMENT_KEY%
  ```
  or
  ```bat
  docker login cp.icr.io --username cp --password %ENTITLEMENT_KEY%
  ```


We will also need an OpenShift project. To create a new project we would use command `oc new-project ...`But, for this workshop, there is the set of projects called *student01, student02...* etc, already predefined. Use the project name provided for you by the instructor.

You may put it in the environment variable
- **Linux/Mac:**
  ```sh
  export PROJECT=...YOUR_PROJECT_NAME...
  ```
- **Windows:**
  ```bat
  set PROJECT=...YOUR_PROJECT_NAME...
  ```

Create an OpenShift secret with the entitlement key in that project. The secret name must be **ibm-entitlement-key**:
- **Linux/Mac:**
  ```sh
  oc create secret docker-registry ibm-entitlement-key --docker-username=cp --docker-password=$ENTITLEMENT_KEY --docker-server=cp.icr.io --namespace=$PROJECT
  ```
- **Windows:**
  ```bat
  oc create secret docker-registry ibm-entitlement-key --docker-username=cp --docker-password=%ENTITLEMENT_KEY% --docker-server=cp.icr.io --namespace=%PROJECT%
  ```

We will continue in the OpenShift web console (discuss with the instructor possibilties of completing the same steps from command line).

<!-- TODO: Screenshots for operator subscription and creating instances. -->
