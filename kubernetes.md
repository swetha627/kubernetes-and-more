#### There is a resource that gets created for every service called  ENDPOINT - it will have the ip address and port of all the pods that matches the Label Selector of the Service

#### you can check the rollout history of the deployment using the cmd :
  kubectl rollout history deployment/my-app

#### you can roll back to the previous deployment by the providing the revision in the below cmd:
  kubectl rollout undo deployment/my-app --to-revision=2 


#### Storage in k8s:
  PV and PVC 
  ##### Static Provisioning: PV is created manually with specific storage configuration
  ##### Dynamic Provisioning: PV is created dynamically when PVC ic created
