# Once docker installed successfully, run this:

```
docker-compose up
```

 # we can access it by navigating to http://localhost:50000/v2/_catalog
 
 # If you have the ubuntu:16.04 image on your local machine, tag it for our local repository.
 
 ```
 docker tag ubuntu:16.04 localhost:5000/myubuntu:16.04
 ```
 
 #the image tagged we can push it to our repository.
 ```
 docker push localhost:5000/myubuntu:16.04
 ```
 
 #  we can use this name in kubernetes yml as well as docker compose yml file to spin-up contianers
