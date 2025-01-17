# 🌐 Explora o Azure Cosmos DB

## 📚 Introdução
- O Azure Cosmos DB é um banco de dados NoSQL totalmente gerenciado.
- Projetado para fornecer baixa latência e escalabilidade elástica da taxa de transferência.
- Consistência dos dados e alta disponibilidade bem definidas.

## 🔍 Principais Benefícios
### 🌍 Replicação Global
- Replicação automática e síncrona de várias regiões.
- Suporte a failover automático e manual.

### 🔄 Níveis de Consistência Variados
- Cinco modelos de consistência com controle sobre equilíbrio entre consistência e desempenho.
- Suporte de SLAs abrangentes.

### ⚡ Baixa Latência
- Atende a solicitações de leitura e gravação em menos de 10 ms no 99º percentil.

### 📈 Dimensionamento Elástico
- Dimensionamento elástico da taxa de transferência de dezenas a centenas de milhões de solicitações/segundo em várias regiões.

## 📂 Hierarquia de Recursos
| Elemento          | Descrição                                                                                     |
|-------------------|------------------------------------------------------------------------------------------------|
| **Conta**         | Unidade fundamental de distribuição global e alta disponibilidade, com um nome DNS exclusivo.  |
| **Banco de Dados**| Unidade de gerenciamento de um conjunto de contêineres, é análogo a um namespace.              |
| **Contêineres**   | Unidade de escalabilidade para taxa de transferência e armazenamento, particionado horizontalmente e replicado em várias regiões. |
| **Itens**         | Dependendo da API usada, pode representar um documento, uma linha em uma tabela ou um nó/borda em um grafo. |

## ⚖️ Níveis de Consistência
| Nível de Consistência  | Descrição                                                                                                                                              |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Forte**              | Operações de gravação são confirmadas no primário após replicação em todas as réplicas.                                                                   |
| **Desatualização Limitada** | Semelhante ao nível Forte, permite configurar quanto tempo (ou versões) um documento de réplica pode ficar desatualizado em relação ao primário.     |
| **Sessão**             | Garante consistência em uma sessão de usuário, todas as leituras e gravações são consistentes.                                                            |
| **Prefixo Coerente**   | Atualizações aparecem na ordem correta sem lacunas.                                                                                                     |
| **Eventual**           | Confirma qualquer operação de gravação no primário imediatamente, consistência eventual ao longo do tempo.                                              |

### 🎯 Benefícios Adicionais
- **Maior Disponibilidade**
- **Menor Latência**
- **Maior Taxa de Transferência**

## 📝 Escolhendo o Nível Certo de Consistência
| Cenário                                   | Nível de Consistência Recomendado                                                                                                             |
|-------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Azure Cosmos DB para NoSQL / Tabela**   | Coerência de sessão para muitos cenários do mundo real, consistência forte se necessário, consistência eventual para maior disponibilidade e menor latência. |
| **Azure Cosmos DB para Cassandra / MongoDB / Apache Gremlin** | Suporte nativo para transmissão compatível com protocolos de APIs populares, consistência padrão configurada na conta para Apache Gremlin.   |

### 💡 Garantias de Consistência na Prática
- Consistência de leitura vinculada ao pedido e propagação de operações de gravação/atualização.

## 💻 APIs com Suporte
| API                      | Descrição                                                                                        |
|--------------------------|--------------------------------------------------------------------------------------------------|
| **NoSQL**                | Armazena dados no formato de documento, controle total sobre a interface e bibliotecas de clientes do SDK. |
| **MongoDB**              | Armazena dados em formato de documentos JSON, compatível com o protocolo MongoDB.                  |
| **Apache Cassandra**     | Armazena dados em esquema orientado a colunas, compatível com o protocolo do Apache Cassandra.     |
| **Tabela**               | Armazena dados no formato chave/valor.                                                            |
| **Apache Gremlin**       | Permite consultas de gráfico e armazenamento de dados como bordas e vértices.                      |
| **PostgreSQL**           | Armazena dados em um único nó ou distribuídos em configuração de diversos nós.                    |

## 📊 Unidades de Solicitação
| Tipo de Conta                        | Descrição                                                                                          |
|--------------------------------------|----------------------------------------------------------------------------------------------------|
| **Taxa de Transferência Provisionada**| Gerenciamento do número de RUs em incrementos de 100 RUs por segundo.                                |
| **Sem Servidor**                     | Cobrança pelo número de RUs consumidas pela operação de banco de dados.                             |
| **Dimensionamento Automático**       | Dimensionamento automático e instantâneo com base no uso.                                          |

## 💼 Trabalhando com o Azure Cosmos DB

### 🔎 Explorando o SDK do Microsoft .NET v3 para Azure Cosmos DB

```vbnet
// Obter referência ao contêiner
CosmosClient client = new CosmosClient(endpoint, key);
Container container = client.GetContainer(databaseName, collectionName);

// Criar tipo anônimo no .NET
Product orangeSoda = new Product {
    id = "7cc3212d-0e2c-4a13-b348-f2d879c43342",
    name = "Orange Soda", group = "Beverages",
    diet = false, price = 1.50m, quantity = 2000
};

// Upload do item
Product item = await container.CreateItemAsync(orangeSoda);
Product item = await container.UpsertItemAsync(orangeSoda);


Podem ser invocadas somente de dentro das consultas.

Não têm acesso ao objeto de contexto e devem ser usadas como código somente de computação.

## 🔄 Explorar o Feed de Alterações no Azure Cosmos DB
- O feed de alterações no Azure Cosmos DB é um registro persistente de alterações em um contêiner na ordem em que ocorrem.
- É possível trabalhar com o feed de alterações usando um modelo push ou pull.
- Recomenda-se usar o modelo push, pois não há necessidade de se preocupar em consultar o feed de alterações futuras.

### Modelos de Leitura do Feed de Alterações
| Modelo                                           | Descrição                                                                                                                |
|--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| **Gatilhos do Azure Cosmos DB para Azure Functions** | Disparados automaticamente a cada novo evento no feed de alterações do contêiner do Azure Cosmos DB.                       |
| **Processador de Feed de Alterações**            | Parte dos SDKs do .NET V3 e do Java V4 do Azure Cosmos DB. Simplifica a leitura do feed de alterações e distribui o processamento de eventos entre vários consumidores de forma eficiente. |
