# Reactjs Application Deployment

## Pre-requisites

```bash
- Install Git
- Install nodejs
- Install Docker
```

## Deploy application manually

1. Install Git, Nodejs and Docker

Install Git

```bash
yum install git -y
```

Install Nodejs

```bash
sudo yum install -y gcc-c++ make
curl -sL https://rpm.nodesource.com/setup_13.x | sudo -E bash -
sudo yum install -y nodejs
```

2. Build package

```bash
npm install
```

3. Deploy application

```bash
npm start
```

## Dockerize Application

1. Install docker

```bash
yum install docker -y
service docker start
```

2. Build docker image and push image to dockerhub

```bash
docker build -t naresh240/reactjsexample:v1 .
docker login
docker push naresh240/reactjsexample:v1
```

3. Run container

```bash
docker run --name reactjs-container -p 3000:3000 -d naresh240/reactjsexample:v1
```

![image](https://github.com/Naresh240/reactjs-app/assets/58024415/3545fde7-0774-4275-80db-9db647d4f6fa)

4. Check application output

![image](https://github.com/Naresh240/reactjs-app/assets/58024415/288827c6-82ce-47f1-ae60-c430f46ba88b)

## Deploy application in k8s

1. Install minikube using [minikube-setup](https://github.com/Naresh240/kubernetes/blob/main/minikube-setup/README.md)

2. Deploy Application in minikube

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

3. Check application output

![image](https://github.com/Naresh240/reactjs-app/assets/58024415/ebef3319-ff69-4ee0-82f8-fe08867442a4)
