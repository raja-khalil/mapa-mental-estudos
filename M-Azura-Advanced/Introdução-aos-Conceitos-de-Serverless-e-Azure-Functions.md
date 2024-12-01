# 🐳 Mapa Mental: **Docker, Kubernetes, Serverless, Azure e Engenharia de Dados**

## 🐋 Docker

### 🧑‍💻 **Processamento, Logs e Rede com Docker**
- **Limitando a Memória e CPU**
  - Comando `stress` e suas variações
  - **Passo 1**: Limitar a Memória e CPU de um Contêiner Docker
    - Comando:
      - `docker run -dti nome imagem`
      - `docker exec -ti nome_container comando`
  
### 📦 **Armazenamento de Dados com Docker**
- **Montando um "Mount" no Local de Armazenamento**
  - Passo a Passo para montar um volume:
    - `docker volume create nome_volume`
    - `docker run -v /local:/container nome_imagem`

### 🛠️ **Criando Dockerfile**
- **Primeiro Dockerfile**
  - Para criar sua imagem personalizada:
    - Comandos:
      - `docker build . -t nome_usuario/nome_imagem`
      - `docker run -dti nome_imagem`

### 🐍 **Criando Imagens Personalizadas a partir de Linguagens de Programação**
- **Exemplo com Python**
  - Buscar imagem no Hub:
    - Comando:
      - `docker pull python`
      - `docker images`
    - Criar e rodar contêiner:
      - `mkdir python`
      - `cd python`

### 🚚 **Realizando o Upload de Imagens para o Docker Hub**
- **Comandos**
  - `docker login`
  - `docker build . -t nome_usuario/nome_imagem`
  - `docker push nome_usuario/nome_imagem`

### 🏗️ **Trabalhando com Docker Compose**
- **Introdução e Instalação**
  - Docker Compose é uma ferramenta para definir e compartilhar aplicativos com múltiplos contêineres.

---

## 🧑‍💻 Kubernetes

### 🔍 **Overview Kubernetes**
- **O que é Kubernetes (k8s)?**
  - Kubernetes é uma ferramenta de orquestração de contêineres que ajuda a gerenciar a implantação, escalabilidade e operação de contêineres, como os do Docker.

### 🚀 **Introdução ao Kubernetes e Orquestração de Contêineres**
- Kubernetes permite gerenciar microserviços em contêineres, garantindo alta disponibilidade e redundância.

### 🌐 **Ambiente de Desenvolvimento Kubernetes**
- **Criando um Cluster com Minikube**
  - Minikube é uma ferramenta que permite executar o Kubernetes em sua máquina local para fins de estudo.

### ☁️ **Cluster Kubernetes em Nuvem**
- **Componentes do Kubernetes**
  - Um cluster Kubernetes é composto por servidores de processamento (nós), que executam as aplicações de contêiner.

### 📦 **Conceitos Básicos sobre Pods em Kubernetes**
- **YAML (YML)**
  - YAML é uma linguagem de serialização de dados comumente usada em arquivos de configuração do Kubernetes.
  
### 🌐 **Serviço de Acesso para Kubernetes Pods**
- **Criando um NodePort**
  - Comandos para expor pods para o exterior:
    - Criar `nodePort.yml`, `pod.yml`

### 💾 **Persistência de Dados em Clusters Kubernetes**
- **PV e PVC**
  - O gerenciamento de armazenamento no Kubernetes envolve o uso de Volumes Persistentes (PV) e Claims de Volumes Persistentes (PVC).

---

## 🌐 Serverless

### ⚡ **Overview Serverless**
- **O que é Serverless?**
  - Aplicações sem servidor, onde o código é executado diretamente na nuvem, sem necessidade de gerenciamento de infraestrutura.
  
### 🏗️ **Arquitetura Serverless**
- **Arquitetura Tradicional Monolítica** vs **Arquitetura Serverless**
  - Serverless permite escalabilidade automática e cobrança baseada no uso.

---

## ☁️ Azure

### 🌟 **Azure API Management Dashboard**
- **Gerenciamento de API no Azure**
  - O Azure API Management permite criar, publicar, proteger e monitorar APIs.

### 📊 **Introdução à Engenharia de Dados na Azure**
- **Visão Geral sobre Engenharia de Dados**
  - Engenharia de dados envolve o processo de coletar, limpar, organizar e analisar dados, especialmente em ambientes de nuvem como o Azure.

### 🔌 **Introdução aos Conceitos de Serverless e Azure Functions**
- **O que é Serverless no Azure?**
  - Azure Functions permite executar código sem provisionar servidores, ideal para tarefas como validação de documentos e gerenciamento de usuários.

---

Este é o mapa mental completo, com tópicos sobre **Docker**, **Kubernetes**, **Serverless**, e **Azure**, abordando os principais conceitos e comandos. Você pode expandir ou personalizar conforme necessário!
