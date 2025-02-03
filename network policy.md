##### network policies

spec.PodSelector.matchLables: to define labels of the pods to which this rules of this network policy shld be applied

spec.PolicyTypes: to define the type of communication **ingress egress**

spec.ingress: to define rules of what traffic can be allowed to these selected pods

spec.egress: to define rules of what can be accessed from the pods


```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: backend-network-policy
spec:
  podSelector:
    matchLabels:
      app: backend
  policyTypes:
  - Ingress
  - Egress
  ingress:
  - from:
    - podSelector:
        matchLabels:
          app: frontend
  egress:
  - to:
    - podSelector:
        matchLabels:
          app: frontend

```
