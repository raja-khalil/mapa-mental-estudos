# 🌐 Mapa Mental: **Docker e Armazenamento de Dados**

## 🐳 Docker
- **O que é Docker?** 🤔
    - Plataforma de containers 🛠️
    - Simula sistemas operacionais em ambientes isolados 💻
    - Facilita a portabilidade das aplicações 🚀

### 🛠️ Criando Container com Docker
- **Overview Docker** 🌍
    - Container que simula o que a aplicação precisa 🖥️
    - A aplicação roda dentro do container 🔒
    - Torna a aplicação portátil 🌎
    - Facilita a navegação entre diferentes sistemas operacionais 🖧

### 🚀 Primeiros Passos com Docker
- **Realizando o Download de Imagem** ⬇️
    - Acesse o [Docker Hub](https://hub.docker.com/) 🌐
    - **Selecionar Imagem** 🖼️
        - Exemplo: `docker pull hello-world` 🖥️
    - **Comandos** 📝
        - `docker pull hello-world` - Baixa a imagem do Docker Hub 🔽
        - `docker images` - Lista as imagens disponíveis no seu sistema 📜
        - `docker run hello-world` - Roda a imagem baixada 🚀

---

## 📦 Armazenamento de Dados com Docker
- **Montando um "Mount" no Docker** 📂
    - O "mount" é um processo de vinculação de dados entre o container e o sistema de arquivos do host 🔗
    - Isso permite que dados gerados dentro do container sejam persistidos fora dele 🗂️

### 🔑 Passo a Passo: Montando um Volume com Docker
1. **Criar Volume** 🔨
    - Comando: `docker volume create nome_do_volume` 💡
    - Exemplo: `docker volume create meus_dados` 📦
2. **Montar Volume no Container** 🧰
    - Comando: `docker run -v nome_do_volume:/diretorio_no_container nome_da_imagem` 💻
    - Exemplo: `docker run -v meus_dados:/app/data hello-world` 🌍
3. **Verificar o Volume** 🔍
    - Comando: `docker volume ls` 🔠
    - Mostra todos os volumes criados no sistema 📑

---

## 🔄 Exemplo de Tipo de Mount na Prática
- **Montando um diretório local no Container** 📂➡️🚢
    - Este tipo de mount usa um diretório no sistema local como "mount" para persistir dados.
    - **Comando**:
        ```bash
        docker run -v /caminho/local:/diretorio_no_container nome_da_imagem
        ```
    - Exemplo:
        ```bash
        docker run -v /home/user/meus_dados:/app/data ubuntu
        ```
    - Esse comando mapeia o diretório local `/home/user/meus_dados` para o diretório `/app/data` dentro do container.

---

## 📝 Gerenciamento de Contêineres no Docker
- **Comandos Básicos de Gerenciamento** ⚙️
    - **Listar Contêineres Ativos** 🗂️
        - Comando: `docker ps` 📜
    - **Listar Todos os Contêineres (Ativos e Inativos)** 🕓
        - Comando: `docker ps -a` 🔍
    - **Parar um Contêiner** 🛑
        - Comando: `docker stop nome_ou_id_do_container` ⏸️
    - **Iniciar um Contêiner** ▶️
        - Comando: `docker start nome_ou_id_do_container` 🚦
    - **Remover um Contêiner** 🗑️
        - Comando: `docker rm nome_ou_id_do_container` 🔨
    - **Remover uma Imagem** ❌
        - Comando: `docker rmi nome_da_imagem` 🧹
