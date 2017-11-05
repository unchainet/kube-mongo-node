
#Entry point how to run mongo & node.js app in kubernetes
https://github.com/kubernetes/examples/blob/master/staging/nodesjs-mongodb/README.md


#minikube installation on mac
https://kubernetes.io/docs/getting-started-guides/minikube/


#Notes
- production kubernetes should run on Ubuntu - version "Cannonical Distribution of Kubernetes" (Juju and conjure-up seem to be the tools to install kube)
- after running container, check status with `kubectl get pod`
- to check logs `kubectl logs <podname>`
- to check create errors `kubectl describe po <podname>`
- create node app docker image https://nodejs.org/en/docs/guides/nodejs-docker-webapp/
- remove exited containers to start again - https://zaiste.net/posts/removing_docker_containers/ (after tag do docker push to make it working!)


#troubleshooting local docker registry to work with minikube
https://gist.github.com/kevin-smets/b91a34cea662d0c523968472a81788f7


#Steps:
1) install docker (don't need to run as minikube runs it's own docker daemon)
2) install minikube, start `minikube start`
3) setup local registry so apps docker images created on localhost and pushed to localhost:5000 are accessible from minikube - https://gist.github.com/kevin-smets/b91a34cea662d0c523968472a81788f7
4) run `kubectl create -f {filename}` for mongo-service, mongo-controller, web-service, web-controller
5) run `minikube service web --url` to get url - open in the browser

