# Criando Container com Docker

## Overview Docker
- **O que é Docker?**
    - Docker é uma plataforma de containers que permite empacotar uma aplicação junto com suas dependências, criando um ambiente isolado e portátil.
    - Um container simula o que a aplicação precisa para rodar, agindo como uma amostragem do sistema operacional.
    - A aplicação roda dentro do container, garantindo que ela funcione da mesma maneira em diferentes sistemas.
    - Facilita a portabilidade de aplicativos entre ambientes de desenvolvimento, teste e produção.

- **Benefícios do Docker**
    - **Portabilidade**: Os containers podem ser executados em qualquer lugar onde o Docker esteja instalado, independentemente do sistema operacional subjacente.
    - **Eficiência**: Reduz o uso de recursos ao compartilhar o sistema operacional host, sem a necessidade de máquinas virtuais completas.
    - **Isolamento**: Cada container é isolado, permitindo que várias versões de uma aplicação sejam executadas simultaneamente em um único sistema sem conflitos.
    - **Escalabilidade**: Facilita a criação de múltiplas instâncias de um aplicativo e a escalabilidade automática.

## Criando Containers com Docker

### Passo 1: Instalar o Docker
- Baixe e instale o Docker em seu sistema operacional:
  - [Docker para Windows](https://www.docker.com/products/docker-desktop)
  - [Docker para Mac](https://www.docker.com/products/docker-desktop)
  - [Docker para Linux](https://docs.docker.com/get-docker/)

### Passo 2: Criar um Dockerfile
- Um **Dockerfile** é um arquivo de configuração que contém um conjunto de instruções para criar uma imagem Docker.
  
  Exemplo de um Dockerfile simples:
  
  ```Dockerfile
  # Use uma imagem base oficial do Node.js
  FROM node:14
  
  # Defina o diretório de trabalho
  WORKDIR /usr/src/app
  
  # Copie o arquivo package.json para o contêiner
  COPY package*.json ./
  
  # Instale as dependências
  RUN npm install
  
  # Copie o código da aplicação para o contêiner
  COPY . .
  
  # Exponha a porta que a aplicação vai usar
  EXPOSE 8080
  
  # Comando para rodar a aplicação
  CMD ["node", "app.js"]
