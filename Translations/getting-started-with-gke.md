# Getting started with GKE (Google Kubernetes Engine)



## Objectives
In this lab, you learn how to perform the following tasks:

- Provision a Kubernetes cluster using Kubernetes Engine.

- Deploy and manage Docker containers using kubectl.




### **Start a Kubernetes Engine cluster**

Open Cloud Shell

> Place your zone in an environment variable

   `export MY_ZONE=us-central1-a`

> Start a Kubernetes cluster and name it 'webfrontend'

   `gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2`

> Check installed version of Kubernetes

   `kubectl version`




### **Run and deploy a container**

From Cloud shell prompt

> launch a single instance of the nginx container

  `kubectl create deploy nginx --image=nginx:1.17.10`

> View the pod running the nginx container:

  `kubectl get pods`

> Expose the nginx container to the Internet:

  `kubectl expose deployment nginx --port 80 --type LoadBalancer`

> View the new service:

  `kubectl get services`

  To Test - Open a new web browser tab and paste your cluster's external IP address into the address bar. The default home page of the Nginx browser is displayed.

> Scale up the number of pods running on your service:
 
 `kubectl scale deployment nginx --replicas 3`


> Confirm that Kubernetes has updated the number of pods:

 `kubectl get pods`

> Confirm that your external IP address has not changed:

 `kubectl get services`

> Return to the web browser tab in which you viewed your cluster's external IP address. Refresh the page to confirm that the nginx web server is still responding.



#### End of Lab

