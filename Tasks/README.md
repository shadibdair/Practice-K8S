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

<img width="478" alt="Screen Shot 2022-10-14 at 12 05 05" src="https://user-images.githubusercontent.com/43513994/195813356-df25a71f-3f23-405d-9533-cdcbbda0545b.png">

![Screen Shot 2022-10-14 at 12 04 47](https://user-images.githubusercontent.com/43513994/195813376-5e2fc853-4648-4f89-bcc6-fbfc6e867c1f.png)

```


### Edit the image of the container in the pod and deploy it.
```
--> kubectl apply -f nginx.yaml
Output --> pod/web-nginx-edited created
```
