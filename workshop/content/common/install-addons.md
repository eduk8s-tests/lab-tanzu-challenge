We understand that as Developer or DevOps, you will expect some capabilities to exist in your cluster. For this reason, we want to offload you from the need to install those and we do provide an installer that will install them in your TMC provisioned cluster.

In order for us to provision your cluster from this platform, we would need access to your `kubeconfig` and `tmc` configuration. Hence, we do provide an installer that we expect you to run, but should be really easy.


You only need to execute this in your terminal:

```workshop:copy
text: |
cat <<EOF | kubectl create -f -
kind: Namespace
apiVersion: v1
metadata:
  name: installer
---
kind: ServiceAccount
apiVersion: v1
metadata:
  name: installer
  namespace: installer
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: installer
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
- kind: ServiceAccount
  name: installer
  namespace: installer
---
apiVersion: v1
kind: Pod
metadata:
  labels:
    run: installer
  name: installer
  namespace: installer
spec:
  containers:
  - image: quay.io/failk8s/installer
    name: installer
    command:
      - "/home/kubeuser/install"
      - "{{ ENV_CHALLENGE_PERSONA }}"
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Never
  serviceAccountName: installer
EOF
```

Then, you can monitor the install process by tailing the execution of the installer pod:

```
kubectl logs -f pod/installer -n installer
```