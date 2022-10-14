# Questions 

### Create a POD with Nginx using kubectl command
```
This will create a pod named nginx, 
running with the nginx image on Docker Hub. 
And by setting the flag --restart=Neverwe 
tell Kubernetes to create a single pod rather than a Deployment:

--> kubectl run nginx --image=nginx --restart=Never
```

### Create a POD with Nginx using a yaml file
```
Created it inside nginx-yaml

Then run this command :
--> kubectl apply -f nginx.yaml 
```


### Using kubectl port-forward access the nginx web page
```
--> kubectl port-forward web-nginx 8000:80

add pics
```


### Edit the image of the container in the pod and deploy it.
```
--> 
```