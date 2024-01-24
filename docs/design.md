# Design

## Kubernetes Cluster

## Requirements

[//]: # (helm; v3.x or later)
[//]: # (tekton; k8s v1.23 or later)
[//]: # (rook; k8s v1.22 or later)

### Initialization

The cluster is initialized using [waves](https://argo-cd.readthedocs.io/en/stable/user-guide/sync-waves/). 
ArgoCD waits for healthy resources at each wave before continuing.

| name                            | resource type (crd, chart, kustomization) | resources                      | wave |
|---------------------------------|-------------------------------------------|--------------------------------|------|
| project                         | crd                                       | `AppProject`                   | -230 | 
| istio definitions & resources   | chart                                     | `base`                         | -220 | 
| istio daemon                    | chart                                     | `istiod`                       | -210 | 
| istio ingress gateway           | chart                                     | `gateway`                      | -200 | 
| certificate manager             | chart                                     | `cert-manager`                 | -190 | 
| cluster issuer & ca certificate | crd                                       | `ClusterIssuer`, `Certificate` | -180 | 
| etc. certificates               | crd                                       | `Certificate`                  | -170 | 
| keycloak                        | crd                                       | `keycloak`                     | -160 | 
| oauth2-proxy                    | crd                                       | `oauth2-proxy`                 | -150 |
| peer authentication             | crd                                       | `PeerAuthentication`           | -140 |
| kiali operator                  | chart                                     | `kiali-operator`               | -130 |
| kiali gateway                   | crd                                       | `Gateway`                      | -129 |
| kiali virtual service           | crd                                       | `VirtualService`               | -128 |
| argocd                          | chart                                     | `argo-helm`                    | -120 |
| argocd gateway                  | crd                                       | `Gateway`                      | -119 |
| argocd virtual service          | crd                                       | `VirtualService`               | -118 |
| knative-operator                | kustomization                             | `knative-operator`             | -110 |
| knative-serving                 | kustomization                             | `knative-serving`              | -100 |
| knative-eventing                | kustomization                             | `knative-eventing`             | -90  |
| prometheus operator stack       | chart                                     | `kube-prometheus-stack`        | -80  |
| grafana gateway                 | crd                                       | `Gateway`                      | -79  |
| grafana virtual service         | crd                                       | `VirtualService`               | -78  |
| rook ceph operator              | chart                                     | `rook-ceph-operator`           | -70  |
| loki                            | chart                                     | `loki-distributed`             | -60  |
| promtail                        | chart                                     | `promtail`                     | -50  |
| tempo                           | chart                                     | `tempo-distributed`            | -40  |
| strimzi kafka operator          | chart                                     | `strimzi-kafka-operator`       | -30  |
| mysql operator                  | chart                                     | `mysql-operator`               | -20  |
| mongodb operator                | chart                                     | `mongodb-kubernetes-operator`  | -10  |
| tenants                         | chart                                     | `tenant`                       | 0    |
