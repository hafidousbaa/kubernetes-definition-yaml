# Pod-definition-yaml  && replicatset  &&recreate  && rollingupdate && deployemnt && Service
 <!--  -->
----------------------------------------------------------------------

![alt](./image/pod.png)
----------------------------------------------------------------------

**Create a pod using file yaml:**
<!--  -->
*what's a pod ?*
<!-- | -->
```
Pods are the smallest deployable units you can create and manage in Kubernetes. 
A pod is a group of one (or more) containers, utilizing shared network and storage resources. 
By nature, the contents of a pod are always co-scheduled and co-located,
 and they are run in a shared context.
```

------------------------------------------------------------------------
 <!--  -->
 ```
what's *replicatset* : the mot describe itself, create a replicat set, 
we use a selector to watch the state of pods 
if there's a pod down a new pod with the same specifies will create automatically.
 ```

 <!--  -->
 ```
what's *recreate* : remove all the pods , and update the new image and running them again (new version).

all the pods in the same time.
 ```
 <!--  -->

 <!--  -->
 ```
what's *rollingUpdate* : remplace pod one after one ,   


 ```
 <!--  -->
* Service :
  * NodePort
  * ClusterIP
  * Load Balaner **work only with CLOUD (aws,azure,gcp)**

 <!--  -->
create a pod with command use a file yaml :  
<!--  -->

`kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx-definition.yaml`
<!--  -->
 // Create a file yaml && the file contains all composant to create a pod nginx
 <!--  -->
`kubectl create -f nginx-definition-yaml`
 <!--  -->
// Create a pod by filename  
<!--  -->
`kubectl replace -f replicaset.yaml`
<!--  -->
//scaling with edit the file replicaset.yaml and execute the command to apply the change
<!--  -->
`kubectl scale --replicas=6 -f replicaset.yaml`
<!--  -->
//instead of modified the yaml file we can scale using this command, Notice that the file yaml doesn't modified  
