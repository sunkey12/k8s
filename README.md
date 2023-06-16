## part 1

1. pod-1.yaml

2. messaging-2.yaml

3. namespace-3.yaml

4. kubectl get nodes -o json > /tmp/nodes-arik
   nodes-arik.json

5. kubectl create service clusterip messaging-service --tcp=6379:6379

6. messaging-6-service.yaml

7. hr-web-app-7.yaml

8. static-busybox-8.yaml

9. finance-arik-9.yaml

10. pv-analytics-10.yaml

11. redis-storage-11.yaml

12. persistent-volume-12.yaml

13. nginx-deploy-13.yaml
    deploy-nginx-afterchange-13.yaml
    
14. nginx-resolver-service-14.yaml

15. nginx-critical-15.yaml

16. multi-pod-16.yaml


## part 2 

## 1.  Type the command for: Get pods with label information
1.  kubectl get pods --show-labels

## 2.  Create 5 nginx pods in which two of them is labeled env=prod and three of them is labeled env=dev
2.  kubectl run nginx-prod-1 --image=nginx --labels=env=prod

    kubectl run nginx-prod-2 --image=nginx --labels=env=prod

    kubectl run nginx-dev-1 --image=nginx --labels=env=dev

    kubectl run nginx-dev-2 --image=nginx --labels=env=dev

    kubectl run nginx-dev-3 --image=nginx --labels=env=dev
	
## 3. 	Verify all the pods are created with correct labels
3.  kubectl get pods --show-labels

## 4. Get the pods with label env=dev
4. kubectl get pods -l env=dev

## 5. Get the pods with label env=dev and also output the labels
5. kubectl get pods -l env=dev --show-labels

## 6. Get the pods with label env=prod
6. kubectl get pods -l env=prod

## 7. Get the pods with label env=prod and also output the labels
7. kubectl get pods -l env=prod --show-labels

## 8. Get the pods with label env
8. kubectl get pods -l env

## 9. Get the pods with labels env=dev and env=prod
9. kubectl get pods -l env=dev,env=prod

## 10. Get the pods with labels env=dev and env=prod and output the labels as well
10. kubectl get pods -l env=dev,env=prod --show-labels

## 11. Change the label for one of the pod to env=uat and list all the pods to verify
11. kubectl label pod nginx-devpod-1 env=uat --overwrite kubectl get pods --show-labels

## 12. Remove the labels for the pods that we created now and verify all the labels are removed
12. kubectl label pod nginx-prod-1 nginx-prod-2 nginx-dev-1 nginx-dev-2 nginx-dev-3 env

    kubectl get pods --show-labels


## 13. Let’s add the label app=nginx for all the pods and verify (using kubectl)
13. kubectl label pod nginx-prod-1 nginx-prod-2 nginx-dev-1 nginx-dev-2 nginx-dev-3 app=nginx

    kubectl get pods --show-labels
	
## 14. Get all the nodes with labels (if using minikube you would get only master node)
14. kubectl get nodes --show-labels

## 15. Label the worker node nodeName=nginxnode
15. kubectl label node node1 nodeName=nginxnode

## 16. yaml --> nginxnode-2-16.yaml

## 17. Verify the pod that it is scheduled with the node selector on the right node… fix it if it’s not behind scheduled.
17. kubectl get pods -A -o wide

## 18. Verify the pod nginx that we just created has this label
18. kubectl get pods -l run=nginx



## part3 - Deployment

1. webapp-3-1.yaml

2. kubectl rollout status deployment webapp

3. kubectl get replicaset -l app=webapp

4. kubectl get replicaset -l app=webapp --export=true --output=yaml > webapprs.yaml
   kubectl get pods -l app=webapp --export=true --output=yaml > webapp-pods.yaml

5. kubectl delete deployment webapp --cascade=true --watch

6. kubectl crear deploy webapp --image=nginx:1.17.1 --port=80 && kubectl describe deployment my-webapp | grep Image

7. kubectl set image deployment/webapp nginx=nginx:1.17.4 kubectl rollout status deployment/webapp

8. kubectl rollout history deployment/webapp

9. kubectl rollout undo deployment/webapp kubectl describe deployment webapp | grep -i image

10. kubectl set image deployment/webapp webapp=nginx:1.100

    kubectl get pods

    kubectl rollout undo deployment/webapp

    kubectl describe deployment webapp | grep -i image

    kubectl rollout history deploy webapp --revision=7

    kubectl set image deployment/webapp webapp=nginx:latest

    kubectl rollout history deploy webapp
    
 11. hpa-pod-3-11.yaml

 13. kubectl delete deployments.apps webapp
 
 14. job-3-14.yaml


## part 4



 
 
   

   
  


