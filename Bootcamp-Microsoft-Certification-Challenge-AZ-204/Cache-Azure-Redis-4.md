# 🔩 Outras Operações Comuns
| Método             | Descrição                                                    |
|--------------------|--------------------------------------------------------------|
| CreateBatch        | Cria um grupo de operações enviado como unidade única.       |
| CreateTransaction  | Cria um grupo de operações processada como unidade única.    |
| KeyDelete          | Exclui a chave/valor.                                        |
| KeyExists          | Verifica se a chave existe no cache.                         |
| KeyExpire          | Define expiração de TTL (vida útil) em uma chave.            |
| KeyRename          | Renomeia uma chave.                                          |
| KeyTimeToLive      | Retorna a TTL de uma chave.                                  |
| KeyType            | Retorna o tipo do valor armazenado na chave.                 |

# 🌐 Desenvolver para Armazenamento em CDNs
## 📋 Introdução
- **CDN:** Rede de servidores para fornecer conteúdo da Web.
- **Funcionamento:** Armazena conteúdo em cache em servidores de borda próximos aos usuários.

# 🌍 Explorar as Redes de Distribuição de Conteúdo do Azure
## 📈 Visão Geral
- Fornece conteúdo de alta largura de banda.
- Acelera conteúdo dinâmico.

## 💡 Benefícios
- Melhor desempenho e experiência do usuário.
- Grande dimensionamento.
- Reduz tráfego ao servidor de origem.

## 🔧 Como Funciona
1. Alice solicita um arquivo com URL especial (ex.: `<nome_do_endpoint>.azureedge.net`).
2. Servidores de borda verificam se o arquivo está em cache.
3. Se não, POP solicita o arquivo do servidor de origem.
4. Servidor de origem retorna o arquivo ao POP.
5. POP armazena o arquivo em cache e retorna para Alice.
6. Outros usuários podem usar a mesma URL.
7. Se TTL não expirou, POP retorna diretamente do cache.

## 📋 Requisitos
- Criar pelo menos um perfil CDN.
- Organizar pontos de extremidade por perfil.

## 🔄 Limitações
- Limites de perfis CDN, pontos de extremidade e domínios personalizados.

## 💻 Produtos CDN do Azure
| Produto                            | Descrição                                             |
|------------------------------------|-------------------------------------------------------|
| CDN Standard do Azure da Microsoft | Funcionalidades básicas.                              |
| CDN do Azure Standard da Edgio     | Funcionalidade padrão com melhorias.                  |
| CDN do Azure Premium da Edgio      | Funcionalidades premium para desempenho e segurança.  |

# 🔍 Controlar o Comportamento de Cache nas CDNs do Azure
## 📋 Visão Geral
- Recursos em cache podem estar desatualizados.
- Recurso em cache não é sempre comparado com o servidor de origem.
- Se considerado atualizado, enviado diretamente ao cliente.
- Recurso atualizado conforme configuração de cache.

## 📋 Controlando o Cache
- **Mecanismos principais:** Regras de cache e cache da cadeia de consulta.
- **Regras de Cache na CDN do Azure Standard da Microsoft:**
  1. Ignorar cadeias de consulta.
  2. Ignorar cache das cadeias de consulta.
  3. Armazenar em cache cada URL exclusiva.

## ⏳ Cache e Vida Útil
- **Como Funciona:** Arquivos armazenados em cache até TTL expirar.
- **Cache-Control:** Cabeçalho HTTP define duração do TTL.
- **Valor Padrão:** CDN define TTL padrão, substituível via regras de cache.

## 📋 Valores Padrão de TTL
| Otimização                   | TTL Padrão  |
|------------------------------|-------------|
| Distribuição da Web          | 7 dias      |
| Arquivos Grandes             | 1 dia       |
| Streaming de Mídia           | 1 ano       |

## 🔄 Atualização de Conteúdo
1. **Operação normal:** Nó de borda fornece ativo até TTL expirar.
2. **Revalidar:** Reconexão ao servidor de origem redefine TTL.
3. **Cadeia de Versão:** Garante recuperação imediata da versão mais recente.
4. **Limpeza de Cache:** Atualiza conteúdo na próxima solicitação do cliente.

# 🧩 Interagir com o Azure Content Delivery Networks (CDN) usando .NET
## 💻 Biblioteca Azure CDN para .NET
**Ações Comuns**
- Criar um cliente da CDN
- Relacionar perfis CDN e pontos de extremidade
- Criar perfis CDN e pontos de extremidade
- Limpar um ponto de extremidade

## 📜 Exemplo de Código para Criar um Cliente da CDN
```csharp
static void Main(string[] args)
{
    // Create CDN client
    CdnManagementClient cdn = new CdnManagementClient(new TokenCredentials(authResult.AccessToken))
    {
        SubscriptionId = subscriptionId
    };
}
