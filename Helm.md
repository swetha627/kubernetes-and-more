helm repo add <repo-name> <repo-url>

helm repo list

helm repo update - refresh the list of all the helm repo's that were added

helm install <release-name> <repo-name/chart-name>

helm list

helm upgrade <release-name> <repo-name/chart-name>

helm uninstall <release-name>

helm get values <release-name> --all to list all the values used to deploy the chart

helm show chart <repo-name/chart-name> - display all the metadata of the helm chart

helm install <release-name> <repo-name/chart-name> --dry-run - simulation

helm install <release-name> <repo-name/chart-name> -f <values-file.yaml>

helm rollback <release-name>  <revision-number>

helm test <release-name>

helm package <chart-name> - create a .tgz file

helm create <chart-name>  - to create an helm chart




