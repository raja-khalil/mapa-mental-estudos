# 🐳 Mapa Mental: **Docker, Kubernetes e Serverless - Processamento, Logs, Rede e Orquestração**

## 🚀 Docker - Processamento, Logs e Rede

### 📦 Armazenamento de Dados com Docker
- **Montando um "Mount" no Docker**  
    Montar um volume no Docker permite que os dados de um container sejam armazenados permanentemente, mesmo após o container ser removido.

    #### Passo a Passo: Montar um Volume com Docker
    1. Crie um volume:
        ```bash
        docker volume create meu_volume
        ```
    2. Execute o container com o volume montado:
        ```bash
        docker run -v meu_volume:/caminho/no/container -d nome_da_imagem
        ```

### ⚙️ Processamento, Logs e Rede com Docker
- **Limitando Memória e CPU**  
    Para limitar os recursos de um container, podemos usar o comando `docker run` com opções de memória e CPU.

    #### Comandos:
    ```bash
    docker run -d --memory="500m" --cpus="1.0" nome_da_imagem
    ```

    **Comando stress** para testar:
    ```bash
    stress --cpu 1 --timeout 60s
    ```

### 🧑‍💻 Definição e Criação de Dockerfile
- **Criando seu primeiro Dockerfile**  
    Para criar uma imagem Docker personalizada, você pode escrever um `Dockerfile` simples.

    #### Exemplo de Dockerfile:
    ```dockerfile
    FROM ubuntu
    RUN apt update && apt install -y python3
    CMD ["python3"]
    ```

    Para construir e rodar a imagem:
    ```bash
    docker build -t minha_imagem .
    docker run -it minha_imagem
    ```

### 📥 Realizando o Upload de Imagens para o Docker Hub
- **Subindo uma Imagem para o Hub do Docker**
    Para compartilhar sua imagem com outros, você pode fazer o upload para o Docker Hub.

    #### Comandos:
    ```bash
    docker login
    docker build . -t nomedousuario/nome_da_imagem
    docker push nomedousuario/nome_da_imagem
    ```

### 📊 Trabalhando com Docker Compose
- **Introdução e Instalação do Docker Compose**
    - O Docker Compose é uma ferramenta para definir e rodar aplicações multi-contêineres. Ele permite que você use um arquivo YAML para definir os serviços, redes e volumes.

    #### Comando de instalação:
    ```bash
    sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    sudo chmod +x /usr/local/bin/docker-compose
    ```

---

## 🐙 Kubernetes - Orquestração de Contêineres

### 🧩 Overview Kubernetes
- **O que é Kubernetes (k8s)?**  
    Kubernetes é uma plataforma de orquestração de containers open source que permite automatizar a implantação, o dimensionamento e a operação de aplicativos em contêineres.

### 🌍 Ambiente de Desenvolvimento Kubernetes
- **Criando um Cluster Kubernetes com o Minikube**
    O Minikube permite criar um cluster Kubernetes local para estudo e desenvolvimento.

    #### Comando para iniciar o Minikube:
    ```bash
    minikube start
    ```

### ☁️ Cluster Kubernetes em Nuvem
- **Cluster Kubernetes em Produção**
    Um cluster Kubernetes consiste em nós de trabalho que executam as aplicações em contêineres. O Kubernetes gerencia esses nós e aplica a orquestração e automação de deploys.

    #### Comando para verificar o cluster:
    ```bash
    kubectl get nodes
    ```

### 📝 Conceitos Básicos sobre Pods em Kubernetes
- **O que são Pods?**
    Pods são a menor unidade de execução em Kubernetes, consistindo em um ou mais contêineres.

    #### Exemplo de arquivo YAML para criar um pod:
    ```yaml
    apiVersion: v1
    kind: Pod
    metadata:
      name: exemplo-pod
    spec:
      containers:
      - name: exemplo-container
        image: nginx
    ```

### 🛠️ Serviço de Acesso para Kubernetes Pods
- **Criando um NodePort para acesso externo**
    O NodePort expõe o serviço Kubernetes em uma porta específica de cada nó do cluster, permitindo o acesso externo.

    #### Exemplo de configuração YAML:
    ```yaml
    apiVersion: v1
    kind: Service
    metadata:
      name: exemplo-nodeport
    spec:
      selector:
        app: exemplo-app
      ports:
        - protocol: TCP
          port: 80
          nodePort: 30007
      type: NodePort
    ```

### 💾 Persistência de Dados em Clusters Kubernetes
- **Introdução ao PV (Persistent Volume) e PVC (Persistent Volume Claim)**
    Para garantir a persistência de dados em Kubernetes, usamos os objetos Persistent Volume (PV) e Persistent Volume Claim (PVC).

    #### Exemplo de PV e PVC:
    ```yaml
    apiVersion: v1
    kind: PersistentVolume
    metadata:
      name: exemplo-pv
    spec:
      capacity:
        storage: 1Gi
      accessModes:
        - ReadWriteOnce
      hostPath:
        path: /data
    ---
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      name: exemplo-pvc
    spec:
      accessModes:
        - ReadWriteOnce
      resources:
        requests:
          storage: 1Gi
    ```

---

## 🌐 Serverless

### 🔥 Overview Serverless
- **O que é Serverless?**
    No modelo serverless, as aplicações são executadas sem a necessidade de gerenciar servidores. Você escreve apenas o código da aplicação, e a nuvem se encarrega da infraestrutura.

    #### Exemplos de Serverless:
    - **Validação de Documentos**: Função que valida documentos automaticamente ao serem carregados.
    - **Gerenciamento de Usuários**: Função que lida com registro, login e autenticação de usuários.

    **Vantagens:**
    - Escalabilidade automática.
    - Pagamento apenas pelo tempo de execução.

---

Essa estrutura abrange os principais tópicos de **Docker**, **Kubernetes** e **Serverless**, com exemplos práticos de comandos e configurações. É uma visão geral bem completa para quem está começando ou deseja consolidar seus conhecimentos nessas tecnologias.
