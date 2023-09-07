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

  <!-- TODO: Screenshots that show catalog importing process -->
