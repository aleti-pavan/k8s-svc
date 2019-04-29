# Kubernetes Service Object

Service object of the kubernetes helps in service discory

Service discovery tools help solve the problem of finding which processes are listening at which addresses for which services. A good service discovery system will enable users to resolve this information quickly and reliably. 

There are 4 types of services 

ClusterIP:
---------
Exposes the service on a cluster-internal IP. Service is only reachable from within the cluster. This is the default Type.

NodePort:
--------
Exposes the service on each Node’s IP at a static port. A ClusterIP service, to which the NodePort service will route, is automatically created. You’ll be able to contact the NodePort service, from outside the cluster, by using “<NodeIP>:<NodePort>”.

LoadBalancer:
------------
Exposes the service externally using a cloud provider’s load balancer. NodePort and ClusterIP services, to which the external load balancer will route, are automatically created.

ExternalName:
------------
Maps the service to the contents of the externalName field (e.g. foo.bar.example.com), by returning a CNAME record with its value.

Service Discovery:
=================

There are two ways to discover service in kubernetes. By ENV variable or DNS.

ENV Var – When a Pod is run on a Node, the kubelet adds a set of environment variables for each active Service.

DNS – The DNS server is a cluster add-on that watches the Kubernetes API for new Services and creates a set of DNS records for each. If DNS has been enabled throughout the cluster then all Pods should be able to do name resolution of Services automatically. This is the recommended option.

