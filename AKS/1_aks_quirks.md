# AKS quirks and features

AKS is build using automation scripts called AKS-Engine.

```
➜ kubectl get nodes -o wide
NAME                        STATUS   ROLES   AGE     VERSION    INTERNAL-IP   EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION      CONTAINER-RUNTIME
aks-agentpool-28835032-0    Ready    agent   2d11h   v1.15.10   10.20.1.234   <none>        Ubuntu 16.04.6 LTS   4.15.0-1075-azure   docker://3.0.10+azure
```

```
➜ az login
➜ az aks get-versions --location uksouth -o table
KubernetesVersion    Upgrades
-------------------  -----------------------
1.17.3(preview)      None available
1.16.7               1.17.3(preview)
1.15.10              1.16.7
1.15.7               1.15.10, 1.16.7
1.14.8               1.15.7, 1.15.10
1.14.7               1.14.8, 1.15.7, 1.15.10
```

## AKS Container Runtime

```
CONTAINER-RUNTIME: docker://3.0.10+azure
```

AKS nodes are using custom fork of Moby-Engine managed and version by Microsoft.

Moby: <https://github.com/moby/moby>

`The components and tools in the Moby Project are initially the open source components that Docker and the community have built for the Docker Project.`

```
# info from MS
Moby 3.0.8 is like docker v19.03.4
Moby 3.0.7 is like docker v19.03.2
```

```
# docker version
Client:
 Version:           3.0.7
 API version:       1.40

## https://docs.docker.com/engine/api/#api-version-matrix
# We can assume than moby-engine 3.0.7 is based on at least docker engine 19.03 :wink:
Docker version    Maximum API version
19.03    1.40
```

## Storage

Link: <https://kubernetes.io/docs/concepts/storage/persistent-volumes/#types-of-persistent-volumes>

- AzureFile (Azure File Share, Samba (SMB) based, really slow for large amount of small files)
- AzureDisk (Azure Managed Disk, it's dynamically attached to your AKS node whenever k8s master schedules the pod with AzureDisk PV to that node)

Maximum number of Azure Disks which you can attach to your AKS node is strictly determined by your VM (node) flavour/size, i.e.

Standard_DS2_v2
  2vCPUs
  7GB RAM
  Max Data Disks: 8

Standard_DS4_v2
  8vCPUs
  28GB RAM
  Max Data Disks: 32


Link: <https://docs.microsoft.com/en-gb/azure/virtual-machines/sizes-general>
