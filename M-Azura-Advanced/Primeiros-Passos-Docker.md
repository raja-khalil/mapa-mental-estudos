# 🐳 Primeiros Passos com o Docker

## ⬇️ Realizando o Download de Imagem
- **Acessando o Docker Hub**
    - Acesse o [Docker Hub](https://hub.docker.com/) 🌐
    - No Docker Hub, você pode buscar por imagens de contêineres para diferentes tipos de aplicações.

### 🖼️ Selecionando a Imagem
- Após acessar o Docker Hub, escolha a imagem desejada para o seu projeto. Por exemplo, você pode procurar pela imagem `hello-world` para testar o Docker.

## 💻 Comandos Básicos do Docker

1. **Baixando a Imagem**
    - Use o comando `docker pull` para baixar a imagem escolhida. Exemplo:
      ```bash
      docker pull hello-world
      ```
    - Isso fará o download da imagem `hello-world`, que é uma imagem simples para testar se o Docker está funcionando corretamente.

2. **Verificando as Imagens Locais**
    - Após o download, você pode listar todas as imagens baixadas com o comando:
      ```bash
      docker images
      ```
    - Isso exibirá uma lista das imagens disponíveis localmente no seu sistema.

3. **Executando a Imagem**
    - Para rodar uma aplicação dentro de um contêiner, use o comando `docker run`, seguido pelo nome da imagem. Exemplo:
      ```bash
      docker run hello-world
      ```
    - Este comando cria e executa um contêiner com a imagem `hello-world`. Se tudo estiver configurado corretamente, o Docker irá exibir uma mensagem de sucesso, confirmando que a instalação foi bem-sucedida.

## 🚀 Conclusão
- Com esses primeiros passos, você começou a trabalhar com Docker e pode agora explorar outras imagens, criar contêineres personalizados e integrar o Docker ao seu fluxo de desenvolvimento.
