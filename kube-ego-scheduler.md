# This is kubernetes ego integration projects

<hr>

* Release version:0.1.2<br>
* Publication date: 20 November 2015<br>
* Last modified: 20 November 2015<br>

#####This document describes how to build the kubernetes ego integration scheduler.<br>

####1、Preconditions<br>

1) Linux environment is necessary.<br>
2) Go version：go1.5.0 linux/amd64 or above should be installed.<br> 
3) IBM EGO version：ibm-ego-3.2.0-354246.ibm.x86_64 should be installed.<br>
4) All kubernetes code version 1.0.0 is nesessary.<br>

####2、Usage<br>

1) get the resource<br>
```Bash
git clone  https://github.rtp.raleigh.ibm.com/qiujian-cn/kubernetes-ego.git
```
2)build binaries<br>
```Bash
cd kubernetes-ego

export KUBERNETES_CONTRIB=ego

make
```
3)The binaries will be put in _output/local/bin soon<br>
