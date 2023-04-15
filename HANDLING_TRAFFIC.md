# Load Balancer
Allows you to expose ONE set of pods to the outside world

Legacy way of getting network traffic into a cluster

Gets AWS to provision a load balancer for you that will forward traffic to your Load Balancer Service (which will forward traffic to your pods)


# Ingress
Allows you to expose multiple set of pods to the outside world

We are using `ingress-nginx` which is a community led project
github.com/kubernetes/ingress-nginx

We are NOT using `kubernetes-ingress` which is a project led by the company nginx
github.com/nginxinc/kubernetes-ingress

Setup of `ingress-ngnix` changes depending on your environment (local, GC, AWS, Azure)

We are going to set up ingress-nginx in our local environment and GC

## Goals:
Ingress routing rules to get traffic to services. Controller for our ingress. Pod running nginx that handles routing.


`ingress-nginx` project gives us Sticky Sessions, a if a user sends 2 request they go to the same pod. This is not a feature of kubernetes, but a feature of `ingress-nginx`. It's a feature of the ingress controller. It bypasses ClusterIP for that reason. It has other features but this is a big one

After applying the `ingress-service.yaml` if you have Docker Desktop the client URL will be `https://kubernetes.docker.internal/` and the server URL will be `https://kubernetes.docker.internal/api`

These use a "Kubernetes Ingress Controller Fake Certificate"

