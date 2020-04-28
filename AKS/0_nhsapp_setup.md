# NHSapp's AKS setup

- Ops
  - Azure
    - Traffic Manager
    - Azure Container Registry
    - CosmosDB: `storing session and audit logs`
      - MongoDB
      - SQL
    - AKS
      - k8s v1.15.7 --> v1.15.10
      - arch <https://www.terraform.io/docs/providers/azurerm/r/kubernetes_cluster.html>
        - network_profile
          - network_plugin  = "azure"     #Azure CNI
          - network_policy  = "calico"
          - kube_dashboard disabled

            ```bash
            addon_profile {
              kube_dashboard {
                enabled = false
              }
            }
            ```

        - type              = "AvailabilitySet"
      - ~kube-system
        <!-- Managed by NHSapp team -->
        - cert-manager
          - internal CA
        - collectorforkubernetes
          - logs collector for Splunk
            - comes with collector + Splunk App (dashboards, alerts)
          - paid solution from Outcold Solutions based on collectord
          - <https://www.outcoldsolutions.com/>
        - ingress-nginx
        - helm3 (app, ingress, cert-manager)
        - cluster-autoscaler
        - Twistlock/Prisma Cloud
        - kured
        <!--  -->
        <!-- Managed by Microsoft -->
        - calico
          - network policies controller
        - coredns
        - kube-proxy
        - metrics-server
        - tunnelfront
        <!--  -->
      - ~apps
        - TeamCity
          - dind
        - NHSapp

## Prod network traffic

```bash
Akamai-->Traffic Manager--UKSouth-->AKS ingress-nginx-->...
                        |
                        --UKWest--->AKS ingress-nginx-->...


-->[Nginx Sidecar Proxy (internal TLS)-->Backend/Web]
    ________________________________________________
                        |
                       \_/
                  single k8s pod
```

## Links

- Network concepts in AKS: <https://docs.microsoft.com/en-gb/azure/aks/concepts-network>
- AKS TF resource: <https://www.terraform.io/docs/providers/azurerm/r/kubernetes_cluster.html>
