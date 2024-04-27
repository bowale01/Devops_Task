
Install Helm 
   
$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
$ chmod 700 get_helm.sh
$ ./get_helm.sh

Installing ARGO CD 
Argo CD is a declarative, GitOps CD tool for Kubernetes. It automates the deployment of applications to Kubernetes clusters based on configuration files stored in Git repositories

Create Argo wrokflow 
kubectl apply -n argo -f https://github.com/argoproj/argo-work

Create a namespace called argo   
    kubectl create ns argocd

installing the chart 

   helm repo add argo https://argoproj.github.io/argo-helm

   helm install argocd argo/argo-cd --namespace argocd 
   

run this to get the secret key 

kubectl -n argocd get secret **************** -o jsonpath="{.data.password}" | base64 -d

<img width="1084" alt="Screenshot 2024-04-26 at 18 47 42" src="https://github.com/debolek/Debolek_Devops_Task/assets/37187773/68e9995a-2d9d-4489-811d-02a03c1345aa">


<img width="603" alt="Screenshot 2024-04-26 at 18 52 01" src="https://github.com/debolek/Debolek_Devops_Task/assets/37187773/3d86be42-4316-4fd8-a50c-b0b53446994a">


<img width="869" alt="Screenshot 2024-04-26 at 19 00 46" src="https://github.com/debolek/Debolek_Devops_Task/assets/37187773/4f25fe41-3765-43b6-be1b-f3d4fadd2746">



1. kubectl port-forward service/argocd-server -n argocd 8080:443

    and then open the browser on http://localhost:8080 

After reaching the UI the first time you can login with username: admin and the random password generated during the installation. You can find the password by running:

you might need to run this incase if you get some error when trying to enter your argocd GUI after some hours 

sudo lsof -i :8080

kill -9 <PID>

kubectl port-forward service/argocd-server -n argocd 8888:443





