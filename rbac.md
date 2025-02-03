##### RBAC - Role Based Access Control

Role/ClusterRole - Defines the permissions (**Group, resource, verbs(actions that are allowed on the resources)**)

RoleBinding/ClusterRoleBinding - Defines to **Users/ Groups/ ServiceAccount** the Referenced Role will be applied to

Role - RoleBinding (Namespace specific)

ClusterRole - ClusterRoleBinding ( Applied for entire Cluster)


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


