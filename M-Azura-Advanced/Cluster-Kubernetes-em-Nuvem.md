# 🐳 Mapa Mental: **Docker e Kubernetes - Processamento, Logs, Rede e Orquestração**

## 🚀 **Docker - Processamento, Logs e Rede**

### ⚙️ **Processamento, Logs e Rede com Docker**
- **Limitando a Memória e CPU**
    - Comando `stress` e suas variações
    - **Passo 1: Limitar a Memória e CPU de um Contêiner Docker**
        - `docker run --memory="500m" --cpus="0.5" ubuntu`

### 📁 **Armazenamento de Dados com Docker**
- **Montando um "Mount" no Local de Armazenamento**
    - **Passo a Passo: Montar um Volume com Docker**
        - `docker run -v /caminho/do/volume:/caminho/dentro/do/container ubuntu`

### 🐍 **Criando Imagens Personalizadas a partir de Imagens de Linguagens de Programação**
- **Comandos**
    - Buscar no Hub Docker por uma imagem (exemplo com Python)
    - `docker pull python`
    - `docker images`
    - `mkdir python`
    - `cd python`
    - Criar o Dockerfile com as configurações desejadas
    - `docker build . -t python-app`

### 🚀 **Realizando o Upload de Imagens para o Hub do Docker**
- **Comandos para Upload**
    - Fazer login no Docker Hub
        - `docker login`
    - Criar e construir a imagem
        - `docker build . -t nomedousuario/nome_da_imagem`
    - Enviar para o Hub Docker
        - `docker push nomedousuario/nome_da_imagem`

### 🛠️ **Trabalhando com Docker Compose**
- **Introdução ao Docker Compose**
    - **Definição:** Docker Compose é uma ferramenta para definir e compartilhar aplicativos com vários contêineres.
    - **Comando Básico:**
        - `docker-compose up`
    - Permite definir ambientes de contêineres de forma simples, com múltiplos contêineres definidos em um único arquivo YAML.

---

## 🌐 **Kubernetes - Orquestração de Contêineres**

### 🔍 **Overview Kubernetes**
- **K8s**
    - Kubernetes é uma ferramenta de orquestração de contêineres, capaz de gerenciar a distribuição e escalabilidade de contêineres Docker em produção.
    - Ele permite automatizar a implantação, o dimensionamento e a operação de aplicações.
    - **Objetivo:** Gerenciar microserviços em containers Docker com alta disponibilidade e redundância.

### 📦 **Introdução ao Kubernetes e Orquestração de Contêineres**
- **O que é Kubernetes (K8s)?**
    - Kubernetes é uma plataforma open-source para automação de implantação, escalabilidade e gerenciamento de aplicativos em contêineres.
    - Ajuda a gerenciar e orquestrar contêineres, garantindo que a infraestrutura por trás deles seja eficiente e escalável.

### 🚀 **Ambiente de Desenvolvimento Kubernetes**
- **Criando um Cluster Kubernetes com Minikube**
    - **Minikube** é uma ferramenta que facilita a execução do Kubernetes localmente para estudos e testes.
    - **Comandos Básicos:**
        - `minikube start` - Inicia o cluster Kubernetes local
        - `kubectl get nodes` - Exibe os nós do cluster
    - Minikube é ideal para estudar o Kubernetes sem precisar de uma infraestrutura em nuvem.

### ☁️ **Cluster Kubernetes em Nuvem**
- **Cluster Kubernetes em Produção**
    - Em produção, o Kubernetes gerencia clusters de contêineres em ambientes de nuvem, garantindo alta disponibilidade e redundância.
    - **Componentes do Kubernetes:**
        - **Master Node**: Controla o cluster, gerencia a orquestração dos contêineres.
        - **Worker Nodes**: Executam as aplicações e contêineres.
        - **Pods**: Unidades básicas de implantação, que podem conter um ou mais contêineres.
        - **Services**: Facilita a comunicação entre diferentes Pods no cluster.
    - **Escalabilidade e Redundância**: Kubernetes gerencia automaticamente a distribuição de carga e a escalabilidade de contêineres, mantendo os serviços redundantes e resilientes.

---

## 💡 **Resumo das Ferramentas e Comandos**

- **Docker:**
    - Criação de contêineres: `docker run`
    - Visualizar imagens: `docker images`
    - Subir imagens para o Hub: `docker push`

- **Kubernetes:**
    - Criar cluster: `minikube start`
    - Gerenciar clusters: `kubectl`
    - Verificar estado dos pods: `kubectl get pods`

---
