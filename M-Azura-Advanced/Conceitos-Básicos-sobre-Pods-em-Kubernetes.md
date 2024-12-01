# 🐳 Mapa Mental: **Docker e Kubernetes - Processamento, Logs, Rede e Orquestração**

## 🚀 Docker

### 🧠 **Introdução ao Docker**
- **O que é Docker?**
    - Plataforma de containers para empacotar, distribuir e rodar aplicações.
    - Facilita a portabilidade, escalabilidade e isolamento.
- **Comandos Importantes**
    - `docker pull <imagem>`: Baixa uma imagem do Docker Hub.
    - `docker images`: Lista as imagens locais.
    - `docker run <imagem>`: Executa um contêiner a partir de uma imagem.
    - `docker exec -it <container> bash`: Acessa o terminal de um contêiner.

### 🛠️ **Trabalhando com Docker**

#### 🔒 **Montando Volumes e Armazenamento**
- **Montagem de Volumes**
    - Comando: `docker run -v /caminho/local:/caminho/container <imagem>`
    - Permite persistir dados de um contêiner.
    - Exemplo de comando para criar volume: 
      ```bash
      docker run -d -v /minha/pasta:/dados ubuntu
      ```
- **Comando de Criação de Volume**
    - `docker volume create <nome_do_volume>`

#### ⚙️ **Limitando Memória e CPU**
- **Comando para Limitar Recursos**
    - `docker run --memory="500m" --cpus="1.5" <imagem>`
    - Uso do comando `stress` para testar limites:
      ```bash
      stress --cpu 2 --timeout 60s
      ```

#### 📦 **Criando Imagens Personalizadas**
- **Criando uma Imagem Docker**
    - Criação de um Dockerfile para personalizar a imagem.
    - Comandos:
      ```bash
      docker build -t minha-imagem .
      docker run -dti --name meu-container minha-imagem
      ```

#### 🔼 **Realizando o Upload para Docker Hub**
- **Comando para Logar no Docker Hub**
    - `docker login`
- **Subindo Imagem para o Hub**
    - `docker build . -t nomedousuario/minha-imagem`
    - `docker push nomedousuario/minha-imagem`

## Kubernetes

### 🌐 **Overview Kubernetes**
- **O que é Kubernetes (k8s)?**
    - Kubernetes é uma ferramenta open-source para orquestrar containers, facilitando a gestão de microserviços em ambientes de produção.
    - Permite a automação de deploy, escala e operações de contêineres.
    - Gerencia containers de forma eficiente e com alta disponibilidade.

#### ⚙️ **Componentes do Kubernetes**
- **Cluster Kubernetes**
    - Um cluster Kubernetes é formado por nós (servidores de processamento) que executam aplicações em containers.
    - **Componentes principais:**
        - **Master Node**: Gerencia o estado do cluster e agendamentos.
        - **Worker Node**: Executa as aplicações.
        - **Pods**: Unidades mínimas de execução dentro do Kubernetes.

### 🛠️ **Ambiente de Desenvolvimento Kubernetes**

#### 🖥️ **Criando um Cluster Kubernetes com Minikube**
- **Minikube** é uma ferramenta que permite executar um cluster Kubernetes em uma única máquina para fins de desenvolvimento.
- **Comando para iniciar o Minikube:**
    ```bash
    minikube start
    ```

### ☁️ **Cluster Kubernetes em Nuvem**
- **Implantação em Produção**
    - Ao implantar o Kubernetes em nuvem, você obtém um conjunto de servidores (nós) em uma infraestrutura de nuvem como AWS, GCP, ou Azure.
    - **Componentes:**
        - Master Node
        - Worker Nodes
        - Pods para execução de containers.

### 🧩 **Conceitos Básicos sobre Pods em Kubernetes**

#### 📄 **Arquivos YAML no Kubernetes**
- **O que é YAML?**
    - YAML (Yet Another Markup Language) é usado para definir configurações de recursos no Kubernetes.
    - Exemplo de um arquivo YAML para criação de Pod:
      ```yaml
      apiVersion: v1
      kind: Pod
      metadata:
        name: meu-pod
      spec:
        containers:
        - name: nginx
          image: nginx:latest
      ```

#### 📦 **Pods em Kubernetes**
- **Pod**: A menor unidade executável no Kubernetes. Pode conter um ou mais containers.
- **Comando para criar um Pod:**
    ```bash
    kubectl apply -f pod.yaml
    ```

## 🖥️ **Trabalhando com Docker Compose**

### ⚙️ **Introdução e Instalação**
- **Docker Compose** é uma ferramenta para definir e rodar aplicativos multi-contêineres.
- **Instalação do Docker Compose**:
    - Em sistemas baseados em Linux:
      ```bash
      sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
      sudo chmod +x /usr/local/bin/docker-compose
      ```

### 📝 **Arquivo docker-compose.yml**
- Exemplo de arquivo `docker-compose.yml`:
  ```yaml
  version: '3'
  services:
    web:
      image: nginx
      ports:
        - "8080:80"
    app:
      image: node
      command: node app.js
