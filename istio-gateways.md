**Istio - Service Mesh**

Uses:
1. Traffic Management: 
2. Observability: Traffic metric, traces and logs are collected
3. Security: Control over incoming traffic

**Gateway**:  
1. Acts has an entry point for external traffics that is entering into the mesh.
2. it also enforces SSL/TLS termination and other security features.
3. It uses **Envoy sidecars** for traffic routing.

**Virtual Service**: Maps Gateway traffic to specific services. It defines routes and policies for requests

**Destination Rule**: Configures how traffic is handled after reaching the specfic services like path/host based routing in ingress

**Sidecar Proxy (Envoy)**: Handles traffic between the services within the mesh






 
