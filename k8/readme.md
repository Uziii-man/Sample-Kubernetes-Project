# Pre-requisites

1. docker
2. minikube
3. kubectl

---

# Steps

1. Start the minikube
```
minikube start
// if you are using windows, please specify the minikube driver like hyperV
```

2. Verify the nodes
```
kubectl get nodes
```

3. Can add a ingress if you want but completely optional which you needed to config later
```
minikube addons enable ingress
```

---
In here there are two main ways you can locate the service image
1. Build the image direcly inside minikube
    - for that
        1. set minikube enviroment
            ```
                eval $(minikube docker-env)
            ```
        
        2. build docker image
            ```
                docker build -t "image-name" .
            ```

        3. Verfiy the docker image
            ```
                docker images
            ```

---

4. Deploy the manifest file
```
kubectl apply -f "manifest-file-name"
```

5. Check for pods
```
kubeclt get pods

// To diagnose pods
kubectl describe pod "pod-name"
```

6. Check for the service
```
kubectl get services
```

---

# To access the services inside

1. To run
```
kubectl run "service-name" --image="image-name"
// can add --restart=Always -- sleep inifinity
```

2. To enter into the service terminal
```
kubectl exec -it "service-name" "list of parameters needed to past"
// for example
kubectl exec -it kafka-client -- kafka-topics.sh --bootstrap-server kafka:9092 --list
```

---

# To cleanup the project
```
kubectl delete -f "name-of-manifest-file"
```
