# CephRBD PV file

monitors: Ceph monitors, comma delimited. This parameter is required.

adminId: Ceph client ID that is capable of creating images in the pool. Default is “admin”.

adminSecretNamespace: The namespace for adminSecret. Default is “default”.

adminSecret: Secret Name for adminId. This parameter is required. The provided secret must have type “kubernetes.io/rbd”.

pool: Ceph RBD pool. Default is “rbd”.

userId: Ceph client ID that is used to map the RBD image. Default is the same as adminId.

userSecretName: The name of Ceph Secret for userId to map RBD image. It must exist in the same namespace as PVCs. This 

parameter is required. The provided secret must have type “kubernetes.io/rbd”, e.g. created in this way:

$ kubectl create secret generic ceph-secret --type="kubernetes.io/rbd" --from-literal=key='QVFEQ1pMdFhPUnQrSmhBQUFYaERWNHJsZ3BsMmNjcDR6RFZST0E9PQ==' --namespace=kube-system
fsType: fsType that is supported by kubernetes. Default: "ext4".

imageFormat: Ceph RBD image format, “1” or “2”. Default is “1”.

imageFeatures: This parameter is optional and should only be used if you set imageFormat to “2”. Currently supported features are layering only. Default is “”, and no features are turned on.
