**Prerequisites**

Install the following on your local machine
  1. kubectl
  2. eksctl
  3. AWS CLI

**Install EKS**

eksctl create cluster --name demo-cluster --region us-east-1 --fargate

aws eks update-kubeconfig --name demo-cluster --region us-east-1

**2048 App**

**Create Fargate profile **

eksctl create fargateprofile \
    --cluster demo-cluster \
    --region us-east-1 \
    --name alb-sample-app \
    --namespace game-2048

**Deploy the deployment, service and Ingress**

kubectl apply -f https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/examples/2048/2048_full.yaml

**configure IAM OIDC provider**

eksctl utils associate-iam-oidc-provider --cluster demo-cluster --approve

**setup alb**

Download IAM Policy:->

curl -O https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/v2.5.4/docs/install/iam_policy.json

Create IAM Policy:->

aws iam create-policy \
    --policy-name AWSLoadBalancerControllerIAMPolicy \
    --policy-document file://iam_policy.json


