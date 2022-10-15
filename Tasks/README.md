# 🤠 Questions 

### Create a POD with Nginx using kubectl command
```
This will create a pod named nginx, 
running with the nginx image on Docker Hub. 
And by setting the flag --restart=Neverwe 
tell Kubernetes to create a single pod rather than a Deployment:

--> kubectl run nginx --image=nginx --restart=Never
```

----

### Create a POD with Nginx using a yaml file
```
Created it inside nginx-yaml

Then run this command :
--> kubectl apply -f nginx.yaml 
```

----

### Using kubectl port-forward access the nginx web page
```
--> kubectl port-forward web-nginx 8000:80
```
*Screenshots:*

<img width="478" alt="Screen Shot 2022-10-14 at 12 05 05" src="https://user-images.githubusercontent.com/43513994/195813596-00ecc2b7-41be-40ab-adc7-c6a41391ac68.png">

![Screen Shot 2022-10-14 at 12 04 47](https://user-images.githubusercontent.com/43513994/195813608-2120de2e-8cf8-4cc9-9a9e-88c3d7bd7d75.png)

----

### Edit the image of the container in the pod and deploy it.
```
--> kubectl apply -f nginx.yaml
Output --> pod/web-nginx-edited created
```

----

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

----

### Create an external service (nodeport or loadbalancer) and connect it to the POD
```
Created it inside svc-nodeport.yaml
--> kubectl apply -f svc-nodeport.yaml
```
*Screenshots:*
![Screen Shot 2022-10-14 at 13 26 47](https://user-images.githubusercontent.com/43513994/195825637-2e31655f-c0cd-4224-8a77-621b058ef94b.png)

----

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

----

### Connect your external services to the deployment.
```
I've added a label "matchLabels" and created service nodeport.
To create a service :
--> kubectl apply -f svc-nodeport.yaml
The yaml file svc nodeport under folder "services".
```
*Screenshots:*

<img width="912" alt="Screen Shot 2022-10-15 at 1 13 29" src="https://user-images.githubusercontent.com/43513994/195951884-555839b9-a700-45af-8fda-c7f017022601.png">

----

### Scale your application to 3 instances.
```
In the deployment yaml I've changed the replicas from 3 to 5, then:
--> kubectl apply -f deployment.yaml
```
*Screenshots:*

![Screen Shot 2022-10-14 at 13 52 37](https://user-images.githubusercontent.com/43513994/195830583-d5e7d5a2-2160-4e9f-8fec-3f223e58b730.png)

----

### Go inside each pod and edit the index.html file and try to access the nginx web site. 
#### Did it change?
```
As you can see the results:
After get inside each pods and edit the index.html.
When I access it from the URL I've received different results.
Because every time I reload the page it's alternating between the "3" pods that I have inside the deployment (replicas) 
```
*Screenshots:*

```
Because I'm access applications running within minikube, I used this command :
Added the name of my service nodeport that I was created.
--> minikube service svc-nodeport --url
```

![Screen Shot 2022-10-15 at 1 42 10](https://user-images.githubusercontent.com/43513994/195954098-544fdcaf-223d-47e8-ab9e-83be2971d57a.png)


<img width="1263" alt="Screen Shot 2022-10-15 at 1 35 10" src="https://user-images.githubusercontent.com/43513994/195953664-7ab84465-211c-4429-b07a-91f36921297c.png">

![Screen Shot 2022-10-15 at 1 32 07](https://user-images.githubusercontent.com/43513994/195953679-783f2fef-91a3-45c0-9955-8f3f8a470566.png)

----

### Create a namespace for the new deployment and move the deployment created to that namespace.
```
Under namespace folder, I've created a yaml file contain a namespace .. then :
--> kubectl apply -f namespace.yaml
--> OUTPUT : namespace/shadi-namespace created
```

*Screenshots:*

<img width="404" alt="Screen Shot 2022-10-15 at 11 05 15" src="https://user-images.githubusercontent.com/43513994/195976468-5f917fd4-98b1-441c-bd01-94c84dceb0a0.png">


----
----

# 🧛 Shadi's Workload status :
![Screen Shot 2022-10-15 at 1 47 27](https://user-images.githubusercontent.com/43513994/195954627-6314474e-38bb-4301-a6a5-325dc4c4ab0f.png)





