# 🐳 Mapa Mental: **Docker e Kubernetes - Processamento, Logs, Rede e Orquestração**

## 🚀 Docker - Processamento, Logs e Rede

### ⚙️ Processamento e Limitação de Memória e CPU
- **Comando para limitar recursos de contêiner:**
    - `docker run -dti --memory="500m" --cpus="1" ubuntu`
    - **Comando `stress` para testar recursos:**
        - `apt install stress`
        - `stress --cpu 2 --timeout 60s`

### 📁 Armazenamento de Dados com Docker
- **Montando um "Mount" de volume:**
    - **Comando:**
        - `docker run -v /meu/diretorio:/container/diretorio -d nome_da_imagem`
    - **Objetivo:** Persistir dados de contêineres em volumes externos, garantindo que os dados não sejam perdidos ao remover o contêiner.

### 📝 Criando Imagens Personalizadas
- **Primeiro Dockerfile:**
    - **Comando:**
        - `docker run -dti --name ubuntu-python ubuntu`
        - `docker exec -ti ubuntu-python bash`
        - `apt update && apt install python`
    - **Objetivo:** Criar imagens customizadas, adicionar dependências e garantir a portabilidade.

### 🌐 Realizando o Upload de Imagens para o Docker Hub
- **Comandos para upload:**
    - `docker login` (para autenticar no Docker Hub)
    - `docker build . -t username/nomedaimagem`
    - `docker push username/nomedaimagem`
    - **Objetivo:** Compartilhar imagens Docker personalizadas com a comunidade através do Docker Hub.

---

## 🐋 Trabalhando com Docker Compose

### 🔧 Introdução e Instalação do Docker Compose
- **Definição:** 
    - O **Docker Compose** é uma ferramenta para definir e compartilhar aplicativos multi-contêiner. 
    - Com Compose, você pode usar arquivos YAML para configurar os serviços, redes e volumes de um aplicativo de forma simplificada.
  
- **Comandos para Instalar o Docker Compose:**
    - **Para sistemas baseados em Linux (exemplo Ubuntu):**
        ```bash
        sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
        sudo chmod +x /usr/local/bin/docker-compose
        ```
    - **Verificar instalação:**
        ```bash
        docker-compose --version
        ```

- **Exemplo básico de arquivo `docker-compose.yml`:**
    ```yaml
    version: '3'
    services:
      web:
        image: nginx
        ports:
          - "8080:80"
      db:
        image: postgres
        environment:
          POSTGRES_PASSWORD: example
    ```

---

## ☸️ Overview Kubernetes

### 🔍 O que é Kubernetes (K8s)?
- **Kubernetes (K8s)** é uma plataforma open-source de orquestração de contêineres, projetada para automatizar o gerenciamento, a escalabilidade e a implantação de aplicativos em contêineres.
- **Objetivo:**
    - Gerenciar **microserviços** em contêineres Docker com redundância e escalabilidade.
    - Permitir **orquestração** de contêineres, ou seja, organizar e controlar os containers em um ambiente de produção.

### ⚙️ Funcionalidades principais do Kubernetes
- **Redundância:** Kubernetes replica contêineres para garantir alta disponibilidade.
- **Escalabilidade:** Permite aumentar ou diminuir o número de contêineres automaticamente, conforme a carga de trabalho.
- **Gerenciamento de contêineres:** Controla e distribui automaticamente os contêineres pelos nós do cluster.
- **Auto-recuperação:** Se um contêiner falhar, o Kubernetes pode reiniciá-lo automaticamente.

### 🛠️ Comandos Básicos do Kubernetes
- **Instalar o kubectl (cliente Kubernetes):**
    ```bash
    curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
    chmod +x ./kubectl
    sudo mv ./kubectl /usr/local/bin/kubectl
    ```

- **Criar um pod simples no Kubernetes:**
    ```bash
    kubectl run nome-do-pod --image=nginx
    ```

- **Exibir todos os pods em execução:**
    ```bash
    kubectl get pods
    ```

---

## 🔗 Conclusão

- O **Docker** é a base para o desenvolvimento de aplicativos portáveis e escaláveis, facilitando a criação, execução e compartilhamento de contêineres.
- O **Docker Compose** ajuda a definir e orquestrar múltiplos contêineres em um único arquivo de configuração, simplificando o desenvolvimento e a implantação de aplicações.
- O **Kubernetes** leva a orquestração a um nível superior, gerenciando a escala e a alta disponibilidade de aplicativos distribuídos em contêineres.

Combinando essas ferramentas, é possível desenvolver, testar e escalar aplicativos de forma eficiente, moderna e totalmente integrada.

---

Esse mapa mental proporciona uma visão completa das ferramentas de contêinerização e orquestração, com foco em Docker e Kubernetes, abordando desde a criação de imagens até o gerenciamento avançado de microserviços. 🚀
