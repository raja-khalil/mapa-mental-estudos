# 🗂️ Mapa Mental: Desenvolver para o Cache do Azure para Redis e CDNs

## 🧠 Introdução ao Caching
- **Caching:** Técnica para melhorar o desempenho e a escalabilidade.
- **Como funciona:** Copia dados acessados com frequência para um local próximo ao aplicativo.

## ⚙️ Cache do Azure para Redis
### 🚀 Benefícios
- Melhora desempenho e escalabilidade.
- Processa grandes volumes de solicitações.
- Baixa latência e alta taxa de transferência.

### 🔄 Principais Cenários
- Cache de dados
- Cache de conteúdo
- Repositório de sessão
- Enfileiramento de mensagens e trabalhos
- Transações distribuídas

### 🛠️ Camadas de Serviço
| Camada            | Descrição                                                                                                                |
|-------------------|--------------------------------------------------------------------------------------------------------------------------|
| Basic             | Camada básica para uso em produção.                                                                                       |
| Standard          | Alta disponibilidade com replicação.                                                                             |
| Premium           | Inclui recursos adicionais como persistência e clustering.                                                               |
| Enterprise        | Projetado para cargas de trabalho empresariais e de grande escala.                                                       |
| Enterprise Flash  | Oferece maior desempenho com armazenamento Flash.                                                                   |

## ⚙️ Configurar o Cache do Azure para Redis
### 📋 Parâmetros para Configuração
- Nome
- Localidade
- Tipo de preço
- Suporte para Rede Virtual
- Suporte a clustering

### 🔌 Acessar a Instância do Redis
- **Ferramenta de linha de comando**:
  | Comando            | Descrição                                                                                |
  |--------------------|------------------------------------------------------------------------------------------|
  | ping               | Execute ping no servidor. Retorna "PONG".                                                 |
  | set [key] [value]  | Define uma chave/valor no cache. Retorna "OK".                           |
  | incr [key]         | Incrementa o valor associado à chave em '1'.          |
  | type [key]         | Retorna o tipo associado ao valor para a chave fornecida.                                 |
  | flushdb            | Exclui todos os valores e chaves do banco de dados.                                       |
  | get [key]          | Obtém um valor do cache.                                                                  |
  | exists [key]       | Retorna '1' se a chave existir no cache, e '0' caso contrário.                            |
  | incrby [key] [amount] | Incrementa o valor associado à chave pelo valor especificado.  |
  | del [key]          | Exclui o valor associado à chave.                                                         |

### ⏳ Adicionando Tempo de Expiração a Valores
- Aplicar TTL a uma chave.
- A chave é excluída automaticamente ao expirar.
- Expirações em segundos ou milissegundos.

**Exemplo de Comando Redis**
```plaintext
> set counter 100
OK
> expire counter 5
(integer) 1
> get counter
100
... wait ...
> get counter
(nil)
