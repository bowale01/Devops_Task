
I am installing minikube on a Mac 

Install Minikube on Mac CLI

To install minikube on x86–64 mac OS, run the following two commands:-

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64
sudo install minikube-darwin-amd64 /usr/local/bin/minikube


Use the following command to start a cluster:-

minikube start

Use the following command to confirm minikube is running:

minikube status
