#### Service Discovery: How to micro-services of the application can communicate to each other?
    micro-services of an application can communicate to each other using k8s service object because it will have static IP unlike the pods of the deployment that keep changing. K8s also provides a dns name **<service-name>.<namespace>.svc.cluster.local**
#### There is a resource that gets created for every service called  ENDPOINT - it will have the ip address and port of all the pods that matches the Label Selector of the Service

#### you can check the rollout history of the deployment using the cmd :
  kubectl rollout history deployment/my-app

#### you can roll back to the previous deployment by the providing the revision in the below cmd:
  kubectl rollout undo deployment/my-app --to-revision=2 

#### RBAC:
  it is a mechanism in k8s that allows you to define and enforce permissions to and perform actions of k8s resources
  ###### Role is a namespace specific k8s resource that contains set of rules that define the permissions (get, list, create, update) for certain resources like pods,secrets ect
  ###### Cluster Role is same as Role but not namespace specific

  ###### RoleBinding and ClusterRole Binding are user bind Role and ClusterRole to users, groups, service accounts respectively
