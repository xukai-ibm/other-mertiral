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

####3、Deploy<br>

```Bash
kube-apiserver  --etcd-servers=http://127.0.0.1:2379 --insecure-bind-address=0.0.0.0 --insecure-port=8080 --logtostderr=true --service-cluster-ip-range=10.200.20.0/24 --v=2 

kube-controller-manager --logtostderr=true --master=http://127.0.0.1:8080 --v=2 

kube-scheduler --master=http://127.0.0.1:8080 --v=2 --api-server=127.0.0.1:8080

kubelet --address=0.0.0.0 --port=10250 --hostname_override=ego.localdomain --enable_server=true --v=0 --api-servers=http://127.0.0.1:8080 
```
