# 🐳 Mapa Mental: **Docker - Processamento, Logs, Rede e Criação de Imagens Personalizadas**

## ⚙️ **Processamento, Logs e Rede com Docker**
- **Limitando a Memória e CPU**
    - Comando `stress` e suas variações
    - **Passo 1: Limitar a Memória e CPU de um Contêiner Docker**
        1. **Crie ou inicie um contêiner** com limites de recursos
        2. Exemplo de comando:
            ```bash
            docker run -d --name mycontainer --memory="500m" --cpus="1.0" ubuntu
            ```
    - **Passo 2: Verificar os Recursos do Contêiner**
        - Comando para verificar os limites de CPU e memória:
            ```bash
            docker stats mycontainer
            ```

---

## 🐍 **Criando Imagens Personalizadas a partir de Imagens de Linguagens de Programação**
- **Comandos para Criar Imagens Personalizadas**
    - Buscar no Docker Hub por uma imagem base
        - Exemplo: Imagem Python
        - Comando para buscar a imagem:
            ```bash
            docker pull python
            ```
    - **Passos para Criar uma Imagem Personalizada**
        1. Criar um diretório para armazenar a imagem:
            ```bash
            mkdir python
            cd python
            ```
        2. Criar o `Dockerfile` com a configuração desejada
        3. Construir a imagem com o comando:
            ```bash
            docker build -t my-python-app .
            ```
        4. Verificar a imagem criada:
            ```bash
            docker images
            ```

---

## 🔝 **Realizando o Upload de Imagens para o Docker Hub**
- **Comandos para Fazer o Upload**
    - **Passo 1: Login no Docker Hub**
        - Comando para login:
            ```bash
            docker login
            ```
    - **Passo 2: Criar um Repositório no Docker Hub**
        - Acesse o [Docker Hub](https://hub.docker.com) e crie um repositório com seu nome de usuário.
    - **Passo 3: Gerar a Imagem com seu Nome de Usuário**
        - Comando para construir a imagem:
            ```bash
            docker build . -t nomedousuario/nome-da-imagem
            ```
    - **Passo 4: Enviar a Imagem para o Docker Hub**
        - Comando para enviar a imagem:
            ```bash
            docker push nomedousuario/nome-da-imagem
            ```

---

## 🛠️ **Trabalhando com Docker Compose**
- **Introdução e Instalação do Docker Compose**
    - **O que é Docker Compose?**
        - Docker Compose é uma ferramenta que facilita a definição e o gerenciamento de aplicativos com múltiplos contêineres. Com o Compose, você pode usar um arquivo YAML para definir todos os serviços que um aplicativo necessita e depois criar e gerenciar esses serviços com um único comando.
    - **Passo 1: Instalar o Docker Compose**
        - Para instalar o Docker Compose, use o seguinte comando:
            ```bash
            sudo apt-get install docker-compose
            ```
    - **Passo 2: Criar um Arquivo `docker-compose.yml`**
        - Defina os serviços e contêineres no arquivo `docker-compose.yml`. Exemplo básico:
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
    - **Passo 3: Subir os Contêineres com Docker Compose**
        - Execute o comando para iniciar os serviços:
            ```bash
            docker-compose up
            ```

---

## 🐳 **Outros Tópicos Importantes**
- **Criando e Definindo Dockerfile**
    - **Primeiro Dockerfile**
        - Exemplo para criar uma imagem personalizada:
            ```bash
            docker run -dti --name ubuntu-python ubuntu
            docker exec -ti ubuntu-python bash
            apt update
            apt install python3
            ```
- **Trabalhando com Containers e Volumes**
    - Montar volumes no Docker para persistência de dados
    - Comando para montar um volume:
        ```bash
        docker run -v /meu/volume:/container/volume mycontainer
        ```
