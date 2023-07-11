# Device Demo

# Tools
- [Lens](https://k8slens.dev/) was used to visualize this demo

# Requirements
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- Install [minikube](https://minikube.sigs.k8s.io/docs/start/)

# Usage
1. In a terminal run `minikube start` and wait for the cluster to start
2. Run `kubectl apply -f namespace.yaml` to create a new namespace
3. Run `kubectl apply -f deployment.yaml` to create the pods

At this point you should have a running cluster by running `kubectl get pods -n demo-dev --watch`. Adjust the values for `replicas`
to see number of pods scale up and down. Adjust the `image: nginx:1.14.2` version
number to see a pod being replaced or "updated". ie. Changing the value to `image: nginx:1.14.1` or `image: nginx:1.14.0` will cause a pod to be replaced gracefully.