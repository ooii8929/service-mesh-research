# service-mesh-research

# init infra
```
terraform init
terraform plan
terraform apply
```

# install istio-base with helm
# https://istio.io/latest/docs/setup/install/helm/
```
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update
# check repo update
helm repo list
cd helm
helm pull istio/base
cd base
helm install --namespace istio-system --create-namespace istio-base .
```

# install istio-base with helm
# https://istio.io/latest/docs/setup/install/helm/
```
helm repo add istio https://istio-release.storage.googleapis.com/charts
helm repo update
# check repo update
helm repo list
cd helm
helm pull istio/istiod
tar -xzf istiod-1.21.0.tgz
rm istiod-1.21.0.tgz
cd istiod
helm install --namespace istio-system istio .
```

# Structure
```
.
├── README.md
├── eks.tf
├── helm
│   ├── base
│   │   ├── Chart.yaml
│   │   ├── README.md
│   │   ├── crds
│   │   ├── files
│   │   ├── templates
│   │   └── values.yaml
│   ├── base-1.21.0.tgz
│   └── istiod
│       ├── Chart.yaml
│       ├── README.md
│       ├── files
│       ├── templates
│       └── values.yaml
├── main.tf
├── network.tf
└── terraform.tfstate
```