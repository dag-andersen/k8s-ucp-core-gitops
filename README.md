# k8s-ucp-core-gitops

*Install initial app*

```makefile
argo-initial-app:
	kubectl create namespace crossplane-system --dry-run=client -o yaml | kubectl apply -f -
	kubectl create secret generic gcp-creds -n crossplane-system --from-file=creds=<path_to_creds.json> --dry-run=client -o yaml | kubectl apply -f -
	kubectl apply -f k8s-ucp-core-gitops/kube-app-bootstrap/kube-applications.yml
```
