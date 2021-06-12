This document will help you to install nfs server in your ubuntu machine

# Install nfs server
```
sudo apt update
sudo apt install nfs-kernel-server

```

```
vi /etc/exports

```
Add the below line (in place of /srv/data, you can mention any directory path )

```
/srv/data *(rw,sync,no_root_squash,subtree_check)

```
Run below command

```
sudo exportfs -ar

```

# Configure Client Machine

Go to your client machine and run the below command to install the client components

```
sudo apt update
sudo apt install nfs-common
```

```
sudo mount -t nfs -o vers=4 10.157.50.208:/srv/data /srv
```

# Install the kubernetes nfs provisioner

```
sudo apt-get install helm
```

```
$ helm repo add nfs-subdir-external-provisioner https://kubernetes-sigs.github.io/nfs-subdir-external-provisioner/
$ helm install nfs-subdir-external-provisioner nfs-subdir-external-provisioner/nfs-subdir-external-provisioner \
    --set nfs.server=x.x.x.x \
    --set nfs.path=/exported/path
```
