
This is a kubernetes example which is combined nginx and busybox for my journey about learning and practicing k8s 

Pod contains two containers, one of them nginx for web server and the other is busybox for getting index.html from github.

These two container share same volume. busybox updates shared volume every 15 seconds and gets the index.html from github, if i update index.html and push it, pod get update automatically.

If you have a kubernetes cluster then you can use that with kubectl apply command, also if you want access from your localhost you should port forward for this example.

First I have done docker, kubectl and minikube setups on my computer.

Next I have used that command for create a pod;

> kubectl apply -f pod.yaml

after that I have used that command for port forward

> kubectl port-forward pod/multicontainer 8080:80
