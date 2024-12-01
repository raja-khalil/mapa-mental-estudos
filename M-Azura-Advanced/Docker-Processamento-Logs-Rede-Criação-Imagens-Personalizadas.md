# 🐳 Mapa Mental: **Docker - Processamento, Logs, Rede e Criação de Imagens Personalizadas**

## ⚙️ **Processamento, Logs e Rede com Docker**

### 🧠 **Limitando a Memória e CPU**
- **Objetivo:** Limitar o uso de recursos (memória e CPU) de contêineres para otimizar o desempenho.
- **Comando para Stress:**
    - `docker run --name stress-container --memory 256m --cpus="1.0" -d ubuntu:latest`
    - Exemplo de comando de stress: `stress --cpu 1 --timeout 30s`

#### **Passo 1: Limitar a Memória e CPU de um Contêiner Docker**
1. **Crie ou inicie um contêiner**: `docker run -dti --name meu-container ubuntu`
2. **Use o comando para limitar recursos**: `docker run --memory 512m --cpus="1.0" ubuntu`
3. **Verifique o uso de recursos**: `docker stats`

---

## 📂 **Definição e Criação de Dockerfile**

### 📝 **Primeiro Dockerfile**
- **Objetivo:** Criar um Dockerfile para gerar uma imagem personalizada.
- **Comandos**:
    - `docker run -dti --name ubuntu-python ubuntu`
    - `docker exec -ti ubuntu-python bash`
    - Dentro do contêiner, use: `apt update && apt install python3`
    
---

## 🐍 **Criando Imagens Personalizadas a partir de Imagens de Linguagens de Programação**

### 🛠️ **Personalizando Imagens com Python**
- **Objetivo:** Criar uma imagem personalizada com a linguagem Python.
- **Comandos**:
    1. **Buscar uma imagem no Docker Hub**: 
        - `docker pull python`
    2. **Verificar as imagens disponíveis**: 
        - `docker images`
    3. **Criar um diretório para armazenar arquivos**:
        - `mkdir python`
    4. **Entrar no diretório**:
        - `cd python`
    5. **Criar um Dockerfile com as configurações necessárias**.
    6. **Construir a imagem**:
        - `docker build -t python-app .`
    7. **Executar a imagem personalizada**:
        - `docker run -it python-app`

---

## 📤 **Realizando o Upload de Imagens para o HUB do Docker**

### 🔼 **Upload para o Docker Hub**
- **Objetivo:** Fazer o upload de sua imagem personalizada para o Docker Hub.
- **Passos**:
    1. **Login no Docker Hub**:
        - `docker login`
    2. **Criar um repositório no Docker Hub**:
        - Visite [Docker Hub](https://hub.docker.com/), crie um repositório com o seu nome de usuário.
    3. **Construir a imagem com seu nome de usuário**:
        - `docker build . -t nomedousuario/nomeimagem`
    4. **Fazer o push da imagem para o Hub**:
        - `docker push nomedousuario/nomeimagem`

---

## 📄 **Comandos Utilizados**

- `docker pull <imagem>`: Baixa a imagem do Docker Hub.
- `docker build . -t <nome_da_imagem>`: Cria uma imagem personalizada.
- `docker run <opções> <imagem>`: Executa um contêiner baseado em uma imagem.
- `docker exec -ti <nome_do_contêiner> bash`: Acessa um contêiner em execução.
- `docker push <nome_da_imagem>`: Envia sua imagem personalizada para o Docker Hub.
- `docker login`: Efetua login no Docker Hub.
- `docker stats`: Exibe o uso de recursos de um contêiner.

---

## 🧳 **Resumo Visual**

1. **Processamento e Rede**: Gerencie os recursos (memória/CPU) dos contêineres.
2. **Dockerfile**: Escreva o Dockerfile para criar imagens personalizadas.
3. **Python**: Use imagens base para criar aplicações com Python.
4. **Upload para Hub**: Suba suas imagens personalizadas para o Docker Hub para compartilhar e reutilizar.

---

**Dicas**:
- **Documentação**: Consulte sempre a [documentação oficial do Docker](https://docs.docker.com/).
- **Prática**: Realize os passos e explore os comandos para entender melhor os fluxos.

---
