
#### RBAC: Role Based Access Control
  
it is a mechanism in k8s that allows you to define and enforce permissions to and perform actions of k8s resources
   
   
   **Role** is a namespace specific k8s resource that contains set of rules that define the permissions (get, list, create, update) for certain resources like pods,secrets ect
  
   **Cluster-Role** is same as Role but not namespace specific

   RoleBinding and ClusterRole Binding are user bind Role and ClusterRole to users, groups, service accounts respectively

Role/ClusterRole - Defines the permissions (**Group, resource, verbs(actions that are allowed on the resources)**)

RoleBinding/ClusterRoleBinding - Defines to **Users/Groups/ServiceAccount** the Referenced Role will be applied to

Example with Service Account:

```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: kubeflow
  name: katib-exporter-role
rules:
- apiGroups: ["kubeflow.org"]
  resources: ["experiments"]
  verbs: ["*"]

---
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  namespace: kubeflow
  name: katib-exporter-rolebinding
subjects:
- kind: ServiceAccount
  name: katib-exporter
  namespace: sparkflow
roleRef:
  kind: Role
  name: katib-exporter-role
  apiGroup: rbac.authorization.k8s.io

---
apiVersion: v1
kind: ServiceAccount
metadata:
  name: katib-exporter
  namespace: sparkflow

```


