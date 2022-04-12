# cool-kid-kloud
Purpose: for my kodekloud learning journey on kubernetesS

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
Execute: kubectl get pods,svc
Alternatively, execute: kubectl get all

--  result should display similar to below --
-- all pods must be in running status and all services are correctly defined with type as below
===========================
$ kubectl get all
NAME                 READY   STATUS    RESTARTS   AGE
pod/postgres-pod     1/1     Running   0          36m
pod/redis-pod        1/1     Running   0          51m
pod/result-app-pod   1/1     Running   0          61m
pod/voting-app-pod   1/1     Running   0          61m
pod/worker-app-pod   1/1     Running   0          25m

NAME                     TYPE        CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
service/db               ClusterIP   10.110.88.170    <none>        5432/TCP       50m
service/kubernetes       ClusterIP   10.96.0.1        <none>        443/TCP        2d19h        
service/redis            ClusterIP   10.103.176.243   <none>        6379/TCP       51m
service/resutl-service   NodePort    10.111.17.40     <none>        80:30005/TCP   24m
service/voting-service   NodePort    10.97.18.33      <none>        80:30004/TCP   60m


##  How to access the application
As this is installed in minikube, you can verify the url for each voting and result app.
This can be done by executing: minikube service voting-service --url and minikube service resutl-service --url
        and minikube service voting-service --url
The output should be similar to below:
           $ minikube service resutl-service --url
           http://192.168.59.100:30005

-- Note that IP address is specific to my laptop installation --

## Important
Note that when you cast the vote in the voting-app url, the result-app url should reflect the vote that you have made.
  
  
        
