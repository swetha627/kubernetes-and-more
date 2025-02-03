**spec.selector.macthLables**
**spec.template.metadata.labels**

#### Deployment is going to manage only the set of the pods that mathes the lables that in given in **spec.selector.macthLables**
#### Because for any updates in deployment a new replicaset is created and replica set looks for **spec.selector** in deployment

### macthLables is available only in deployment, sts, job and daemonset. **for Service we will have to provide the pod lables not deployment labels**


apiVersion: apps/v1
kind: Deployment
metadata:
  name: fastapi-deployment
  labels:
    app: fastapi-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: fastapi-app
  template:
    metadata:
      labels:
        app: fastapi-app
    spec:
      containers:
      - name: fastapi-container
        image: your-docker-image:latest  # Replace with your image
        ports:
        - containerPort: 8000  # Assuming FastAPI runs on port 8000
