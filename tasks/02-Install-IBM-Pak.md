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

Linux/Mac example:
```
tar -xf oc-ibm_pak-linux-amd64.tar.gz
chmod 755 oc-ibm_pak-linux-amd64
mv oc-ibm_pak-linux-amd64 /usr/local/bin/oc-ibm_pak
```

On Windows 10, open command prompt as administrator and extract file to any directory that is in the PATH. In the following example the directory name is *C:\CLI*
```
tar -xvzf oc-ibm_pak-windows-amd64.tar.gz -C C:\CLI
```
The name of extracted file is *oc-ibm_pak-windows-amd64*, rename it to *oc-ibm_pak.exe*

Verify
```
oc ibm-pak --version
```
