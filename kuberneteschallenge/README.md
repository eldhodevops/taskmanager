#clone the repo once minikube setup has been completed.
I've setup minikube in my Windows machine using the exact steps in the url below
```
https://www.assistanz.com/installing-minikube-on-windows-10-home-edition-using-virtualbox/
```

Please follow the same, I've attached the screenshot of the results obtained. 

Note: please forward the port to view the web in 8080, (screenshot attached in "screenshot" directorty, refer it for further clarifications. 

#Commands to scale replicas:

```
kubectl scale --replicas=<provide num> -f <deploymentfilename>
```
Commands to update image:

```
kubectl set image deployment/frontend www=image:v2
```

if needed we can use local registry and push images to those and update image name with them in kubernetes yml files to deploy

```
docker run -d -p 5000:5000 --restart=always --name registry registry:2
```

In the result i used the official images and the images provided in the task to accomplish. 
