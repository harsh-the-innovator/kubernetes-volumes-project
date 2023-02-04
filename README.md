# kubernetes-volumes-project

## Project Setup Requirements

- docker (see https://docs.docker.com/get-docker/)
- minikube (see https://minikube.sigs.k8s.io/docs/start/)
- kubectl (see https://kubernetes.io/docs/tasks/tools/)

## Steps to start project

### Build Image and push to Docker Hub

- `docker build -t kub-data-demo:tag-name .` (tag-name is 'latest' by default if you don't add. _Also change your image name in deployment.yaml file also_)
- `docker push your-dockerhub-user-name/kub-data-demo:tag-name`

### Start Minikube in terminal

- `minikube start` ( Need docker or docker-desktop up and running for starting )
- `minikube dashboard` ( Use this command only when you want to see your kubernetes dashboard )
- `minikube service story-service` ( This command will only run after setting up deployments and services
  and returns the Kubernetes URL(s) for service(s) in your local cluster. )

### Set up Deployments, Services, Volumes, Environments

- `kubectl apply -f service.yaml` (Set up service)
- `kubectl apply -f host-pv.yaml` (Set up Persistent Volume)
- `kubectl apply -f host-pvc.yaml` (Set up Persistent volume Claim)
- `kubectl apply -f environment.yaml` (Set up Environment Variables usin ConfigMap)
- `kubectl apply -f deployment.yaml` (Finally setup deployment)

### To run container locally and not inside Kubernetes cluster

- `docker-compose up`
