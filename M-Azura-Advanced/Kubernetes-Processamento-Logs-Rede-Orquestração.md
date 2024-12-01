# 🐳 Mapa Mental: **Docker e Kubernetes - Processamento, Logs, Rede e Orquestração**

## 🚀 Docker - Processamento, Logs e Rede

### ⚙️ **Processamento, Logs e Rede com Docker**
- **Limitando a Memória e CPU**
    - Comando `stress` e suas variações
    - **Passo 1: Limitar a Memória e CPU de um Contêiner Docker**
        1. **Crie ou inicie o contêiner** com as opções de limite de recursos.
        2. Utilize os seguintes comandos:
            - `docker run -d --memory=512m --cpus=1.0 ubuntu`
            - `docker stats` para monitorar uso de CPU e memória.

### 📁 **Armazenamento de Dados com Docker**
- **Montando um Volume ("Mount")**
    - Montar um volume permite que os dados de um contêiner sejam armazenados persistentemente fora do ciclo de vida do contêiner.
    - **Passo a Passo: Montar um Volume com Docker**
        1. Crie um volume:
            - `docker volume create meu-volume`
        2. Monte o volume no contêiner:
            - `docker run -v meu-volume:/dados ubuntu`
        3. Verifique o volume montado:
            - `docker inspect meu-volume`

### 🐍 **Criando Imagens Personalizadas a partir de Imagens de Linguagens de Programação**
- **Exemplo de Comandos**
    - Buscar no Hub Docker uma imagem, por exemplo, Python:
        - `docker pull python`
    - Criar um diretório para trabalhar com a imagem:
        - `mkdir python`
        - `cd python`
    - Criar um Dockerfile básico para a imagem personalizada:
        - `FROM python:3.9`
        - `RUN pip install --upgrade pip`

### 🔼 **Realizando o Upload de Imagens para o Docker Hub**
- **Comandos**
    - **Login no Docker Hub**:
        - `docker login`
    - **Criar a imagem e nomear com o seu repositório no Hub**:
        - `docker build . -t nomedousuarop/nomeimagem`
    - **Push da imagem para o Docker Hub**:
        - `docker push nomedousuarop/nomeimagem`

---

## 🧩 Kubernetes - Orquestração de Contêineres

### 🛠️ **Introdução ao Kubernetes e Orquestração de Contêineres**
- **O que é Kubernetes (k8s)?**
    - Kubernetes é uma ferramenta open source de orquestração de contêineres.
    - Ele permite gerenciar múltiplos contêineres e serviços em grande escala.
    - Facilita o gerenciamento de microserviços e garante alta disponibilidade e redundância.
    - **Principais Funcionalidades**:
        - **Gerenciamento de Containers**: Automação do deployment, escala e operação de contêineres.
        - **Escalabilidade**: Kubernetes permite escalar contêineres automaticamente com base na demanda.
        - **Redundância**: Garante que os serviços não fiquem offline mesmo em caso de falha de contêiner.

### 🔄 **Orquestração de Contêineres**
- **Como o Kubernetes Gerencia os Contêineres?**
    - O Kubernetes usa "pods", que são grupos de contêineres.
    - Ele orquestra a execução, rede e comunicação entre esses pods.
    - Permite definir políticas para escalabilidade automática, recuperação em falhas, balanceamento de carga, entre outros.

### 📡 **Comandos Básicos do Kubernetes**
- **Verificar os pods em execução**:
    - `kubectl get pods`
- **Deploy de uma aplicação no Kubernetes**:
    - `kubectl run meuapp --image=meuapp:latest`
- **Escalar o número de réplicas**:
    - `kubectl scale --replicas=3 deployment/meuapp`

---

## 🧑‍💻 **Trabalhando com Docker Compose**
- **Introdução e Instalação do Docker Compose**
    - **O que é o Docker Compose?**
        - Docker Compose é uma ferramenta que permite definir e executar aplicativos multi-contêiner.
        - Com o Compose, você define a configuração do aplicativo em um arquivo YAML e, com um único comando, pode iniciar e parar todos os contêineres necessários.

    - **Instalação do Docker Compose**:
        - Verifique se o Docker Compose já está instalado:
            - `docker-compose --version`
        - Se necessário, instale o Docker Compose a partir do site oficial: [Instalar Docker Compose](https://docs.docker.com/compose/install/).

    - **Criar um Arquivo `docker-compose.yml`**:
        - Exemplo:
            ```yaml
            version: '3'
            services:
              web:
                image: nginx
                ports:
                  - "8080:80"
            ```

    - **Subir os contêineres com o Compose**:
        - `docker-compose up`

---

Com essas informações, você tem uma visão geral de como trabalhar com Docker, Kubernetes e Docker Compose, incluindo os principais comandos e conceitos para gerenciar contêineres e orquestrar sistemas complexos de contêineres.
