# EKS Game 2048

Este proyecto despliega una aplicación del juego 2048 en un clúster de Amazon EKS (Elastic Kubernetes Service). Utiliza Kubernetes para gestionar el despliegue, escalado y exposición del servicio. El objetivo de este proyecto es aprender sobre el despliegue de aplicaciones en Kubernetes y la integración con EKS.

## Tecnologías utilizadas

- **Amazon EKS**: Servicio de Kubernetes gestionado en AWS.
- **Kubernetes**: Para gestionar los recursos y el despliegue de la aplicación.
- **AWS CLI / kubectl**: Herramientas para interactuar con AWS y Kubernetes.

## Requisitos

Antes de empezar, asegúrate de tener instaladas las siguientes herramientas:

- [AWS CLI](https://aws.amazon.com/cli/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [eksctl](https://eksctl.io/)

## Despliegue de la aplicación

### 1. Crear un clúster de EKS

Si no tienes un clúster de EKS, puedes crear uno usando `eksctl`:

eksctl create cluster --name test-cluster --region eu-west-1 --nodegroup-name workers --node-type t2.micro --nodes 2

### 2. Configurar kubectl

aws eks --region eu-west-1 update-kubeconfig --name test-cluster

### 3. Desplegar la aplicación

kubectl apply -f manifests/deployment-game2048.yaml

kubectl apply -f manifests/svc.yaml

### 4. Resultado de kubectl get all -n default

A continuación se muestra el resultado de ejecutar kubectl get all -n default:

![image](https://github.com/user-attachments/assets/78c96b12-7a7d-488e-b0d6-4e9da7bbf628)

Créditos
La imagen de Docker utilizada para este proyecto no fue creada por mí, sino que se encuentra disponible en Docker Hub bajo el nombre blackicebird/2048. Puedes encontrarla en el siguiente enlace:

blackicebird/2048 en Docker Hub
