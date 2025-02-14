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
