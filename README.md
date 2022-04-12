# cool-kid-kloud
Purpose: for my kodekloud learning journey on kubernetes

Base on kodekloud kubernetes for absolute beginner course 
URL: https://kodekloud.com/courses/kubernetes-for-the-absolute-beginners-hands-on/

## How to use?
1. Install minikube in your laptop, preferably via Oracle VM
2. Install Visual Studio Code
3. Git clone this repository
4. Installation:
   - kubectl create -f voting-app-pod.yaml
   - kubectl create -f voting-service.yaml
   - kubectl create -f redis-pod.yaml
   - kubectl create -f redis-service.yaml
   - kubectl create -f result-app-pod.yaml
   - kubectl create -f result-service.yaml
   - kubectl create -f postgres-pod.yaml
   - kubectl create -f postgres-service.yaml
   - kubectl create -f worker-pod.yaml

## How to verify that all pods and service are created?
Execute: **kubectl get pods,svc**.   Alternatively, execute: **kubectl get all**

The result should display similar to below.  All pods must be in running status and all services are correctly defined with type as below.

![image](https://user-images.githubusercontent.com/34974207/162943553-e469fdcd-4d1d-4ffc-9d64-1e8fed46ce99.png)



##  How to access the application
As this is installed in minikube, you can verify the url for each voting and result app.
This can be done by executing: **minikube service voting-service --url** and **minikube service resutl-service --url**.  
The output should be similar to below:

![image](https://user-images.githubusercontent.com/34974207/162943634-4cbe6458-0de0-4a74-a9a7-0e751b9095a0.png)

-- Note that IP address is specific to my laptop installation --

## Important
Note that when you cast the vote in the voting-app url, the result-app url should reflect the vote that you have made.
  
  
        
