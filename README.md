# argo-deploy-test

## Flagger
### Blue-green

ArgoCD yaml deployment for nginx :
```yaml
project: default
source:
  repoURL: 'https://github.com/ixxeL2097/argo-deploy-test.git'
  path: flagger-blue-green
  targetRevision: HEAD
destination:
  server: 'https://kubernetes.default.svc'
  namespace: blue-green
syncPolicy:
  automated:
    prune: true
    selfHeal: true
  syncOptions:
    - CreateNamespace=true
    - ApplyOutOfSyncOnly=true
```