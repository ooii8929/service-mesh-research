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
tar -xzf base-1.21.0.tgz
rm base-1.21.0.tgz
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
```
 helm ls -n istio-system
NAME            NAMESPACE       REVISION        UPDATED                                 STATUS          CHART           APP VERSION
istio           istio-system    1               2024-03-29 00:34:00.941528 +0800 CST    deployed        istiod-1.21.0   1.21.0     
istio-base      istio-system    1               2024-03-29 00:27:27.932434 +0800 CST    deployed        base-1.21.0     1.21.0
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