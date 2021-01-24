# Document to install the istio


## Downloading the istioctl 

```
wget 
https://github.com/istio/istio/releases/download/1.8.2/istioctl-1.8.2-linux-amd64.tar.gz
```
Unzip the package

```
tar zxf istioctl-1.8.2-linux-amd64.tar.gz 
```
Move to bin

```
mv istioctl /bin
``


## Using the istioctl command create the manifest file

```
istioctl profile dump demo > install_istio_core_components.yaml

```

## Deploying in the CLuster