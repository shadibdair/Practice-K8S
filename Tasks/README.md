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
Created it inside svc.yaml
--> kubectl apply -f svc.yaml


Remember: 
- to add a label to your pod yaml, then "kubectl apply -f nginx.yaml" to edit the changes you've made.
- On the service clusterIP there's "selector" which match the labels you have.
```
*Screenshots:*

![Screen Shot 2022-10-14 at 13 06 14](https://user-images.githubusercontent.com/43513994/195821332-3a17dc16-0d91-4cd3-910b-8a687b0645d7.png)


### Create an external service (nodeport or loadbalancer) and connect it to the POD
```
Created it inside svc-nodeport.yaml
--> kubectl apply -f svc-nodeport.yaml
```
*Screenshots:*
![Screen Shot 2022-10-14 at 13 26 47](https://user-images.githubusercontent.com/43513994/195825637-2e31655f-c0cd-4224-8a77-621b058ef94b.png)


### Create a deployment instead of the pod.
#### Why should we use deployment and not ReplicaSet or POD objects?
```
Kubernetes schedules and automates container deployment across multiple compute nodes, whether on the public cloud, onsite VMs or physical on-premises machines.
Its automatic scaling lets teams scale up or down to meet demand faster.
```
```
Created it inside deployment.yaml 
--> kubectl apply -f deployment.yaml 
```
*Screenshots:*

![Screen Shot 2022-10-14 at 13 39 11](https://user-images.githubusercontent.com/43513994/195828065-f4c43a4f-5921-4ac0-aaa0-44683c31d61b.png)



### Scale your application to 3 instances.
```
In the deployment yaml I've changed the replicas from 3 to 5, then:
--> kubectl apply -f deployment.yaml
```
*Screenshots:*

![Screen Shot 2022-10-14 at 13 52 37](https://user-images.githubusercontent.com/43513994/195830583-d5e7d5a2-2160-4e9f-8fec-3f223e58b730.png)

