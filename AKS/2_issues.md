# AKS - issues

1. Python 3.8 (Alpine 3.11) removed support for `time.clock` function and the most of Ansible Azure modules are using it, so to fix it we needed to downgrade the version of Python to 3.7 (Alpine 3.10)
<https://github.com/ansible/ansible/issues/67473>
<https://github.com/VSChina/ansible-issue-tracker/issues/1295>
<https://pkgs.alpinelinux.org/packages?name=python3&branch=v3.10>
<https://bugs.python.org/issue36895>

2. CoreDNS update took 4 months:
<https://github.com/Azure/AKS/issues/1304#issue-519474976>

3. MS started using VMSS by default when it wasn't production ready and multiple issues were raised:

   - AKS Latency and performance/availability issues due to IO saturation and throttling under load: <https://github.com/Azure/AKS/issues/1373>
   - AKS ARM/VMSS Throttling: <https://github.com/Azure/AKS/issues/1413>

4. If you are using any external software to manage your cluster internally (cert-manager, cluster-autoscaler, kube-router, ingress-nginx), Microsoft will not support it at all, if there's possibility that your deployed software can have any (even small) impact on the issue which you are raising - you will need to deal with it on your own.

   ```
   # MS Support respond
   The customer isn't using the managed AKS autoscaler. We only support managed AKS autoscaler: https://docs.microsoft.com/en-us/azure/aks/cluster-autoscaler and unmanaged autoscaler is out of support scope.
   The unmanaged autoscaler deletes the VMs directly during scale-in which might leave trailing NICs behind.
   If the customer is still experiencing issues with the unmanaged autoscaler, please let them know, that they can file an issue on the GitHub project: https://github.com/kubernetes/autoscaler/issues
   ```

5. We had occasionally internal networking issues in the past (kube-proxy), but we are not experiencing them for a very long time now (since Feb 2019).

   - besides a small episode on 20.03.2020 `k8s is not capable to assign public IP to loadbalancer type of service`

6. Azure Network Policies Engine doesn't work for us, when we tested it 08.08.2019 (It was already GA)

7. Cert-manager were constantly recreating Let's Encrypt certs (Azure DNS challenge) and we were reaching LE rate limits. That's why we migrated to custom LE Ansible script for managing LE certs in k8s. (March-May 2018, can be no longer valid)

Azure DNS-01 challenge causing panic: <https://github.com/jetstack/cert-manager/issues/593>

8. k8s version bump issues, we are not encountering any issues since Nov 2018

- 1.13.5 Oct 2019 <https://github.com/Azure/AKS/issues/1245>
- 1.14.6 Sep 2019 <https://github.com/Azure/AKS/issues/1202>
- 1.7.7 Nov 2017 <https://github.com/Azure/AKS/issues/61>

## ksniff

Link: <https://github.com/eldadru/ksniff>

## Links

- LE rate limits: <https://letsencrypt.org/docs/rate-limits/>
