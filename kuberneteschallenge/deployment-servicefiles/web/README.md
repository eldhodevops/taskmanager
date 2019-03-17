#Location: E:\kubernetestask\web in my windows machine 

Create deployment and service for web using the below command:
```
kubectl.exe create -f deploy
```
```
kubectl.exe create -f svc.yml
```
Once completed check the port using kubectl.exe get svc and forward the port in virtual box as provided in the screenshot
