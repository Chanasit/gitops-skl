# Gitops

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
