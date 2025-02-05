# 📊 Dimensionamento de Unidades de Produtividade
O tráfego dos Hubs de Eventos é controlado por unidades de produtividade.

A Captura de Hubs de Eventos copia os dados diretamente do armazenamento interno dos Hubs de Eventos, ignorando as cotas de saída das unidades de produtividade e salvando a saída de outros leitores de processamento.

A Captura de Hubs de Eventos é executada automaticamente quando você envia o primeiro evento.

# ⚙️ Dimensionar seu Aplicativo de Processamento
"O segredo para dimensionar os Hubs de Eventos é a ideia de consumidores particionados. Em contraste com consumidores concorrentes padrão, o padrão de consumidor particionado permite alta escala, removendo o gargalo de contenção e promovendo o paralelismo de ponta a ponta."

## 🌐 Cenário de Exemplo
"Ao projetar o consumidor em um ambiente distribuído, a solução deve lidar com os seguintes requisitos: escala, balanceamento de carga, retomada suave em caso de falhas e consumo de eventos."

## 💻 Processador de Eventos ou Cliente Consumidor
"Você não precisa criar sua própria solução para atender a esses requisitos."

"Os SDKs dos Hubs de Eventos do Azure fornecem essa funcionalidade."

"Para a maioria dos cenários de produção, use o cliente do processador de eventos para ler e processar eventos."

## 🗂️ Acompanhamento de Propriedade da Partição
"Uma instância do processador de eventos normalmente possui e processa eventos de uma ou mais partições."

"Cada processador de eventos recebe um identificador exclusivo e a propriedade de declarações de partições ao adicionar ou atualizar uma entrada em um repositório de ponto de verificação."

## 📬 Receber Mensagens
"Ao criar um processador de eventos, você especifica as funções que processarão eventos e erros."

"É recomendável que você faça coisas de forma relativamente rápida, ou seja, faça o menor processamento possível."

## 🛠️ Definindo o Ponto de Verificação
"Pontos de verificação é um processo pelo qual um processador de eventos marca ou confirma a posição do último evento processado com êxito em uma partição."

"É possível retornar aos dados mais antigos especificando um deslocamento inferior nesse processo de ponto de verificação."

## 🔒 Instâncias de Processador e de Segurança do Thread
"Por padrão, a função que processa os eventos é chamada sequencialmente para uma determinada partição. Os eventos da mesma partição e chamadas subsequentes para essa função são enfileirados em segundo plano enquanto a bomba de eventos continua sendo executada em segundo plano em outros threads."

# 🔐 Controlar o Acesso a Eventos

## 🔑 Funções Internas do Azure
| Função | Descrição |
| --- | --- |
| Proprietário de Dados do Hubs de Eventos do Azure | Acesso completo aos recursos dos Hubs de Eventos |
| Remetente de Dados do Hubs de Eventos do Azure | Acesso para envio aos recursos dos Hubs de Eventos |
| Receptor de Dados do Hubs de Eventos do Azure | Acesso para recebimento aos recursos dos Hubs de Eventos |

## 📋 Autorização de Acesso
- Autorizar o acesso com identidades gerenciadas.
- Autorizar o acesso com o Microsoft Identity Platform.
- Autorizar o acesso a editores de Hubs de Eventos com assinaturas de acesso compartilhado.

# ⚙️ Executar Operações Comuns com a Biblioteca de Clientes dos Hubs de Eventos

## 🔍 Inspecionar um Hub de Eventos
```csharp
await using (var producer = new EventHubProducerClient(connectionString, eventHubName))
{
    string[] partitionIds = await producer.GetPartitionIdsAsync();
}
