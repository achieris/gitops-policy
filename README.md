
#  gitops-policy

This project contains the policy and placement manifests to install and configure OpenShift GitOps. 

The *policies/gitops* folder contains the manifests of the subscription, argocd instance and cluster role binding, that are deployed on all managed clusters using the all-clusters-policyGenerator.yaml, moreover there are the clusterset, clustersetbinding, placement and gitopscluster that are deployed on the cluster hub using the cluster-hub-policyGenerator.yaml. 


The *rhacm* folder contains the placementrules used in the policy generators. 

```
.
├── policies 
│   └── gitops
│       ├── all-clusters  
│       │   ├── argocd.yaml
│       │   ├── cluster-admin-gitops.yaml
│       │   └── gitops-operator-sub.yaml
│       ├── all-clusters-policyGenerator.yaml
│       ├── cluster-hub
│       │   ├── gitopscluster.yaml
│       │   ├── managed-cluster-set-binding.yaml
│       │   ├── managed-cluster-set.yaml
│       │   └── placement.yaml
│       ├── cluster-hub-policyGenerator.yaml
│       └── kustomization.yaml
└── rhacm
    ├── all-clusters-placement-rule.yaml
    └── cluster-hub-placement-rule.yaml

```


## Usage

```
cd rhacm

oc apply -f . 

cd policies/gitops

oc apply -k . 

```
