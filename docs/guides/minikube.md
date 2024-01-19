# `minikube` usage

This guide covers local cluster initialization using `minikube`.

## Run `minikube` with `terragrunt`

install:
```shell
terragrunt init
terragrunt plan
terragrunt apply
```

uninstall:
```shell
terragrunt destroy
```

uninstall(force):
```shell
minikube delete
```

## Run `minikube` with `terraform`

install:
```shell
terraform init
terraform plan
terraform apply
```

uninstall:
```shell
terraform destroy
```

uninstall(force):
```shell
minikube delete
```

### Enable DNS

[//]: # (todo: attempt removing step; see static-ip, dnsmasq, metallb)
[//]: # (todo: see: https://minikube.sigs.k8s.io/docs/tutorials/static_ip/)

1. retrieve `external-ip`
    ```shell
    kubectl get -n istio-ingress services
    ```
2. edit `/etc/hosts`
    ```shell
    sudo nano /etc/hosts
    ```
3. add A records
    ```text
    <external-ip> argocd.development.local.generic-infrastructure.com
    <external-ip> grafana.development.local.generic-infrastructure.com
    <external-ip> kiali.development.local.generic-infrastructure.com
    <external-ip> minio.development.local.generic-infrastructure.com
    <external-ip> api.development.local.generic-infrastructure.com
    ```

### Enable Ingress

[//]: # (todo: remove need for sudo by setting exact sudoers permissions one-time)
[//]: # (todo: see: https://superuser.com/questions/1328452/sudoers-nopasswd-for-single-executable-but-allowing-others)
[//]: # (todo: see: https://serverfault.com/questions/1110340/executing-a-command-without-password-prompt-or-root)

1. open new terminal window
2. provide load balancing services
    ```shell
    minikube tunnel
    ```

### Enable HTTPS

[//]: # (todo: update organization certificate; validate tls setup and certificate chain)
[//]: # (todo: add steps for chrome and safari)

1. export ca cert
    ```shell
    kubectl get -n cert-manager secret istio-ca -ogo-template='{{index .data "tls.crt"}}' | base64 -d > ca.pem
    ```
2. add cert to browser
   * firefox: settings > privacy & security > view certificates > authorities > import > (select `ca.pem`) > trust to identify websites
   
[//]: # (todo: enable gpu; kvm2 driver only; see: https://minikube.sigs.k8s.io/docs/tutorials/nvidia/)

## Services

| name                                                                    | login                                                          | description                              |
|-------------------------------------------------------------------------|----------------------------------------------------------------|------------------------------------------|
| [argocd](https://argocd.development.local.generic-infrastructure.com)   | `admin` / `test`                                               | login for continuous delivery service    |
| [grafana](https://grafana.development.local.generic-infrastructure.com) | `admin` / `prom-operator`                                      | login for observability service          |
| [kiali](https://kiali.development.local.generic-infrastructure.com)     | `kubectl -n istio-system create token kiali-service-account`   | login for network administration service |
| [minio](https://minio.development.local.generic-infrastructure.com)     | `admin` / `testtesttest`                                       | login for object store                   |

## Troubleshooting

### driver fix-all
1. Remove the local `minikube` cache within the home folder
    ```shell
    rm -r ~/.minikube
    ```
2. Start `minikube` with the specified driver (e.g. `kvm2`)
    ```shell
    minikube start --driver=kvm2
    ```
3. Delete minikube cluster
    ```shell
    minikube delete
    ```

### fix dns issue reaching argocd
1. Open a new terminal window
2. Start port-forwarding
    ```shell
    kubectl port-forward -n argocd services/argo-cd-argocd-server 8080:443
    ```
3. Visit [https://localhost:8080/](https://localhost:8080/)
