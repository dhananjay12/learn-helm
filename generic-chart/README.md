### How to deploy the chart

Package the chart:

```
helm package .
```

Copy the generated `tgz` file to docs folder. Then update the index by running:

```
 helm repo index .
```

### Install local Ingress

https://kubernetes.github.io/ingress-nginx/deploy/

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.41.2/deploy/static/provider/cloud/deploy.yaml
```
If you want to delete later just use `delete` afterwards.

```
kubectl delete -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.41.2/deploy/static/provider/cloud/deploy.yaml
```