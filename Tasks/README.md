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
```
*Screenshots:*

<img width="478" alt="Screen Shot 2022-10-14 at 12 05 05" src="https://user-images.githubusercontent.com/43513994/195813596-00ecc2b7-41be-40ab-adc7-c6a41391ac68.png">

![Screen Shot 2022-10-14 at 12 04 47](https://user-images.githubusercontent.com/43513994/195813608-2120de2e-8cf8-4cc9-9a9e-88c3d7bd7d75.png)


### Edit the image of the container in the pod and deploy it.
```
--> kubectl apply -f nginx.yaml
Output --> pod/web-nginx-edited created
```

### Create a ClusterIP service and connect it to the pod.
```
--> kubectl apply -f svc.yaml


Remember: 
- to add a label to your pod yaml, then "kubectl apply -f nginx.yaml" to edit the changes you've made.
- On the service clusterIP there's "selector" which match the labels you have.
```
*Screenshots:*

![Screen Shot 2022-10-14 at 13 06 14](https://user-images.githubusercontent.com/43513994/195821332-3a17dc16-0d91-4cd3-910b-8a687b0645d7.png)


### Create an external service (nodeport or loadbalancer) and connect it to the POD
```

-->
```