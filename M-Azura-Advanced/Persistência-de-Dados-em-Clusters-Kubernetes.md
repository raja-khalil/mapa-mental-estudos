# 🐳 Mapa Mental: **Docker e Kubernetes - Processamento, Logs, Rede e Orquestração**

## 🚀 Docker

### 🧩 **Processamento, Logs e Rede com Docker**

- **Limitando a Memória e CPU**
    - Comando `stress` e suas variações
    - **Passo 1: Limitar a Memória e CPU de um Contêiner Docker**
        1. Crie ou modifique o Dockerfile
        2. Use o comando: 
            ```bash
            docker run -dti --memory="256m" --cpus="1" nome-da-imagem
            ```

### 📦 **Criando Imagens Personalizadas a partir de Imagens de Linguagens de Programação**
- **Comandos**
    - Buscar uma imagem no Docker Hub (exemplo: Python)
    - `docker pull python`
    - `docker images`
    - Criar diretório:
        ```bash
        mkdir python
        cd python
        ```
    - Criar Dockerfile e construir imagem:
        ```bash
        docker build . -t nome-usuario/python-custom
        ```

### ☁️ **Realizando o Upload de Imagens para o Hub do Docker**
- **Comandos**
    - Fazer login no Docker Hub
        ```bash
        docker login
        ```
    - Construir e enviar a imagem para o Docker Hub:
        ```bash
        docker build . -t nome-usuario/nome-imagem
        docker push nome-usuario/nome-imagem
        ```

### 🐳 **Trabalhando com Docker Compose**
- **Introdução e Instalação**
    - O Docker Compose é uma ferramenta para definir e rodar aplicações com múltiplos containers.
    - Com Compose, você pode configurar aplicações em um arquivo YAML e gerenciar múltiplos containers de forma simplificada.
    - **Exemplo de Comando para Rodar um Compose**:
        ```bash
        docker-compose up -d
        ```

---

## 🚀 Kubernetes

### 🔍 **Overview Kubernetes (K8s)**
- **O que é Kubernetes?**
    - Kubernetes é uma plataforma de orquestração de containers, projetada para gerenciar a execução de microserviços em containers Docker.
    - Ele permite a automação da implantação, escalabilidade e operações de aplicações em containers.
    - **Kubernetes usa Pods**, que são unidades de execução para containers.

### ⚙️ **Introdução ao Kubernetes e Orquestração de Contêineres**
- **O que é o Kubernetes?**
    - Kubernetes (K8s) é uma ferramenta open-source para orquestrar containers. Ela gerencia clusters de máquinas e pode automatizar o deploy, a escalabilidade e o gerenciamento de aplicações em containers.

### 🖥️ **Ambiente de Desenvolvimento Kubernetes**
- **Criando um Cluster Kubernetes com Minikube**
    - **Minikube** é uma ferramenta para rodar Kubernetes localmente.
    - Com Minikube, é possível criar um cluster Kubernetes para testes e desenvolvimento.
    - Comandos para rodar Minikube:
        ```bash
        minikube start
        ```

### ☁️ **Cluster Kubernetes em Nuvem**
- **Cluster Kubernetes em Produção**
    - **Componentes do Kubernetes**:
        - Um cluster Kubernetes é composto por nós, que são máquinas físicas ou virtuais.
        - Cada nó possui um **master** que controla a distribuição de tarefas, e **workers** que executam os containers.
    - **Exemplo de Escalabilidade**:
        - O Kubernetes permite a criação de múltiplos Pods e replicas de aplicações para garantir a alta disponibilidade.

### 🛠️ **Conceitos Básicos sobre Pods em Kubernetes**
- **Arquivo YAML**
    - YAML é uma linguagem de serialização de dados usada para configuração no Kubernetes.
    - Arquivos YAML descrevem a configuração dos Pods e outros recursos do Kubernetes.
    - **Exemplo de arquivo YAML para um Pod**:
        ```yaml
        apiVersion: v1
        kind: Pod
        metadata:
          name: nginx-pod
        spec:
          containers:
            - name: nginx
              image: nginx:latest
        ```

### 🌐 **Serviço de Acesso para Kubernetes Pods**
- **Criando um NodePort**
    - O NodePort é um tipo de serviço Kubernetes que expõe o pod para acesso externo.
    - **Exemplo de arquivos YAML para NodePort e Pod**:
        - `nodePort.yml`:
            ```yaml
            apiVersion: v1
            kind: Service
            metadata:
              name: nginx-service
            spec:
              type: NodePort
              ports:
                - port: 80
                  targetPort: 80
                  nodePort: 30001
              selector:
                app: nginx
            ```
        - `pod.yml`:
            ```yaml
            apiVersion: v1
            kind: Pod
            metadata:
              name: nginx-pod
            spec:
              containers:
                - name: nginx
                  image: nginx:latest
            ```

### 💾 **Persistência de Dados em Clusters Kubernetes**
- **Introdução ao PV e PVC (Persistent Volumes e Persistent Volume Claims)**
    - **O que é PV e PVC?**
        - **PV** é um recurso de armazenamento em Kubernetes que existe independentemente de um Pod.
        - **PVC** é uma requisição de armazenamento por um Pod, que se associa a um PV.
    - **Comandos de Criação**:
        - Criar um PV com YAML:
            ```yaml
            apiVersion: v1
            kind: PersistentVolume
            metadata:
              name: pv-storage
            spec:
              capacity:
                storage: 1Gi
              accessModes:
                - ReadWriteOnce
              hostPath:
                path: "/mnt/data"
            ```
        - Criar um PVC:
            ```yaml
            apiVersion: v1
            kind: PersistentVolumeClaim
            metadata:
              name: pvc-storage
            spec:
              resources:
                requests:
                  storage: 1Gi
            ```

---

Com este mapa mental, você tem uma visão completa dos principais conceitos e comandos envolvidos no uso de **Docker e Kubernetes** para containerização, orquestração e gerenciamento de aplicações e dados. Cada seção contém os principais passos, comandos e arquivos de configuração para realizar operações no Docker e no Kubernetes, fornecendo um guia de uso tanto para iniciantes quanto para desenvolvedores mais experientes.
