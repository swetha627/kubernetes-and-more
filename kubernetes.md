#### There is a resource that gets created for every service called  ENDPOINT - it will have the ip address and port of all the pods that matches the Label Selector of the Service

#### you can check the rollout history of the deployment using the cmd :
  kubectl rollout history deployment/my-app

#### you can roll back to the previous deployment by the providing the revision in the below cmd:
  kubectl rollout undo deployment/my-app --to-revision=2 


#### Storage in k8s:
  PV and PVC 
  ##### Static Provisioning: PV is created manually with specific storage configuration
  ##### Dynamic Provisioning: PV is created dynamically when PVC ic created

  ###### Retain Policy:
  1. retain: pv remains intact for manual data recovery
  2. recycle: pv is not deleted, but data is wiped off
  3. delete: pv itself is deleted

  ###### AccessMode:
  1. ReadWriteOnce: can be mounted as read-write by a single node
  2. ReadOnlyMany: can be mounted as read-only by many nodes
  3. ReadWriteMany: Can be mounted as read-write by many nodes
