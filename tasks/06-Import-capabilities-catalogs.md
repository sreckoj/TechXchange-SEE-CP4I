## Import capabilities catalogs

Here is a list of parameters and commands for importing per CP4I capability. For each of the capabilities we show the CASE repo URL where you can check the latest CASE version and the commands for importing. 

If you run on **Windows**, open the command prompt as an administrator. In the examples bellow, we asume the user name **Admin**

**The table of contents:**

- [IBM API Connect](#api-connect)
- [IBM App Connect](#app-connect)
- [IBM Aspera HSTS](#aspera)
- [IBM Automation foundation assets](#asset-repo)
- [IBM Cloud Pak for Integration Operations Dashboard](#operations-dashboard)
- [IBM DataPower Gateway](#data-power)
- [IBM Event Endpoint Management](#event-em)
- [IBM Event Streams](#event-streams)
- [IBM MQ](#mq)

<br><br>

<a name="api-connect"></a>
### IBM API Connect

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-apiconnect

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-apiconnect
      set CASE_VERSION=5.0.0
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources-linux-amd64.yaml
      oc apply -f catalog-sources.yaml
      ```


<a name="app-connect"></a>
### IBM App Connect 

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-appconnect

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-appconnect 
      set CASE_VERSION=9.2.0
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources.yaml
      ```

<a name="aspera"></a>
### IBM Aspera HSTS 

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-aspera-hsts-operator

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-aspera-hsts-operator
      set CASE_VERSION=1.5.11
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources.yaml
      ```

<a name="asset-repo"></a>
### IBM Automation foundation assets

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-integration-asset-repository

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-integration-asset-repository
      set CASE_VERSION=1.5.12
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources-linux-amd64.yaml
      ```

<a name="operations-dashboard"></a>
### IBM Cloud Pak for Integration Operations Dashboard  

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-integration-operations-dashboard

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-integration-operations-dashboard
      set CASE_VERSION=2.6.14
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources-linux-amd64.yaml
      ```

<a name="data-power"></a>
### IBM DataPower Gateway 

  - *NOTE:* This step is not necessary if you have already imported catalog source for API Connect. 
    In this case the DataPower gateway catalog is also already imported.   

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-datapower-operator

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-datapower-operator
      set CASE_VERSION=1.7.0
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources-linux-amd64.yaml
      ```

<a name="event-em"></a>
### IBM Event Endpoint Management

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-eventendpointmanagement

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-eventendpointmanagement
      set CASE_VERSION=11.0.3
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources-linux-amd64.yaml
      ```

<a name="event-streams"></a>
### IBM Event Streams 

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-eventstreams

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-eventstreams
      set CASE_VERSION=3.2.3
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources.yaml
      ```

<a name="mq"></a>
### IBM MQ

  - Check the latest version:<br>
    https://github.com/IBM/cloud-pak/tree/master/repo/case/ibm-mq

  - **Linux/Mac**  
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

  - **Windows**
    - Prepare
      ```bat
      set CASE_NAME=ibm-mq
      set CASE_VERSION=2.4.2
      ```
    - Run
      ```bat
      oc ibm-pak get %CASE_NAME% --version %CASE_VERSION%
      oc ibm-pak generate mirror-manifests %CASE_NAME% icr.io --version %CASE_VERSION%
      cd C:\Users\Admin\.ibm-pak\data\mirror\%CASE_NAME%\%CASE_VERSION%
      oc apply -f catalog-sources.yaml
      ```
