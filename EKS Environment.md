**Prerequisites**

Install the following on your local machine
  1. kubectl
  2. eksctl
  3. AWS CLI

**Install EKS**

eksctl create cluster --name demo-cluster --region us-east-1 --fargate

aws eks update-kubeconfig --name demo-cluster --region us-east-1

eksctl create fargateprofile \
    --cluster demo-cluster \
    --region us-east-1 \
    --name alb-sample-app \
    --namespace game-2048
