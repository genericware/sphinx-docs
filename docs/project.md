# Project

## Maintainers

| Name          | Username                                        | Contact                         | Role |
|---------------|-------------------------------------------------|---------------------------------|------|
| Andrew Linzie | [caerulescens](https://github.com/caerulescens) | `caerulescens.github@proton.me` | BDFL |

## Issue Tracking

:::{table} YouTrack JetBrains IDE issues
:widths: auto

| Id                                                                                                                              | State     | Description                                                                                 |
|---------------------------------------------------------------------------------------------------------------------------------|-----------|---------------------------------------------------------------------------------------------|
| [PY-61291](https://youtrack.jetbrains.com/issue/PY-61291/Support-MyST-syntax)                                                   | `preview` | PyCharm support for [MyST](https://myst-parser.readthedocs.io/en/latest/index.html#) syntax | 
| [IDEA-313978](https://youtrack.jetbrains.com/issue/IDEA-313978/Terraform-and-HCL-plugin-does-not-support-formatting-.hcl-files) | `open`    | Terraform and HCL plugin support for `*.hcl` files                                          | 
| [IDEA-332935](https://youtrack.jetbrains.com/issue/IDEA-332935/Autocomplete-fails-for-locals-reference-in-HCL)                  | `open`    | Autocomplete fails for `locals` referenced in `*.hcl` files                                 |
:::

:::{table} Tracking GitHub issues
:widths: auto

| Repository                                         | Issue                                                                                  | State  | Description                                                                                         |
|----------------------------------------------------|----------------------------------------------------------------------------------------|--------|-----------------------------------------------------------------------------------------------------|
| `tiangolo/sqlmodel`                                | [#654](https://github.com/tiangolo/sqlmodel/issues/654)                                | `open` | Roadmap for official `fastapi`+`sqlalchemy`+`pydantic`+`alembic`+`typer` support, async tools, docs |
| `scott-the-programmer/terraform-provider-minikube` | [#120](https://github.com/scott-the-programmer/terraform-provider-minikube/issues/120) | `open` | Support for launching `minikube` using [`opentofu`](https://opentofu.org/)                          |
:::

## Source Code

:::{table} generic-infrastructure
:widths: auto

| Name                                                                                               | Description                                                                                                                                                  |
|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [cookiecutter-terragrunt](https://github.com/generic-infrastructure/cookiecutter-terragrunt)       | [`cookiecutter`](https://github.com/cookiecutter/cookiecutter) template for [`terragrunt`](https://github.com/gruntwork-io/terragrunt) projects.             |
| [cookiecutter-fastapi](https://github.com/generic-infrastructure/cookiecutter-fastapi)             | [`cookiecutter`](https://github.com/cookiecutter/cookiecutter) template for [`fastapi`](https://github.com/tiangolo/fastapi) projects.                       |
| [cookiecutter-poetry](https://github.com/generic-infrastructure/cookiecutter-poetry)               | [`cookiecutter`](https://github.com/cookiecutter/cookiecutter) template for [`poetry`](https://github.com/python-poetry/poetry) projects.                    |
| [cookiecutter-terraform](https://github.com/generic-infrastructure/cookiecutter-terraform)         | [`cookiecutter`](https://github.com/cookiecutter/cookiecutter) template for [`terraform`](https://github.com/hashicorp/terraform) projects.                  |
| [helm-app-of-apps](https://github.com/generic-infrastructure/helm-app-of-apps)                     | Application that launches other applications.                                                                                                                |
| [helm-tenant](https://github.com/generic-infrastructure/helm-tenant)                               | Application that launches tenant specific resources.                                                                                                         |
| [next-frontend](https://github.com/generic-infrastructure/next-frontend)                           | Front-end based on [`Next.js`](https://github.com/vercel/next.js/).                                                                                          |
| [sphinx-docs](https://github.com/generic-infrastructure/sphinx-docs)                               | [`sphinx`](https://github.com/sphinx-doc/sphinx) documentation containing designs, guides, research, and notes.                                              |
| [terraform-gke-cluster](https://github.com/generic-infrastructure/terraform-gke-cluster)           | [`terraform`](https://github.com/hashicorp/terraform) project for launching [`gke`](https://cloud.google.com/kubernetes-engine/) clusters.                   |
| [terraform-minikube-cluster](https://github.com/generic-infrastructure/terraform-minikube-cluster) | [`terraform`](https://github.com/hashicorp/terraform) project for launching [`minikube`](https://github.com/kubernetes/minikube) clusters.                   |
| [terragrunt-devops](https://github.com/generic-infrastructure/terragrunt-devops)                   | [`kubernetes`](https://github.com/kubernetes/kubernetes) cluster development operations based on [`terragrunt`](https://github.com/gruntwork-io/terragrunt). |

:::

:::{table} GitHub Actions
:widths: auto

| Name                                                                                | Description                         |
|-------------------------------------------------------------------------------------|-------------------------------------|
| [medyagh/setup-minikube](https://github.com/medyagh/setup-minikube)                 | Installing and running `minikube`   |
| [gruntwork-io/terragrunt-action](https://github.com/gruntwork-io/terragrunt-action) | Installing and running `terragrunt` |
| [hashicorp/setup-terraform](https://github.com/hashicorp/setup-terraform)           | Installing and running `terraform`  |
| [imranismail/setup-kustomize](https://github.com/imranismail/setup-kustomize)       | Installing and running `kustomize`  |
| [helm/chart-testing-action](https://github.com/helm/chart-testing-action)           | Lint and test `helm` charts         |
| [actions/setup-python](https://github.com/actions/setup-python)                     | Installing and running `python`     |
| [pre-commit/action](https://github.com/pre-commit/action)                           | Installing and running `pre-commit` |
:::

:::{table} Pre-commit hooks
:widths: auto

| Name                                                                                               | Description                                              |
|----------------------------------------------------------------------------------------------------|----------------------------------------------------------|
| [gruntwork-io/pre-commit](https://github.com/gruntwork-io/pre-commit)                              | `terragrunt`, `terraform`, `helm`, `go`, and shell hooks | 
| [terraform-docs/terraform-docs](https://github.com/terraform-docs/terraform-docs/#pre-commit-hook) | `terraform` doc hooks                                    | 
| [norwoodj/helm-docs](https://github.com/norwoodj/helm-docs#pre-commit-hook)                        | `helm` doc hooks                                         | 
| [pre-commit/pre-commit-hooks](https://github.com/pre-commit/pre-commit-hooks)                      | `python` hooks                                           |
| [pre-commit/pygrep-hooks](https://github.com/pre-commit/pygrep-hooks)                              | `python` regex hooks                                     | 
| [pre-commit/mirrors-mypy](https://github.com/pre-commit/mirrors-mypy)                              | `python` type checking hooks                             |
| [astral-sh/ruff-pre-commit](https://github.com/astral-sh/ruff-pre-commit)                          | `python` linting & formatting hooks                      | 
| [psf/black](https://github.com/psf/black)                                                          | `python` formatting hooks                                |
:::

:::{table} Terraform Providers
:widths: auto

| Name                                                                                                                    | Description                    |
|-------------------------------------------------------------------------------------------------------------------------|--------------------------------|
| [scott-the-programmer/terraform-provider-minikube](https://github.com/scott-the-programmer/terraform-provider-minikube) | `minikube` cluster             |
| [hashicorp/terraform-provider-google](https://github.com/hashicorp/terraform-provider-google)                           | Google Cloud Project resources |
:::

:::{table} Helm Charts
:widths: auto

| Name                                                                                                                                     | Description                     |
|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
| [argoproj/argo-helm](https://github.com/argoproj/argo-helm)                                                                              | Continuous delivery             |
| [cert-manager/cert-manager](https://github.com/cert-manager/cert-manager)                                                                | Issuer & certificate automation |
| [keycloak](https://github.com/codecentric/helm-charts/tree/master/charts/keycloakx)                                                      | Identity & access management    |
| [oauth2-proxy](https://github.com/oauth2-proxy/manifests/tree/main/helm/oauth2-proxy)                                                    | OAuth reverse proxy             | 
| [istio/istio-base](https://github.com/istio/istio/tree/master/manifests/charts/base)                                                     | Network base definitions        |
| [istio/istio-ingress](https://github.com/istio/istio/tree/master/manifests/charts/gateways/istio-ingress)                                | Network ingress gateway         |
| [istio/istiod](https://github.com/istio/istio/tree/master/manifests/charts/istio-control/istio-discovery)                                | Network daemon                  |
| [kiali/kiali-operator](https://github.com/kiali/kiali-operator)                                                                          | Network portal                  |
| [prometheus-community/kube-prometheus-stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack) | Metrics & visualization         |
| [grafana/loki-distributed](https://github.com/grafana/helm-charts/tree/main/charts/loki-distributed)                                     | Distributed logging             |
| [mysql/mysql-operator](https://github.com/mysql/mysql-operator)                                                                          | SQL  storage                    |
| [mongodb/mongodb-kubernetes-operator](https://github.com/mongodb/mongodb-kubernetes-operator)                                            | Document storage                |
| [minio/minio](https://github.com/minio/minio/blob/master/helm/minio/README.md)                                                           | S3 storage                      |
| [grafana/promtail](https://github.com/grafana/helm-charts/blob/main/charts/promtail/README.md)                                           | Log collector & post processor  |
| [strimzi/strimzi-kafka-operator](https://github.com/strimzi/strimzi-kafka-operator)                                                      | Event broker                    |
| [grafana/tempo-distributed](https://github.com/grafana/helm-charts/blob/main/charts/tempo-distributed/README.md)                         | Distributed tracing             |
:::

:::{table} Go
:widths: auto

[//]: # (todo: tekton)
| Name                                                                                        | Description                        |
|---------------------------------------------------------------------------------------------|------------------------------------|
| [knative/operator](https://github.com/knative/operator)                                     | Cloud microservice framework       |
| [knative/serving](https://github.com/knative/serving)                                       | Microservice server hosting        |
| [knative/eventing](https://github.com/knative/eventing)                                     | Microservice event delivery        |
| [knative-extensions/net-istio](https://github.com/knative-extensions/net-istio)             | Istio network integration          |
| [knative-extensions/net-certmanager](https://github.com/knative-extensions/net-certmanager) | `cert-manager` network integration |
| [knative-extensions/eventing-kafka](https://github.com/knative-extensions/eventing-kafka)   | Kafka event integration            |
| [knative/client](https://github.com/knative/client)                                         | Knative cli                        |
| [knative/func](https://github.com/knative/func)                                             | Knative functions cli              |
:::

:::{table} Python
:widths: auto

[//]: # (todo: add cloudevents)
[//]: # (todo: hypercorn + trio)
[//]: # (todo: kafka client driver)
[//]: # (todo: s3 client driver)
| Name                                                                                                                          | Description                                    |
|-------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------|
| [encode/uvicorn](https://github.com/encode/uvicorn)                                                                           | ASGI web server                                |
| [MagicStack/uvloop](https://github.com/MagicStack/uvloop)                                                                     | Cython event loop                              |
| [ijl/orjson](https://github.com/ijl/orjson)                                                                                   | JSON serialization & deserialization           |
| [mpdavis/python-jose](https://github.com/mpdavis/python-jose)                                                                 | JavaScript object signing and encryption       |
| [tiangolo/fastapi](https://github.com/tiangolo/fastapi)                                                                       | ASGI server framework                          |
| [fastapi-users/fastapi-users](https://github.com/fastapi-users/fastapi-users)                                                 | MySQL & MongoDB user authentication            |
| [pydantic/pydantic](https://github.com/pydantic/pydantic)                                                                     | Modeling & validation                          |
| [pydantic/pydantic-settings](https://github.com/pydantic/pydantic-settings)                                                   | Settings modeling & validation                 |
| [tiangolo/sqlmodel](https://github.com/tiangolo/sqlmodel)                                                                     | ORM modeling & validation                      |
| [sqlalchemy/sqlalchemy](https://github.com/sqlalchemy/sqlalchemy)                                                             | SQL toolkit & ORM                              |
| [roman-right/beanie](https://github.com/roman-right/beanie)                                                                   | Object document manager                        |
| [alembic/alembic](https://github.com/alembic/alembic)                                                                         | Database migration tool                        |
| [long2ice/asyncmy](https://github.com/long2ice/asyncmy)                                                                       | Cython database driver                         |
| [Delgan/loguru](https://github.com/Delgan/loguru)                                                                             | Logging implementation                         |
| [trallnag/prometheus-fastapi-instrumentator](https://github.com/trallnag/prometheus-fastapi-instrumentator)                   | ASGI middleware for metrics                    |
| [open-telemetry/opentelemetry-instrumentation-fastapi](https://github.com/open-telemetry/opentelemetry-python-contrib)        | ASGI middleware for traces                     |
| [open-telemetry/opentelemetry-exporter-otlp](https://github.com/open-telemetry/opentelemetry-python)                          | ASGI middleware for exporting traces           |
| [pytest-dev/pytest](https://github.com/pytest-dev/pytest)                                                                     | Test framework                                 |
| [pytest-dev/pytest-asyncio](https://github.com/pytest-dev/pytest-asyncio)                                                     | `pytest` plugin for async tests                |
| [pytest-dev/pytest-cov](https://github.com/pytest-dev/pytest-cov)                                                             | `pytest` plugin for test coverage              |
| [igortg/pytest-async-sqlalchemy](https://github.com/igortg/pytest-async-sqlalchemy)                                           | `pytest` plugin for `sqlalchemy`               |
| [ClearcodeHQ/pytest-mysql](https://github.com/ClearcodeHQ/pytest-mysql)                                                       | `pytest` plugin for MySQL                      |
| [ClearcodeHQ/pytest-mongo](https://github.com/ClearcodeHQ/pytest-mongo)                                                       | `pytest` plugin for MongoDB                    |
| [pnuckowski/aioresponses](https://github.com/pnuckowski/aioresponses)                                                         | `pytest` plugin for async responses            |
| [GoogleCloudPlatform/terraform-python-testing-helper](https://github.com/GoogleCloudPlatform/terraform-python-testing-helper) | `pytest` plugin for `terragrunt` & `terraform` |
| [tox-dev/tox](https://github.com/tox-dev/tox)                                                                                 | Test automation                                |
| [psf/black](https://github.com/psf/black)                                                                                     | Formatting                                     |
| [astral-sh/ruff](https://github.com/astral-sh/ruff)                                                                           | Linting                                        |
| [python/mypy](https://github.com/python/mypy)                                                                                 | Type checking                                  |
| [sphinx-doc/sphinx](https://github.com/sphinx-doc/sphinx)                                                                     | Documentation                                  |
| [readthedocs/sphinx_rtd_theme](https://github.com/readthedocs/sphinx_rtd_theme)                                               | Documentation theme                            |
| [executablebooks/myst-parser](https://github.com/executablebooks/MyST-Parser)                                                 | Documentation plugin for Markdown              |
:::
