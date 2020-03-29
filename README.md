# Jenkins CI/CD Pipeline (Kubernetes Deployment)
![VPC-Image](https://github.com/georgio-sd/jenkins-cicd-pipeline/raw/master/pipeline.jpg)

Authentication:
* Jenkins GitHub Branch Source plugin for GitHub authentication
* Add jenkins user to docker group on Jenkins server for letting Jenkins use Docker
* awscli with custom script(token-update) on Jenkins server for AWS ECR (Docker repo) authentication 
* Copy kubectl to /usr/bin and kubernetes credentials to ~/.kube/config (jenkins user) on Jenkins server for letting Jenkins use Kebernetes
* Add CroneJob https://github.com/georgio-sd/kubernetes-aws-ecr-token-updater on Kubernetes Cluster for AWS ECR (Docker repo) authentication

(!) For additional security, the part of Jenkins job, which builds a Docker image, should be done by a Jenkins Agent to prevent potential malicious code from getting access to Jenkins credentials and Kubernetes Cluster.
