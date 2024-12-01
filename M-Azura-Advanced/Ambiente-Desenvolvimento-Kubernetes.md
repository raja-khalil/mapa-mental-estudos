# 🐳 Mapa Mental: **Docker e Kubernetes - Processamento, Logs, Rede e Orquestração**

## 🚀 Docker - Processamento, Logs e Rede

### ⚙️ Processamento, Logs e Rede com Docker
- **Limitando a Memória e CPU**
    - Comando `stress` e suas variações
    - Passo 1: Limitar a Memória e CPU de um Contêiner Docker
        1. **Crie ou inicie o contêiner** com limites:
           ```bash
           docker run -d --name nome-container --memory="256m" --cpus="0.5" ubuntu
           ```
        2. **Verifique o uso de memória e CPU**:
           ```bash
           docker stats nome-container
           ```
        3. **Comando para testar a carga**:
           ```bash
           stress --cpu 2 --timeout 60s
           ```

### 📁 Armazenamento de Dados com Docker
- **Montando um "Mount"**
    - Montar um volume no Docker permite que os dados de um contêiner sejam armazenados de maneira persistente, fora do contêiner.
    - **Comandos**:
        - Criar um volume:
          ```bash
          docker volume create meu-volume
          ```
        - Iniciar um contêiner com o volume montado:
          ```bash
          docker run -d -v meu-volume:/app/data ubuntu
          ```
        - Verificar volumes:
          ```bash
          docker volume ls
          ```

### 🐍 Criando Imagens Personalizadas a partir de Imagens de Linguagens de Programação
- **Comandos para trabalhar com imagens**:
    - Buscar no Docker Hub uma imagem (exemplo: Python):
      ```bash
      docker pull python
      ```
    - Criar diretório para seu projeto:
      ```bash
      mkdir python
      cd python
      ```
    - Criar um **Dockerfile**:
      ```dockerfile
      FROM python:3.9-slim
      WORKDIR /app
      COPY . /app
      RUN pip install -r requirements.txt
      CMD ["python", "app.py"]
      ```
    - Construir a imagem:
      ```bash
      docker build -t meu-usuario/python-app .
      ```

### 🔼 Realizando o Upload de Imagens para o Hub do Docker
- **Comandos para fazer upload**:
    - Fazer login no Docker Hub:
      ```bash
      docker login
      ```
    - Gerar imagem com seu nome de usuário:
      ```bash
      docker build . -t meu-usuario/nome-imagem
      ```
    - Enviar imagem para o Docker Hub:
      ```bash
      docker push meu-usuario/nome-imagem
      ```

### ⚡ Trabalhando com Docker Compose
- **Introdução e Instalação do Docker Compose**
    - **Docker Compose**:
      - Definição: Docker Compose é uma ferramenta desenvolvida para definir e compartilhar aplicativos com múltiplos contêineres. Com o Compose, você pode facilmente configurar ambientes de desenvolvimento e produção.
    - **Comandos**:
      - Criar um arquivo `docker-compose.yml`:
        ```yaml
        version: '3'
        services:
          web:
            image: nginx
            ports:
              - "80:80"
          db:
            image: mysql
            environment:
              MYSQL_ROOT_PASSWORD: example
        ```
      - Subir os contêineres com Docker Compose:
        ```bash
        docker-compose up
        ```

---

## ☸️ Kubernetes - Orquestração de Contêineres

### ⚙️ Overview Kubernetes
- **O que é Kubernetes (K8s)?**
    - O Kubernetes (K8s) é uma ferramenta open-source de orquestração de contêineres que facilita o gerenciamento de contêineres em larga escala. Ele permite automação no gerenciamento, escalabilidade e monitoramento de contêineres.
    - **Principais Benefícios**:
        - Gerencia microserviços em contêineres Docker.
        - Oferece redundância e escalabilidade.
        - Funciona como um orquestrador de contêineres, facilitando a gestão de sistemas distribuídos.
  
### 🛠️ Introdução ao Kubernetes e Orquestração de Contêineres
- **O que é Kubernetes?**
    - Kubernetes é uma plataforma para automatizar a implantação, o dimensionamento e o gerenciamento de aplicações containerizadas. Ele é composto por múltiplos componentes, como o **API Server**, **Scheduler**, **Controller Manager** e **Kubelet**, que trabalham juntos para gerenciar os contêineres.

### 💻 Ambiente de Desenvolvimento Kubernetes
- **Criando um Cluster Kubernetes com Minikube**
    - **Minikube**: Ferramenta que permite executar Kubernetes (k8s) localmente em sua máquina para fins de desenvolvimento e testes.
    - **Passo a Passo para criar um cluster com Minikube**:
        1. Instalar o Minikube:
           ```bash
           brew install minikube  # para MacOS
           ```
        2. Iniciar o cluster:
           ```bash
           minikube start
           ```
        3. Verificar o status do cluster:
           ```bash
           minikube status
           ```
        4. Acessar o painel do Kubernetes:
           ```bash
           minikube dashboard
           ```

---

## 📦 Exemplos de Comandos Importantes para Docker e Kubernetes

### 🐳 Docker
- **Verificar contêineres em execução**:
  ```bash
  docker ps
