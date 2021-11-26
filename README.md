# Kubernetes

## Intro

### O que é?
O Kubernetes é uma plataforma de código aberto de nível de produção que orquestra o agendamento e a execução de contêineres de aplicativos dentro e entre clusters de computador.
### Composição de um Cluster
Um cluster Kubernetes consiste em dois tipos de recursos:
- A Camada de gerenciamento (Control Plane) coordena o cluster
- Os Nós (Nodes) são os nós de processamento que executam aplicativos

### Exemplo de deployment através de arquivo .yaml
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: myapp
spec:
  selector:
    matchLabels:
      app: myapp
  template:
    metadata:
      labels:
        app: myapp
    spec:
      containers:
      - name: myapp
        image: myapp-docker-image
        resources:
          limits:
            memory: "128Mi"
            cpu: "500m"
        ports:
        - containerPort: 80

```

## Bons links para estudo
- [Documentação - Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)
- [Minikube - Como rodar kubernetes em localhost](https://minikube.sigs.k8s.io/docs/start/)
