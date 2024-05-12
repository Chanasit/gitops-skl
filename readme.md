# Gitops

## Structure
```
├── apps
│   ├── development
│   │   ├── repositories
│   │   │   ├── kustomization.yaml
│   │   │   └── node-js-postgresql-crud-example.yaml
│   │   └── tenants
│   │       ├── automation.yaml
│   │       ├── kustomization.yaml
│   │       ├── namespace.yaml
│   │       ├── node-js-postgresql-crud-example.yaml
│   │       └── postgresql.yaml
│   ├── production
│   │   ├── repositories
│   │   │   ├── kustomization.yaml
│   │   │   └── node-js-postgresql-crud-example.yaml
│   │   └── tenants
│   │       ├── kustomization.yaml
│   │       ├── namespace.yaml
│   │       ├── node-js-postgresql-crud-example.yaml
│   │       └── postgresql.yaml
│   └── shared
│       └── tenants
│           ├── jenkins.yaml
│           ├── kustomization.yaml
│           └── namespace.yaml
├── clusters
│   └── skl
│       ├── apps.yaml
│       └── flux-system
│           ├── gotk-components.yaml
│           ├── gotk-sync.yaml
│           └── kustomization.yaml
└── readme.md
```

## bootstrap fluxcd
```
flux bootstrap github \           
  --components-extra image-reflector-controller,image-automation-controller \
  --token-auth \
  --owner=chanasit \
  --repository=gitops-skl \
  --branch=master \
  --path=clusters/skl \
  --personal
```
