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

# 🛠️ Acessar Cache Redis de um Cliente
Necessário: Nome do host, porta e chave de acesso.

- **Nome do Host:** Endereço público do cache (ex.: sportsresults.redis.cache.windows.net).
- **Chave de Acesso:** Senha do cache (primária e secundária).

# 💻 Interagir com o Cache do Azure para Redis usando .NET
## 🚀 StackExchange.Redis
### Criar uma Conexão
```csharp
using StackExchange.Redis;

var connectionString = "[nome-do-cache].redis.cache.windows.net:6380,password=[senha-aqui],ssl=True,abortConnect=False";
var redisConnection = ConnectionMultiplexer.Connect(connectionString);

🛠️ Acessar Cache Redis de um Cliente
Necessário: Nome do host, porta e chave de acesso.

Nome do Host: Endereço público do cache (ex.: sportsresults.redis.cache.windows.net).

Chave de Acesso: Senha do cache (primária e secundária).

💻 Interagir com o Cache do Azure para Redis usando .NET
🚀 StackExchange.Redis
Criar uma Conexão
using StackExchange.Redis;

var connectionString = "[nome-do-cache].redis.cache.windows.net:6380,password=[senha-aqui],ssl=True,abortConnect=False";
var redisConnection = ConnectionMultiplexer.Connect(connectionString);

🔧 Principais Tarefas com ConnectionMultiplexer
Acessar um banco de dados Redis.

Publicações/assinaturas do Redis.

Manutenção ou monitoramento.

📜 Exemplo de Código para Acessar Banco de Dados Redis
IDatabase db = redisConnection.GetDatabase();
bool wasSet = db.StringSet("favorite:flavor", "i-love-rocky-road");
string value = db.StringGet("favorite:flavor");
Console.WriteLine(value); // exibe: "i-love-rocky-road"
🔩 Outras Operações Comuns

Método	Descrição
CreateBatch	Cria um grupo de operações enviado como unidade única.
CreateTransaction	Cria um grupo de operações processada como unidade única.
KeyDelete	Exclui a chave/valor.
KeyExists	Verifica se a chave existe no cache.
KeyExpire	Define expiração de TTL (vida útil) em uma chave.
KeyRename	Renomeia uma chave.
KeyTimeToLive	Retorna a TTL de uma chave.
KeyType	Retorna o tipo do valor armazenado na chave.
🌐 Desenvolver para Armazenamento em CDNs
📋 Introdução
CDN: Rede de servidores para fornecer conteúdo da Web.

Funcionamento: Armazena conteúdo em cache em servidores de borda próximos aos usuários.

🌍 Explorar as Redes de Distribuição de Conteúdo do Azure
📈 Visão Geral
Fornece conteúdo de alta largura de banda.

Acelera conteúdo dinâmico.

💡 Benefícios
Melhor desempenho e experiência do usuário.

Grande dimensionamento.

Reduz tráfego ao servidor de origem.

🔧 Como Funciona
Alice solicita um arquivo com URL especial (ex.: <nome_do_endpoint>.azureedge.net).

Servidores de borda verificam se o arquivo está em cache.

Se não, POP solicita o arquivo do servidor de origem.

Servidor de origem retorna o arquivo ao POP.

POP armazena o arquivo em cache e retorna para Alice.

Outros usuários podem usar a mesma URL.
📋 Requisitos
Criar pelo menos um perfil CDN.

Organizar pontos de extremidade por perfil.

🔄 Limitações
Limites de perfis CDN, pontos de extremidade e domínios personalizados.

💻 Produtos CDN do Azure
Produto	Descrição
CDN Standard do Azure da Microsoft	Funcionalidades básicas.
CDN do Azure Standard da Edgio	Funcionalidade padrão com melhorias.
CDN do Azure Premium da Edgio	Funcionalidades premium para desempenho e segurança.
🔍 Controlar o Comportamento de Cache nas CDNs do Azure
📋 Visão Geral
Recursos em cache podem estar desatualizados.

Recurso em cache não é sempre comparado com o servidor de origem.

Se considerado atualizado, enviado diretamente ao cliente.

Recurso atualizado conforme configuração de cache.

📋 Controlando o Cache
Mecanismos principais: Regras de cache e cache da cadeia de consulta.

Regras de Cache na CDN do Azure Standard da Microsoft:

Ignorar cadeias de consulta.

Ignorar cache das cadeias de consulta.

Armazenar em cache cada URL exclusiva.

⏳ Cache e Vida Útil
Como Funciona: Arquivos armazenados em cache até TTL expirar.

Cache-Control: Cabeçalho HTTP define duração do TTL.

Valor Padrão: CDN define TTL padrão, substituível via regras de cache.

📋 Valores Padrão de TTL
Otimização	TTL Padrão
Distribuição da Web	7 dias
Arquivos Grandes	1 dia
Streaming de Mídia	1 ano
🔄 Atualização de Conteúdo
Operação normal: Nó de borda fornece ativo até TTL expirar.

Revalidar: Reconexão ao servidor de origem redefine TTL.

Cadeia de Versão: Garante recuperação imediata da versão mais recente.

Limpeza de Cache: Atualiza conteúdo na próxima solicitação do cliente.

🧩 Interagir com o Azure Content Delivery Networks (CDN) usando .NET
💻 Biblioteca Azure CDN para .NET
Ações Comuns

Criar um cliente da CDN

Relacionar perfis CDN e pontos de extremidade

Criar perfis CDN e pontos de extremidade

Limpar um ponto de extremidade

📜 Exemplo de Código para Criar um Cliente da CDN
csharp
static void Main(string[] args)
{
    // Create CDN client
    CdnManagementClient cdn = new CdnManagementClient(new TokenCredentials(authResult.AccessToken))
    {
        SubscriptionId = subscriptionId
    };
}
📋 Relacione Perfis CDN e Pontos de Extremidade
csharp
private static void ListProfilesAndEndpoints(CdnManagementClient cdn)
{
    // List all the CDN profiles in this resource group
    var profileList = cdn.Profiles.ListByResourceGroup(resourceGroupName);
    foreach (Profile p in profileList)
    {
        Console.WriteLine("CDN profile {0}", p.Name);
    }