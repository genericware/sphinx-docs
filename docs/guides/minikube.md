# `minikube` usage

This guide covers local cluster initialization using `minikube`.

## Run `minikube` with `terragrunt`

install:
```shell
cd path/to/project
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
minikube delete -p <name>
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



#### GNU/Linux

##### Using `systemd-resolved`

1. Install `systemd-resolved`
   ```shell
   sudo apt-get -y install systemd-resolved
   ```
2. Make directory
   ```shell
   sudo mkdir /etc/systemd/resolved.conf.d
   ```
3. Make DNS Record
   ```shell
   sudo tee /etc/systemd/resolved.conf.d/minikube.conf << EOF
   [Resolve]
   DNS=$(kubectl get service -n istio-ingress istio-ingress -o jsonpath="{.status.loadBalancer.ingress[0].ip}")
   Domains=~test
   EOF
   ```
4. Restart resolved
   ```shell
   sudo systemctl restart systemd-resolved
   ```

##### Using ``

#### macOS

### Enable Ingress

[//]: # (todo: document setting how to set sudoers permissions one-time)
[//]: # (see: https://superuser.com/questions/1328452/sudoers-nopasswd-for-single-executable-but-allowing-others)
[//]: # (see: https://serverfault.com/questions/1110340/executing-a-command-without-password-prompt-or-root)

1. open new terminal window
2. provide load balancing services
    ```shell
    minikube tunnel
    ```

### Enable HTTPS

[//]: # (todo: add certificate steps for chrome and safari)

1. export ca cert
    ```shell
    kubectl get -n cert-manager secret istio-ca -ogo-template='{{index .data "tls.crt"}}' | base64 -d > ca.pem
    ```
2. Add Root CA Certificate to browser
   * Firefox: settings > privacy & security > view certificates > authorities > import > (select `ca.pem`) > trust to identify websites


[//]: # (todo: document kvm2 gpu usage)
[//]: # (see: https://minikube.sigs.k8s.io/docs/tutorials/nvidia/)

## Services

| name                                                                     | login                                                          | description                              |
|--------------------------------------------------------------------------|----------------------------------------------------------------|------------------------------------------|
| [argocd](https://argocd.development.local.generic-infrastructure.test)   | `admin` / `test`                                               | login for continuous delivery service    |
| [grafana](https://grafana.development.local.generic-infrastructure.test) | `admin` / `prom-operator`                                      | login for observability service          |
| [kiali](https://kiali.development.local.generic-infrastructure.test)     | `kubectl -n istio-system create token kiali-service-account`   | login for network administration service |
| [minio](https://minio.development.local.generic-infrastructure.test)     | `admin` / `testtesttest`                                       | login for object store                   |

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

### Fallback when there's DNS issues reaching ArgoCD
1. Open a new terminal window
2. Start port-forwarding
    ```shell
    kubectl port-forward -n argocd services/argocd-server 8080:443
    ```
3. Visit [https://localhost:8080/](https://localhost:8080/)
4. Retrieve initial admin secret
   ```shell
   kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
   ```
