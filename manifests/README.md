# ArgoCD Installation Manifests

Two sets of installation manifests are provided:

* [install.yaml](install.yaml) - Standard ArgoCD installation with cluster-admin access. Use this
  manifest set if you plan to use ArgoCD to deploy applications in the same cluster that ArgoCD runs
  in (i.e. kubernetes.svc.default). Will still be able to deploy to external clusters with inputted
  credentials.

* [namespace-install.yaml](namespace-install.yaml) - Installation of ArgoCD which requires only
  namespace level privileges (does not need cluster roles). Use this manifest set if you do not
  need ArgoCD to deploy applications in the same cluster that ArgoCD runs in, and will rely solely
  on inputted cluster credentials. An example of using this set of manifests is if you run several
  ArgoCD instances for different teams, where each instance will bedeploying applications to
  external clusters. Will still be possible to deploy to the same cluster (kubernetes.svc.default)
  with inputted credentials (i.e. `argocd cluster add <CONTEXT> --in-cluster`).
