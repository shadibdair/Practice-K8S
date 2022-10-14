# Questions 

### Create a POD with Nginx using kubectl command
```
This will create a pod named nginx, running with the nginx image on Docker Hub. And by setting the flag --restart=Neverwe tell Kubernetes to create a single pod rather than a Deployment:

--> kubectl run nginx --image=nginx --restart=Never
```
