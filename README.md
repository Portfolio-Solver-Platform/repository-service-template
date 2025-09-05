# repository-service-template
All template files used for a service

- copy all files (except the README) and customize them as needed
- setup github workflows
- install kubernetes metric server:
```
helm repo add metrics-server https://kubernetes-sigs.github.io/metrics-server/
helm repo update
helm upgrade --install metrics-server metrics-server/metrics-server -n kube-system
```
- replace all occurences of `<name>` with your desired name of the service (can just be the repository name)
The following files is:
```
./skaffold.yaml
./helm/Chart.yaml
./helm/templates/deployment.yaml
./helm/values.yaml
```
    on my mac I can just run this:
```
find skaffold.yaml -type f -exec sed -i '' 's/solver-director/<name>/g' {} + 
find helm/ -type f -exec sed -i '' 's/solver-director/<name>/g' {} +
```

- go through all settings and set them yourself to what u want

NOTE: a CI/CD pipeline is still missing