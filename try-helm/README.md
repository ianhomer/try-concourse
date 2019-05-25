# Pre-requisites

    brew install kubernetes-helm
    minikube start
    kubectl config use-context minikube
    helm init

# tl;dr

    helm install --name try-concourse -f values.yaml stable/concourse  
    
Routing for port 8080

```
set -x POD_NAME (kubectl get pods --namespace default -l "app=try-concourse-web" -o jsonpath="{.items[0].metadata.name}")
echo "Visit http://127.0.0.1:8080 to use Concourse"
kubectl port-forward --namespace default $POD_NAME 8080:8080
```

And visit 

        http://127.0.0.1:8080
        
# Next

[Handle secrets properly](https://github.com/helm/charts/tree/master/stable/concourse)

# Troubleshooting

Show persistent volumes

    kubectl get pvc

# Clean up 

    helm delete try-concourse
    kubectl delete pvc -l app=try-concourse-worker

# thanks

* https://github.com/helm/charts/tree/master/stable/concourse
* https://helm.sh/docs/install/
