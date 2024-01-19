# Design

## Cluster Initialization

[//]: # (todo: terragrunt, terraform cycle prior to `app-of-apps`)

The cluster is initialized using [waves](https://argo-cd.readthedocs.io/en/stable/user-guide/sync-waves/). 
ArgoCD waits for healthy resources at each wave before continuing.

| name                            | resource type (crd, chart, kustomization) | resources                      | wave  |
|---------------------------------|-------------------------------------------|--------------------------------|-------|
| project                         | crd                                       | `AppProject`                   | -230  | 
| istio definitions & resources   | chart                                     | `base`                         | -220  | 
| istio daemon                    | chart                                     | `istiod`                       | -210  | 
| istio ingress gateway           | chart                                     | `gateway`                      | -200  | 
| certificate manager             | chart                                     | `cert-manager`                 | -190  | 
| cluster issuer & ca certificate | crd                                       | `ClusterIssuer`, `Certificate` | -180  | 
| etc. certificates               | crd                                       | `Certificate`                  | -170  | 
| gateways                        | crd                                       | `Gateway`                      | -160  | 
| virtual services                | crd                                       | `VirtualService`               | -150  |
| peer authentication             | crd                                       | `PeerAuthentication`           | -140  |
| kiali operator                  | chart                                     | `kiali-operator`               | -130  |
| argocd                          | chart                                     | `argo-helm`                    | -120  |
| knative-operator                | kustomization                             | `knative-operator`             | -110  |
| knative-serving                 | kustomization                             | `knative-serving`              | -100  |
| knative-eventing                | kustomization                             | `knative-eventing`             | -90   |
| prometheus operator & grafana   | chart                                     | `kube-prometheus-stack`        | -80   |
| rook ceph operator              | chart                                     | `rook-ceph-operator`           | -70   |
| loki                            | chart                                     | `loki-distributed`             | -60   |
| promtail                        | chart                                     | `promtail`                     | -50   |
| tempo                           | chart                                     | `tempo-distributed`            | -40   |
| strimzi kafka operator          | chart                                     | `strimzi-kafka-operator`       | -30   |
| mysql operator                  | chart                                     | `mysql-operator`               | -20   |
| mongodb operator                | chart                                     | `mongodb-kubernetes-operator`  | -10   |
| tenants                         | chart                                     | `tenant`                       | 0     |

[//]: # (todo: tenant chart)
