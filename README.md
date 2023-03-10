
# Continuous deployment to Kubernetes with GitHub Actions
This simple example show how to set up a containerized application in Kubernetes with a very simple CI/CD pipeline to manage deployment using GitHub Actions

The integration of GitHub Actions with a Kubernetes cluster provides a powerful CI/CD solution for containerized applications, automating the deployment and testing processes and helping to ensure a smooth and efficient development workflow.

In this example, the infrastructure is deployed in AWS. You can also use another provider or a local cluster.

## Workflow

![](/images/diagram.png)

The repo contains a Dockerfile, which will be used to build a docker image of the application. You can maintain any number of environments for your application like Production, QnA, Staging, Development, etc. For sake of simplicity, we will be maintaining only two deployment environments of the application. There are only two branches in the repo - Main(Prod) and Dev

## Requirements: 

- You must have access configured in the AWS CLI and have access rights to create EC2 instances.

- You will also need to add secrets to your repository


## Secrets:
![](/images/secrets.png)

`KUBE_CONFIG – required: A base64-encoded kubeconfig file with credentials for Kubernetes to access the cluster. You can get it by running the following command:`
```
cat $HOME/.kube/config | base64
```
`AWS_ACCESS_KEY_ID - your access key for your AWS account.`

`AWS_SECRET_ACCESS_KEY - your secret key for your AWS account.`

`DOCKERHUB_TOKEN - your personal access tokens Docker Hub registry.`

`DOCKERHUB_USERNAME - your username Docker Hub registry.`

`PRODUCT_REPO_NAME - your product name.`
