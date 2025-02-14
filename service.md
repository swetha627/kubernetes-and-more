#### Service Discovery: How to micro-services of the application can communicate to each other?
    micro-services of an application can communicate to each other using k8s service object because it will have static IP unlike the pods of the deployment that keep changing. K8s also provides a dns name **<service-name>.<namespace>.svc.cluster.local**
#### There is a resource that gets created for every service called  ENDPOINT - it will have the ip address and port of all the pods that matches the Label Selector of the Service


