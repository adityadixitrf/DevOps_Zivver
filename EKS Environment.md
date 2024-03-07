**Prerequisites**

Install the following on your local machine
  1. kubectl
  2. eksctl
  3. AWS CLI

**Install EKS**

eksctl create cluster --name Zivvertask-cluster --region us-east-1 --fargate

aws eks update-kubeconfig --name Zivvertask-cluster --region us-east-1

eksctl create fargateprofile \
    --cluster Zivvertask-cluster \
    --region us-east-1 \
    --name alb-sample-app \
    --namespace version-app
