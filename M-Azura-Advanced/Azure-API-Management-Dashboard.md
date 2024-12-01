# 🐳 Mapa Mental: **Docker, Kubernetes, Serverless e Azure - Processamento, Logs, Rede e Orquestração**

## 🚀 Docker e Kubernetes

### 🐋 **Processamento, Logs, Rede e Criação de Imagens Personalizadas**

- **Docker Compose**
    - **Introdução e Instalação do Docker Compose**
        - Docker Compose é uma ferramenta desenvolvida para ajudar a definir e compartilhar aplicativos com vários contêineres.
        - Com Compose, você define os contêineres de forma simples através de arquivos YAML.
        - Comandos importantes: 
            - `docker-compose up`
            - `docker-compose down`

- **Trabalhando com Docker Compose**
    - Criação e gerenciamento de múltiplos contêineres de forma simples e automatizada com Compose.
    - Permite definir uma configuração única para diferentes serviços.
    - Arquivo `docker-compose.yml`: Define a configuração para os serviços, redes e volumes.

- **Criando Imagens Personalizadas a partir de Imagens de Linguagens de Programação**
    - **Comandos**:
        - Buscar no Hub Docker: `docker pull python`
        - `docker images` para ver imagens locais.
        - Criar diretório para armazenar a imagem: `mkdir python`
        - Navegar para o diretório: `cd python`
        - Construir e rodar o container: `docker run -dti name ubuntu-python ubuntu`

### 🐋 **Kubernetes**

- **Overview Kubernetes (K8s)**
    - Kubernetes (K8s) é uma ferramenta de orquestração de contêineres open-source.
    - Ele ajuda a gerenciar, escalar e automatizar a implantação de aplicações em contêineres.
    - Ele permite que você crie e gerencie microserviços em contêineres Docker.
    - **Componentes**:
        - Pods: Unidade mínima de execução.
        - Nodes: Máquinas que executam os Pods.

- **Introdução ao Kubernetes e Orquestração de Contêineres**
    - Kubernetes facilita a gestão de clusters de contêineres e fornece funcionalidades como escalabilidade, automação e manutenção de disponibilidade.
    - Permite definir regras para escalabilidade de aplicações.

- **Ambiente de Desenvolvimento Kubernetes**
    - **Minikube**: Executa o Kubernetes localmente para estudos e testes.
        - `minikube start`: Inicia o cluster local.
        - `kubectl`: Comando para interagir com o Kubernetes.

- **Cluster Kubernetes em Nuvem**
    - Implantações em produção, com gerenciamento em clusters de servidores de processamento.
    - **Componentes do Kubernetes**:
        - Cluster consiste em um conjunto de nós que executam as aplicações.
        - Cada nó pode ter múltiplos contêineres (Pods).

- **Conceitos Básicos sobre Pods em Kubernetes**
    - **Arquivo YAML**:
        - O YAML (YAML Ain't Markup Language) é amplamente utilizado para escrever arquivos de configuração no Kubernetes.
        - Exemplo de configuração para Pods em YAML:
          ```yaml
          apiVersion: v1
          kind: Pod
          metadata:
            name: mypod
          spec:
            containers:
            - name: mycontainer
              image: myimage
          ```

- **Serviço de Acesso para Kubernetes Pods**
    - **Criando um NodePort**: Expondo um serviço Kubernetes para acessar através da rede.
    - Arquivos usados:
        - `dockerfile`
        - `nodePort.yml`
        - `pod.yml`

- **Persistência de Dados em Clusters Kubernetes**
    - **Introdução ao PV (Persistent Volume) e PVC (Persistent Volume Claim)**:
        - Kubernetes oferece armazenamento persistente para dados, separado do ciclo de vida de Pods.
        - Usado para manter dados após reinicialização de Pods.

### ☁️ **Serverless**

- **Overview Serverless**
    - **O que é Serverless?**
        - Serverless é um modelo onde o código é executado sem gerenciar explicitamente servidores.
        - A infraestrutura é gerenciada pela nuvem, e você apenas define funções.
        - Exemplo de funções serverless:
            - Validação de documentos.
            - Gerenciamento de usuários.
        - Escalabilidade automática sem intervenção manual.

### ☁️ **Azure**

- **Azure API Management Dashboard**
    - **Introdução ao Azure API Management**:
        - Plataforma para gerenciar, expor e proteger APIs.
        - Oferece uma maneira de garantir que as APIs sejam escaláveis e seguras.
    - **Descobrindo o Serviço de Gerenciamento de API**:
        - O Azure API Management fornece um conjunto de ferramentas para definir, monitorar e proteger APIs.
        - **Papel do Gerenciamento de API**:
            - Fornece governança de acesso.
            - Permite a monitoração de uso e desempenho.
            - Ajuda a proteger APIs contra uso indevido.
