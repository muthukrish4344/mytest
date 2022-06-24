# devops-hiring

Hugo (Linux) installation steps: https://gohugo.io/getting-started/installing#debian-and-ubuntu

Command to generate static site (inside quickstart folder): `hugo`

Microk8s instructions: https://microk8s.io/

Nginx Ingress Controller instructions: https://kubernetes.github.io/ingress-nginx/deploy/#microk8s


## Instructions:

### Running it on EC2 instance locally
0. Setup a new EC2 instance
1. Clone the repo in the instance
2. Install hugo as per instructions and run the build command (`hugo server -D --bind 0.0.0.0`) inside `quickstart` folder to test the website.

### Deploying with s3
1. Run `hugo` inside `quickstart` folder to generate the static site in the `public` folder.
2. Host the generated files on s3 as a publicly accessible website.

### Running it with docker
1. Write an nginx configuration that will host the site
2. Write a dockerfile to dockerize the site hosting
3. Build docker image and push to dockerhub
4. Create new EC2 instance and run docker container (without k8s) there directly and demonstrate by accessing from public ip

### Running it with k8s
1. Write k8s yaml file for deployment, service and ingress (assuming nginx ingress)
2. Create new EC2 instance and install microk8s on it.
3. Create another EC2 instance and it as a node of the microk8s cluster.
4. Install nginx ingress on k8s cluster (via helm-chart)
5. Apply k8s config to cluster
6. Scale up pods of nginx deployment
