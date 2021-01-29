
Note : Clone the repository and navigate to the path /K8_infra/Kind 

# Command to list cluster
```
kind get clusters
```

# Command to delete Cluster
```
kind delete cluster --name istiocluster
```


# Command to create Kind cluster 
```
kind create cluster --name istiocluster --config=kindconfig.yaml
```