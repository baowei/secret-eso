# create vault token
```
cat << EOF |kubectl -n external-secrets apply -f -
---
apiVersion: v1
kind: Secret
metadata:
  name: vault-token
data:
  token: xxxXXXM0pjMVEyZxxxXXX
EOF
```

## add chart repo
```
helm repo add kube-secret https://baowei.github.io/secret-eso
```

## Install
```
helm install my-release kube-secret/secret-eso --version 0.1.2
```