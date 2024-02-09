[//]: # (todo: demo docs first draft)
# Demo

A list of feature demos.

## Prerequisites

* Install tools from [Quickstart](quickstart.md)

---

## `cookiecutter-terragrunt`

```shell
git clone git@github.com:generic-infrastructure/cookiecutter-terragrunt.git
cd cookiecutter-terragrunt
poetry install
poetry shell
cookiecutter .
```

### Cluster Engine(s)

| Option     | Description                      |
|------------|----------------------------------|
| `none`     | Generate with essential todos    |
| `kvm2`     | Generate with `kvm2` support     |
| `qemu2`    | Generate with `qemu2` support    |
| `hyperkit` | Generate with `hyperkit` support |
| `gke`      | Generate with `gke` support      |

### Name Cluster(s)

### `tox` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

### `pre-commit` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

### `sphinx` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

---

## `cookiecutter-fastapi`

```shell
git clone git@github.com:generic-infrastructure/cookiecutter-fastapi.git
cd cookiecutter-fastapi
poetry install
poetry shell
cookiecutter .
```

### Database

| option    | description                     |
|-----------|---------------------------------|
| `none`    | Generate with essential todos   | 
| `mysql`   | Generate with `mysql` support   |
| `mongodb` | Generate with `mongodb` support |

### Authentication Backend(s)

#### Transport(s)

| option   | description      |
|----------|------------------|
| `cookie` | Use cookie       |
| `bearer` | Use bearer token |

#### Strategy(s)

| option     | description           |
|------------|-----------------------|
| `database` | Use SQL-like database |
| `jwt`      | Use JSON web tokens   |
| `redis`    | Use `redis` cache     |

### OAuth2 Support

| option | description     |
|--------|-----------------|
| `no`   | Disable support | 
| `yes`  | Enable support  |

### `tox` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

### `pre-commit` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

### `sphinx` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

---

## `cookiecutter-poetry`

```shell
git clone git@github.com:generic-infrastructure/cookiecutter-poetry.git
cd cookiecutter-poetry
poetry install
poetry shell
cookiecutter .
```

### C Extension Support

| option   | description                  |
|----------|------------------------------|
| `none`   | Disable C Extension Support  |
| `cffi`   | C Foreign Function Interface | 
| `cython` | Cython Static Compiler       |

### `tox` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

### `pre-commit` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

### `sphinx` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

---

## `cookiecutter-terraform`

```shell
git clone git@github.com:generic-infrastructure/cookiecutter-terraform.git
cd cookiecutter-terraform
poetry install
poetry shell
cookiecutter .
```

### Backend

### Provider(s)

### `tox` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

### `pre-commit` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

### `sphinx` Support

| Option | Description |
|--------|-------------|
| `no`   | Disable     | 
| `yes`  | Enable      |

---

## `helm-app-of-apps`

---

## `helm-tenant`

---

## `sphinx-docs`

---

## `terraform-gke-cluster`

---

## `terraform-minikube-cluster`

---

## `terragrunt-devops`

```shell
git clone git@github.com:generic-infrastructure/terragrunt-devops.git
cd terragrunt-devops
poetry install
poetry shell
```

### Run a Kubernetes Cluster

#### GNU/Linux `kvm2` Demo Profile

```shell
cd live/development/local/minikube/demo/dev-local-kvm2
cat <<EOF > terraform.tfvars

EOF
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### GNU/Linux `qemu2` Demo Profile

```shell
cd live/development/local/minikube/demo/dev-local-qemu2
cat <<EOF > terraform.tfvars

EOF
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### macOS `hyperkit` Demo Profile

```shell
cd live/development/local/minikube/demo/dev-local-hyperkit
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### macOS `qemu2` Demo Profile

```shell
cd live/development/local/minikube/demo/dev-local-qemu2
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### GNU/Linux `kvm2` Default Profile

```shell
cd live/development/local/minikube/default/dev-local-kvm2
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### GNU/Linux `qemu2` Default Profile

```shell
cd live/development/local/minikube/default/dev-local-qemu2
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### macOS `hyperkit` Default Profile

```shell
cd live/development/local/minikube/default/dev-local-hyperkit
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### macOS `qemu2` Default Profile

```shell
cd live/development/local/minikube/default/dev-local-qemu2
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### `gke` Staging Default Profile

```shell
cd live/staging/us-east1-b/gke/default/stg-us-east1-b-gke
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

#### `gke` Production Default Profile

```shell
cd live/production/us-east1-b/gke/default/prd-us-east1-b-gke
terragrunt init
terragrunt plan -out 'tfplan'
terragrunt apply 'tfplan'
```

### Start the Cluster Software Manager

#### `minikube` Development Demo Profile

```shell
kustomize build --enable-helm k12s/argocd/overlays/minikube-development-demo | kubectl apply -f -
```

#### `minikube` Development Default Profile

```shell
kustomize build --enable-helm k12s/argocd/overlays/minikube-development-default | kubectl apply -f -
```

#### `gke` Staging Default Profile

```shell
kustomize build --enable-helm k12s/argocd/overlays/gke-staging-default | kubectl apply -f -
```

#### `gke` Production Default Profile

```shell
kustomize build --enable-helm k12s/argocd/overlays/gke-production-default | kubectl apply -f -
```

### Bootstrap the Cluster Software

#### `minikube` Development Demo Profile

```shell
kustomize build --enable-helm k12s/app-of-apps/overlays/minikube-development-demo | kubectl apply -f -
```

#### `minikube` Development Default Profile

```shell
kustomize build --enable-helm k12s/app-of-apps/overlays/minikube-development-default | kubectl apply -f -
```

#### `gke` Staging Default Profile

```shell
kustomize build --enable-helm k12s/app-of-apps/overlays/gke-staging-default | kubectl apply -f -
```

#### `gke` Production Default Profile

```shell
kustomize build --enable-helm k12s/app-of-apps/overlays/gke-production-default | kubectl apply -f -
```

### Destroy the Cluster

```shell
terragrunt destroy
```
