We understand that as Developer or DevOps, you will expect some capabilities to exist in your cluster. For this reason, we want to offload you from the need to install those and we do provide an installer that will install them in your TMC provisioned cluster.

You only need to provide your kubeconfig file here and then run this script:

```terminal:execute
command: installer/install --kubeconfig <FILE>
session: 1
```