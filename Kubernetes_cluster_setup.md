Install Minikube on Mac CLI

Step 1 :- To install minikube on x86–64 mac OS, run the following two commands:-

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64 sudo install minikube-darwin-amd64 /usr/local/bin/minikube

Step 2 :- Use the following command to start a cluster:-

minikube start

Step 3:- Use the following command to confirm minikube is running:

minikube status

<img width="464" alt="Screenshot 2024-04-26 at 11 31 14" src="https://github.com/debolek/Debolek_Devops_Task/assets/37187773/6ec097d7-b87e-48b8-9a97-76bbd02e3fde">



To ensure high availability and scalability for your Nginx test site for the choosen application on our Kubernetes cluster, i need:

We already have a master node which we called "control plane" 

Worker Nodes: At least two worker nodes are recommended for fault tolerance. This setup ensures that if one worker node fails, the other node can continue serving traffic. Having more than two nodes further enhances fault tolerance and allows for better distribution of resources.
Pods: You need multiple replicas of the Nginx pod to achieve fault tolerance and scalability. By having multiple replicas spread across different nodes, your application can continue to serve traffic even if one or more pods or nodes fail. Additionally, scaling the number of replicas based on CPU load ensures that your application can handle increased traffic efficiently.


Worker Nodes: Start with at least two worker nodes in your Kubernetes cluster. You can scale up the number of nodes based on your application's resource requirements and expected traffic. Kubernetes provides features like automatic node scaling to help manage node resources efficiently.


minikube start --nodes 3 -p k8cluster 

check the nodes 

<img width="539" alt="Screenshot 2024-04-26 at 15 50 02" src="https://github.com/debolek/Debolek_Devops_Task/assets/37187773/f33e153e-4ca6-47f6-b77d-4ac07c465331">

<img width="1043" alt="Screenshot 2024-04-26 at 16 01 34" src="https://github.com/debolek/Debolek_Devops_Task/assets/37187773/e2033938-63aa-4413-9436-8da91ab29612">


Label Nodes 

When i want to deploy the choosen application pods which is nginx, i don't want them to deploy to my control-plane, so i will label out second and third nodes as "worker"  with this below command 

kubectl label node <node_name> node-role.kubernetes.io/worker=worker

kubectl label node k8cluster-m02 node-role.kubernetes.io/worker=workernode

kubectl label node k8cluster-m03 node-role.kubernetes.io/worker=workernode


<img width="1008" alt="Screenshot 2024-04-26 at 16 14 02" src="https://github.com/debolek/Debolek_Devops_Task/assets/37187773/52ba2e43-ad03-42db-9a1e-f0eb87a91157">



The YAML files that we will deploy will search for these worker nodes based on a key:value label pair using this below command 

 kubectl label nodes <node_name> role=worker

 kubectl label node k8cluster-m02 role=workernode

 kubectl label node k8cluster-m03 role=workernode


