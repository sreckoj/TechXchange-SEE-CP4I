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

Unzip and copy to the location in your PATH.

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
