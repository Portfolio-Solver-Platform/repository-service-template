# repository-service-template
All template files used for a service. Here is how to use the template yourself:
## Copy
 copy all files (except the README.md) 

## Replace
- replace all occurences of `<name>` with your desired name of the service (can just be the repository name). It is in the following files:
```
./skaffold.yaml
./helm/Chart.yaml
./helm/templates/deployment.yaml
./helm/values.yaml
./pyproject.toml
```

#### A semi automatic way of replacing `<name>`
on my mac I can just run this:
```
find skaffold.yaml -type f -exec sed -i '' 's/solver-director/<name>/g' {} + 
find helm/ -type f -exec sed -i '' 's/solver-director/<name>/g' {} +
```
except in pyproject I need to enter it manually in the top of the file, where it says: `name = "service" # replace service with <name> 
`


## Customize settings
- go through all settings and set them yourself to what u want
