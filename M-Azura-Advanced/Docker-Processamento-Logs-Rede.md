# 🐋 Mapa Mental: **Docker - Processamento, Logs e Rede**

## ⚙️ Processamento, Logs e Rede com Docker

### 🧠 Limitando a Memória e CPU
- **Objetivo**: Controlar recursos de CPU e memória para contêineres.
- **Comando stress**:
    - O comando `stress` é utilizado para gerar carga no sistema e testar a capacidade de processamento.
    - **Exemplo de comando**:
      ```bash
      stress --cpu 1 --timeout 30s
      ```
      - **Parâmetro `--cpu`**: Especifica o número de CPUs para utilizar.
      - **Parâmetro `--timeout`**: Limita o tempo de execução do comando.

### 📊 Passo 1: Limitar a Memória e CPU de um Contêiner Docker
1. **Crie ou inicie o contêiner com limites de CPU e memória**:
    - **Comando**:
      ```bash
      docker run -d --name meu_container --memory=512m --cpus="1.0" alpine sleep 3600
      ```
    - **Explicação**:
      - `--memory=512m`: Limita a memória do contêiner para 512 MB.
      - `--cpus="1.0"`: Limita o contêiner a usar 1 CPU.
      - `alpine`: Imagem do contêiner (neste caso, a imagem Alpine Linux).
      - `sleep 3600`: O contêiner irá dormir por 1 hora para simulação.

### 📋 Comandos Comuns para Gerenciar Recursos:
- **Verificar o uso de CPU e memória de um contêiner**:
  ```bash
  docker stats meu_container
