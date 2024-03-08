Login to ECR 
$ aws ecr get-login-password --region | docker login --username AWS --password-stdin .dkr.ecr..amazonaws.com

Build the Docker image 
$ docker build -t .dkr.ecr..amazonaws.com/:latest .

Push the Docker image to ECR 
$ docker push .dkr.ecr..amazonaws.com/:latest
