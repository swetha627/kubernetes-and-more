ingress is tool for routing traffic from outside the cluster to services running in the clsuter
there shld be an ingress controller like nginx, HAproxy installed
ingress does two kinds of routing:
1. path based routing
2. host based routing

example for path based routing :

say we have two services svc1 for home page and svc2 for blog
now we don't have to maintain different load balancer or nodeport for each service because with the help of path based routing in ingress we can use same ingress external ip 

snippet of ingress yaml:

apiversion: networking.k8s.io/v1
kind: ingress
metadata:
  name: test-path-based-routing
spec:
  rules:
    ingressClassName: nginx-ingress
    host: aicloud.cloudlyte.sslip
    http:
      paths:
      -  path:/home
        pathType: Prefixx
        backend:
          service:
            name: svc1.default.cluster.local.svc
            port:
              number: 80
     -  path:/blog
        pathType: Prefix
        backend:
          service:
            name: scv2.default.cluster.local.svc
          port:
            number: 80




There are three type of the path Types: Exact, Prefix, ImplementationSpecific

Exact: routes to the service if it is a exact match

Prefix: route to any url with the specified prefix
