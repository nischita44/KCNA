KubeCTL

To interact with K8s Cluster

Pre-requisites

- minikube
- kubectl

1. Install minikube cluster which comes with pre-installed docker

Basic Commands to start with:

1. To get the status of Nodes

   kubectl get nodes

   - status as Ready and name of the node here its minikube

 2. To get the version:

    kubectl version

3. kubectl get pod

4. kubectl get services

5. kubectl create -h
   - lists all the  available command to create the component
   - Pod cant be created since it is created through Deployment

6. kubectl create deployment NAME --image=image   
   Lets create a deployment nginx,
   kubectl create deployment nginx-depl --image=nginx
   - this will install the latest nginx image from the docker hub

7. kubectl get deployment   
 
 once you have nginx created,
8. kubectl get pod
 - this will have a nginx pod created

 9. kubectl get replicaset

10. kubectl edit  deployment nginx-depl

Debugging

11. kubectl logs [NAME]

12. kubectl describe pod [PODNAME]
    - detailed error

13. kubectl exec -it [podname] -- bin/bash


Delete the Pods

14. kubectl delete deployment nginx-depl


Node: Create edit and delete happens at deployment level and rest follows it like replicaset

15. kubectl apply -f nginx-deployment.yml
  - to execute the configuration file which is created


Advanced Commands

16. kubectl set image deployment/nginx-deployment nginx=nginx:1.161
    - Suppose that you made a typo while updating the Deployment, by putting the image name as nginx:1.161 instead of nginx:1.16.1:


17. kubectl rollout status deployment/nginx-deployment
    - The rollout gets stuck. You can verify it by checking the rollout status:


18. kubectl rollout undo deployment/nginx-deployment    
    - Rolling back to previous version


19. kubectl scale deployment/nginx-deployment --replicas=10
    - Scaling the deployment

## References
 - [KubeCTL](https://kubernetes.io/docs/reference/kubectl/)

