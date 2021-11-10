# simple-helm

*the exemple is accomplished in a cluster k8s on GKE/GCP*

*A nginx kubernete's ingress controller is deployed in the cluster to manage the redirection of requests*

*the url is http://35.233.90.15.nip.io*

*nip.io is a dns service that allows us to map a IP Address to a hostname wihout have a reall FQDN in public*

*the ip 35.233.90.15 is proveided by the GKE*

### Defaut route:  35.233.90.15.nip.io 
**A ClusterIP k8s service with a simple gninx site. the portal is realized by a staic file conserved in configmap mounted in the pod of the service.

### Route:  /service1 
A nodePort k8s service who has 2 pod with a serviceaccount to communicate with apiserver of the cluster

### Route:  /service2
A LoadBalancer service with a hpa autoscaling strategy when the pod's cpu or mem exceede a limit. it has it own static ip  : http://146.148.28.150/
