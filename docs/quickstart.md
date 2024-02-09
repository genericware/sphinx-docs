# Quickstart

A quickstart guide for containerized development.

## Introduction

## Installation

:::{table} Install Toolchains, Command-line Tools, and Libraries
:widths: auto

| Name                                                                                         | Audience (GNU/Linux, macOS, All) | Description                                                                    |
|----------------------------------------------------------------------------------------------|----------------------------------|--------------------------------------------------------------------------------|
|                                                                                              |                                  |                                                                                |
| [kvm](https://wiki.debian.org/KVM)                                                           | GNU/Linux                        | Kernel-based Virtual Machine (KVM)                                             |
| [qemu](https://www.qemu.org/)                                                                | All                              | Quick Emulator (QEMU)                                                          |
| [socket_vmnet](https://formulae.brew.sh/formula/socket_vmnet)                                | macOS                            | Socket interface to [`vmnet`](https://developer.apple.com/documentation/vmnet) |
| [gcloud](https://cloud.google.com/sdk/gcloud/)                                               | All                              | Google Cloud Project (GCP) Command-line Interface                              |
| [terragrunt](https://terragrunt.gruntwork.io/docs/getting-started/install/)                  | All                              | Wrapper for scripting `terraform`                                              |
| [terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli) | All                              | Infrastructure as Code (IaC)                                                   |
| [kubeadm](https://kubernetes.io/docs/tasks/tools/#kubeadm)                                   | GNU/Linux                        | Kubernetes Administration Toolbox                                              |
| [kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl)                                   | All                              |                                                                                |
| [go]()                                                                                       | All                              |                                                                                |
| [typescript]()                                                                               | All                              |                                                                                |
| [pyenv]()                                                                                    | All                              |                                                                                |
| [poetry]()                                                                                   | All                              |                                                                                |
| [minikube](https://kubernetes.io/docs/tasks/tools/#minikube)                                 | All                              |                                                                                |
| [helm]()                                                                                     | All                              |                                                                                | 
| [docker]()                                                                                   | All                              |                                                                                |
| [istioctl]()                                                                                 | All                              |                                                                                |
| [argocd]()                                                                                   | All                              |                                                                                |
| [kn]()                                                                                       | All                              |                                                                                |
| [func]()                                                                                     | All                              |                                                                                |
| [kcat]()                                                                                     | All                              |                                                                                |
| [nvm]()                                                                                      | All                              |                                                                                |
:::

:::{table} Install Development Software
:widths: auto

| name          | description |
|---------------|-------------|
| [KeyPassXC]() |             |
| [Toolbox]()   |             |
| [PyCharm]()   |             |
| [GoLand]()    |             |
| [OpenLens]()  |             |
| [Insomnia]()  |             |
:::

:::{table} Install Jetbrains Plugins
:widths: auto

| name                                                                                                        | description |
|-------------------------------------------------------------------------------------------------------------|-------------|
| [.env files support](https://plugins.jetbrains.com/plugin/9525--env-files-support)                          |             |
| [.ignore](https://plugins.jetbrains.com/plugin/7495--ignore)                                                |             |
| [Conventional Commit](https://plugins.jetbrains.com/plugin/13389-conventional-commit)                       |             |
| [Commitlint Conventional Commit](https://plugins.jetbrains.com/plugin/14046-commitlint-conventional-commit) |             |
| [Go Template](https://plugins.jetbrains.com/plugin/10581-go-template)                                       |             |
| [Ideolog](https://plugins.jetbrains.com/plugin/9746-ideolog)                                                |             |
| [Kubernetes](https://plugins.jetbrains.com/plugin/10485-kubernetes)                                         |             |
| [Terraform and HCL](https://plugins.jetbrains.com/plugin/7808-terraform-and-hcl)                            |             |
| [Mypy](https://plugins.jetbrains.com/plugin/11086-mypy)                                                     |             |
| [Pydantic](https://plugins.jetbrains.com/plugin/12861-pydantic)                                             |             |
| [Mermaid](https://plugins.jetbrains.com/plugin/20146-mermaid)                                               |             |
| [TeXiFy IDEA](https://plugins.jetbrains.com/plugin/9473-texify-idea)                                        |             |
:::

### Kubernetes CRDs

[//]: # (todo: improve recommendation descriptions)

### Recommendations

Jetbrains:
* Add run and debug configurations
* Setup SonarLint connection
* Open all repositories in one IDE window
* Use same branch name for all repositories
* Enable changing zoom within source files using the ctrl + mousewheel
* Use same keymap across all operating systems
* Compile python with profile guided optimizations and link time optimizations
* Maintain latest patch for each stable minor version of python
* Generate virtual environments using pycharm
* Check virtual environments and package dependencies
* View package readmes using pycharm
* Rename and group terminal tabs for repositories
* Split windows while working between multiple files
* Collapse all to reset project view
* Expand all to review commit status
* Use "todo" and "fixme" for highlighted development notes
* Inspect code using problems view
* Type check code using the mypy view
* Model with pydantic for completions and linting
* Check all working branches at same time
* One commit message for multiple repositories
* Run pre-commit checks for multiple repositories

### Cheatsheet

terragrunt:
```shell
# install
cd path/to/project
terragrunt init
terragrunt plan
terragrunt apply

# destroy
terragrunt destroy
```

terraform:
```shell
# install
cd path/to/project
terraform init
terraform plan
terraform apply
```

minikube:
```shell
# install driver
minikube start --driver=<name>
minikube delete

# reset minikube config
rm -rf ~/.minikube
minikube start
minikube delete
```

kubectl
```shell
# get all
kubectl get all --all-namespaces

# get istio external ip
kubectl get service -n istio-ingress istio-ingress -o jsonpath="{.status.loadBalancer.ingress[0].ip}"
```

kustomize:
```shell
# install
kustomize build --enable-helm path/to/kustomization | kubectl apply -f -
```

helm:
```shell
# install

# test

# docs
```
