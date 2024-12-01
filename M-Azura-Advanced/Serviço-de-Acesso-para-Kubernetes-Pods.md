# 🐳 Mapa Mental: **Docker e Kubernetes - Processamento, Logs, Rede e Orquestração**

## 🚀 Docker - Processamento, Logs e Rede

### ⚙️ **Processamento, Logs e Rede com Docker**
- **Limitando a Memória e CPU**
    - Comando `stress` e suas variáveis
    - **Passo 1: Limitar a Memória e CPU de um Contêiner Docker**
        1. Crie ou configure o contêiner com a opção de limite de recursos:
            - Comando: `docker run -dti --memory="512m" --cpus="1" nome_do_container`

---

## 🐍 **Docker - Criando Imagens Personalizadas a partir de Linguagens de Programação**
- **Buscar Imagem no Docker Hub**
    - No caso, imagem de Python
    - Comandos:
        - `docker pull python`
        - `docker images`
        - `mkdir python`
        - `cd python`
        - Criar Dockerfile: `FROM python:3.9-slim`
        - Configurar o arquivo de aplicação no contêiner

---

## ⬆️ **Realizando o Upload de Imagens para o Hub do Docker**
- **Comandos para Upload**
    - Realizando login no Docker Hub:
        - `docker login`
    - Gerar imagem com seu nome de usuário:
        - `docker build . -t nomedousuario/nome_da_imagem`
    - Enviar para o Hub:
        - `docker push nomedousuario/nome_da_imagem`

---

## 🐙 **Trabalhando com Docker Compose**
- **Introdução e Instalação do Docker Compose**
    - **Definição**: O Docker Compose é uma ferramenta que ajuda a definir e compartilhar aplicativos com múltiplos contêineres.
    - **Comandos principais**:
        - `docker-compose up` – Para iniciar todos os serviços definidos no arquivo `docker-compose.yml`
        - `docker-compose down` – Para parar e remover os contêineres

---

## ⚙️ **Kubernetes - Visão Geral e Orquestração de Contêineres**
- **O que é Kubernetes (k8s)?**
    - Kubernetes é uma ferramenta open-source de orquestração de contêineres. Ele gerencia e automatiza a implantação, escalabilidade e operações de contêineres.
    - **Funcionalidade**:
        - Gerenciamento de microserviços em contêineres Docker
        - Redundância e escalabilidade automática

---

## 🚀 **Ambiente de Desenvolvimento Kubernetes**
- **Criando um Cluster Kubernetes com Minikube**
    - **Minikube**: Utilitário para executar o Kubernetes localmente
    - Comandos:
        - `minikube start` – Inicia o Minikube
        - `kubectl get nodes` – Verifica o estado dos nós no cluster

---

## ☁️ **Cluster Kubernetes em Nuvem**
- **Cluster Kubernetes em Produção**
    - **Componentes do Kubernetes**:
        - Um cluster Kubernetes consiste em servidores de processamento chamados "nós".
        - **Nó mestre**: Gerencia o cluster e as operações.
        - **Nó de trabalho**: Executa os contêineres.

---

## 📦 **Conceitos Básicos sobre Pods em Kubernetes**
- **O que são Pods?**
    - Um Pod é a unidade básica de execução no Kubernetes. Ele pode conter um ou mais contêineres.
- **Arquivo YAML**
    - O YAML é usado para configurar Pods e outros recursos no Kubernetes.
    - **Estrutura YAML**:
        - Exemplo de definição de um Pod:
            ```yaml
            apiVersion: v1
            kind: Pod
            metadata:
              name: exemplo-pod
            spec:
              containers:
              - name: nginx
                image: nginx
            ```

---

## 🔐 **Serviço de Acesso para Kubernetes Pods**
- **Criando um NodePort**
    - O NodePort expõe o serviço Kubernetes para fora do cluster.
    - Arquivos necessários:
        - **nodePort.yml**: Define o serviço.
        - **pod.yml**: Define o Pod.
    - Comandos:
        - Para criar um serviço NodePort:
            ```yaml
            apiVersion: v1
            kind: Service
            metadata:
              name: meu-servico
            spec:
              type: NodePort
              ports:
                - port: 80
                  targetPort: 8080
                  nodePort: 30001
              selector:
                app: meu-app
            ```

---

## 📈 **Monitoramento e Logs no Kubernetes**
- **Monitoramento com kubectl**
    - Para verificar logs de Pods:
        - `kubectl logs nome_do_pod`
    - Para monitorar o estado do cluster:
        - `kubectl get pods`
        - `kubectl describe pod nome_do_pod`

---

## 🛠️ **Gerenciamento de Contêineres no Kubernetes**
- **Escalabilidade**
    - Kubernetes permite aumentar ou diminuir a quantidade de Pods em execução conforme a demanda.

    **Comandos de escalabilidade**:
    - Escalar a aplicação:
        - `kubectl scale deployment nome_da_aplicacao --replicas=3`

---

Este mapa mental oferece uma visão abrangente sobre **Docker e Kubernetes**, abordando desde a criação e gerenciamento de contêineres, até o uso de Kubernetes para orquestração e escalabilidade em produção.
