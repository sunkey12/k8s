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
