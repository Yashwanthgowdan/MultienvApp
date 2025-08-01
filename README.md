# MultienvApp

A multi-environment deployment setup using Docker and Docker Compose, supporting both development and production backends, with a React-based frontend.

## Prerequisites

Ensure the following are installed on your environment:
* Docker
* Docker Compose
* Git

Install commands (Ubuntu):
sudo apt update                                       #to update ubuntu to latest version
sudo apt install -y docker.io docker-compose git      #install Docker, Docker-compose and Git to the environment
sudo usermod -aG docker ubuntu                        #Grant access to user to user Docker

## Environment Used

* Environment Type: EC2
* OS: Ubuntu 22.04
* Instance Specs: t2.medium
* Open Ports: 22, 3000, 3001, 3002

## Docker Configuration

Create Dockerfile for both Frontend and Backend(Seperate files for Dev and Prod)
Create docker-compose.yml file with the MultienvApp folder
MultiEnvApp/
├── docker-compose.yml
├── backend/
│   ├── dev/
│   │   ├── app.py
│   │   ├── requirements.txt
│   │   ├── Dockerfile
│   │   └── .env
│   └── prod/
│       ├── app.py
│       ├── requirements.txt
│       ├── Dockerfile
│       └── .env
└── frontend/
    ├── src/
    ├── public/
    ├── Dockerfile
    └── package.json

## Application Deployment

docker-compose build            #Build service
docker-compose up -d            #Start service

###Verify
docker ps                       #Check running containers

* Frontend: Port `3000`
* Backend-Dev: Port `3001`
* Backend-Prod: Port `3002`

## Test Routes

Open in browser:
http://[IP]:3000
<img width="1365" height="682" alt="image" src="https://github.com/user-attachments/assets/1225ca7b-5249-47ca-876d-1bef5be406b9" />

http://[IP]:3000/dev
<img width="1363" height="676" alt="image" src="https://github.com/user-attachments/assets/51814512-7990-4883-b53e-04225a1eef11" />

http://[IP]:3000/prod
<img width="1365" height="682" alt="image" src="https://github.com/user-attachments/assets/c48627f1-a3c1-4ac2-b9f4-dcf9c7edbffe" />

