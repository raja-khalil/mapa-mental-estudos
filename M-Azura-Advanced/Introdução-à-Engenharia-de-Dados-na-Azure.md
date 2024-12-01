# 🐳 Mapa Mental: **Docker, Kubernetes, Serverless, Azure e Engenharia de Dados**

## 🐋 Docker - Processamento, Logs, Rede e Armazenamento
### ⚙️ Processamento, Logs e Rede com Docker
- **Limitando a Memória e CPU**
    - Comando `stress` e suas variações
    - Passo 1: Limitar a Memória e CPU de um Contêiner Docker
        - Criar ou rodar um contêiner com limites de recursos.
        - Exemplo de comando:
            ```bash
            docker run -d --memory="256m" --cpus="1.0" --name test_container ubuntu
            ```

### 📦 Armazenamento de Dados com Docker
- **Montando um Volume no Docker**
    - Passo a Passo: Montar um Volume com Docker ("Mount")
    - Exemplo de comando:
        ```bash
        docker run -d -v /host/path:/container/path --name my_container ubuntu
        ```

### 🐍 Criando Imagens Personalizadas a partir de Imagens de Linguagens de Programação
- **Exemplo de comandos**:
    - Buscar no hub.docker uma imagem (exemplo: python)
    - Comandos:
        ```bash
        docker pull python
        docker images
        mkdir python
        cd python
        ```

### 🌍 Realizando o Upload de Imagens para o Hub do Docker
- **Comandos**:
    - Login no Docker Hub:
        ```bash
        docker login
        ```
    - Construir e enviar a imagem:
        ```bash
        docker build . -t username/imagename
        docker push username/imagename
        ```

### 🛠️ Trabalhando com Docker Compose
- **Introdução e Instalação do Docker Compose**
    - **Definição**: Docker Compose é uma ferramenta para definir e compartilhar aplicativos com múltiplos contêineres.
    - **Comandos comuns**:
        ```bash
        docker-compose up
        docker-compose down
        ```

## 🚀 Kubernetes - Orquestração de Contêineres
### 🔍 Overview Kubernetes
- **O que é Kubernetes?**
    - Kubernetes (k8s) é uma ferramenta de orquestração de contêineres que facilita o gerenciamento de microserviços e contêineres Docker.
    - Ele permite a gestão de aplicações em escala com alta disponibilidade e redundância.

### 🚀 Ambiente de Desenvolvimento Kubernetes
- **Criando um Cluster Kubernetes com Minikube**
    - **Minikube**: Ferramenta para rodar Kubernetes localmente.
    - Comandos:
        ```bash
        minikube start
        kubectl get nodes
        ```

### ☁️ Cluster Kubernetes em Nuvem
- **Cluster Kubernetes em Produção**
    - Componentes do Kubernetes: Pods, Nodes, Services, Deployments.
    - Exemplo de comandos:
        ```bash
        kubectl apply -f deployment.yml
        kubectl get pods
        ```

### 🧱 Conceitos Básicos sobre Pods em Kubernetes
- **YAML no Kubernetes**
    - O YAML é amplamente utilizado para configurar recursos no Kubernetes.
    - Exemplo de arquivo YAML para Pod:
        ```yaml
        apiVersion: v1
        kind: Pod
        metadata:
          name: example-pod
        spec:
          containers:
          - name: nginx
            image: nginx
        ```

### 🌐 Serviço de Acesso para Kubernetes Pods
- **Criando um NodePort**
    - Arquivos necessários:
        - `nodePort.yml`
        - `pod.yml`
    - Exemplo de comando:
        ```bash
        kubectl apply -f nodePort.yml
        kubectl apply -f pod.yml
        ```

### 🗄️ Persistência de Dados em Clusters Kubernetes
- **Introdução ao PV e PVC**
    - **PV (Persistent Volume)** e **PVC (Persistent Volume Claim)** são usados para gerenciar armazenamento persistente no Kubernetes.
    - Exemplo de comando:
        ```yaml
        apiVersion: v1
        kind: PersistentVolumeClaim
        metadata:
          name: my-pvc
        spec:
          accessModes:
            - ReadWriteOnce
          resources:
            requests:
              storage: 1Gi
        ```

## ⚡ Serverless
### 🌩️ Overview Serverless
- **O que é Serverless?**
    - Serverless permite a execução de funções diretamente na nuvem sem se preocupar com a infraestrutura.
    - Exemplos:
        - Validação de documentos
        - Gerenciamento de usuários
        - Escalabilidade automática de funções

## 🌐 Azure - Ferramentas e Serviços
### 🌍 Azure API Management Dashboard
- **Azure API Management**
    - Gerenciamento de APIs para integrar e gerenciar serviços web.
    - Papel do gerenciamento de API: Fornece controle de tráfego, segurança e integração.
    - Exemplo de comando:
        ```bash
        az apim create --name MyApiManagement --resource-group MyResourceGroup
        ```

### 📊 Introdução à Engenharia de Dados na Azure
- **Visão Geral sobre Engenharia de Dados**
    - **Ciência de Dados**: Combina ciência da computação com ferramentas estatísticas para análise de dados.
    - **Principais componentes**:
        - Extração, transformação e carregamento (ETL)
        - Armazenamento e processamento de grandes volumes de dados.
