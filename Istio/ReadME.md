# Document to install the istio


## Downloading the istioctl 

```
wget https://github.com/istio/istio/releases/download/1.8.2/istioctl-1.8.2-linux-amd64.tar.gz
```
Unzip the package

```
tar zxf istioctl-1.8.2-linux-amd64.tar.gz 
```
Move to bin

```
mv istioctl /bin
```

## Using the istioctl command create the manifest file

```
istioctl profile dump demo > install_istio_core_components.yaml

```

## Deploying istio core components in the kubernetes Cluster

```
istioctl install -f install_istio_core_components.yaml --set values.global.jwtPolicy=first-party-jwt

```
## Deploying kiali,grafana,jagger,prometheus components in the kubernetes Cluster

```
kubectl apply -f install_istio_addon_grafana.yaml
kubectl apply -f install_istio_addon_jaeger.yaml
kubectl apply -f install_istio_addon_kiali.yaml
kubectl apply -f install_istio_addon_prometheus.yaml
```

## Accessing

kiali -   http://10.157.50.15:15008
Jagger - http://10.157.50.15:15009
Grafana -  http://10.157.50.15:15010

## Labeling the default namespace

```
kubectl label namespace default  istio-injection=enabled

```
## Deploying the Microservice in the default namespace

```
cd microservice_deployment



```