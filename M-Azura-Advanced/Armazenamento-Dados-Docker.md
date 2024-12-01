# 📦 Armazenamento de Dados com Docker

## 🔒 Montando um "Mount" no Local de Armazenamento

**Passo a Passo: Montar um Volume com Docker ("Mount")**

Montar um volume no Docker permite que os dados de um container sejam armazenados de forma persistente, mesmo após o container ser removido. Essa técnica é útil quando se deseja manter dados importantes entre as execuções dos containers.

### 1️⃣ Criando o Volume
- O Docker permite criar volumes para armazenar dados de forma isolada e reutilizável.
    - **Comando**: `docker volume create nome_do_volume`
    - Exemplo: `docker volume create dados_app`

### 2️⃣ Montando o Volume no Container
- Para associar um volume a um container, utilizamos o comando `docker run` com a opção `-v` (volume).
    - **Comando**: `docker run -v nome_do_volume:/caminho/no/container nome_da_imagem`
    - Exemplo: `docker run -v dados_app:/app/data my_image`

### 3️⃣ Verificando o Volume
- Você pode verificar os volumes criados e seu estado com o comando:
    - **Comando**: `docker volume ls`
    - Isso exibirá uma lista de todos os volumes armazenados no Docker.

### 4️⃣ Removendo o Volume
- Caso queira remover um volume, utilize o comando:
    - **Comando**: `docker volume rm nome_do_volume`
    - Exemplo: `docker volume rm dados_app`

### Benefícios de Montar Volumes:
- 📂 **Persistência**: Dados permanecem mesmo se o container for removido.
- 🔄 **Reusabilidade**: Volumes podem ser compartilhados entre diferentes containers.
- 🛠️ **Facilidade de Backup**: Volumes podem ser facilmente copiados ou movidos.

Agora, seus dados estão seguros e organizados, independentemente do que aconteça com seus containers! 🚀
