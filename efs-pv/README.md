# EFS Persistent volume

create an EFS and hook it up to a persistent volume on EKS

## EFS CSI Driver
- Installation of EFS CSI driver by following these instructions: https://docs.aws.amazon.com/eks/latest/userguide/efs-csi.html
- EFS CSI Driver K8s manifests from here: https://github.com/kubernetes-sigs/aws-efs-csi-driver/tree/master/deploy/kubernetes/base
  - [Static provisioning instructions](https://github.com/kubernetes-sigs/aws-efs-csi-driver/tree/master/examples/kubernetes/static_provisioning)

CFN & some kube templates need to be deployed using [iidy](https://github.com/unbounce/iidy)


To test that the pods are writing to EFS: 
```sh
kubectl exec -ncarmen-test -ti $POD_NAME -- tail -f /data/carmen/output.txt
```
