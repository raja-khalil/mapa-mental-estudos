# 📦 Explorar a Durabilidade da Entrega de Eventos

## 🔄 Agenda de Repetição
Decide entre tentar novamente, desativar ou descartar o evento com base no tipo de erro

## ⚙️ Política de Repetição
Personalização ao criar uma assinatura de evento, configurando tentativas e tempo de vida

## 📦 Envio em Lote de Saída
Agrupamento de eventos em lotes para entrega, melhorando o desempenho do HTTP

## ⏱️ Entrega Atrasada
Se o endpoint falhar, a entrega do evento será atrasada e tentada novamente

## 🗑️ Eventos Inativos
Eventos não entregues dentro de um período ou número de tentativas são considerados inativos

# 🔐 Controlar o Acesso a Eventos

## 🔑 Funções Internas da Grade de Eventos do Azure
| Função | Descrição |
| --- | --- |
| Leitor de assinatura da Grade de Eventos | Leia operações de assinatura de evento da Grade de Eventos |
| Colaborador de Assinatura da Grade de Eventos | Gerencie operações de assinatura de evento da Grade de Eventos |
| Colaborador da Grade de Eventos | Crie e gerencie recursos da Grade de Eventos |
| Remetente de dados da Grade de Eventos | Envie eventos para tópicos da Grade de Eventos |

## 📋 Permissões para Assinaturas de Evento
| Tipo de Tópico | Descrição |
| --- | --- |
| Tópicos do sistema | Permissão para gravar nova assinatura de evento no escopo do recurso |
| Tópicos personalizados | Permissão para gravar nova assinatura de evento no escopo do tópico da grade de eventos |

# 🌐 Receber Eventos Usando WebHooks

## 🛠️ Serviços da Azure que Utilizam WebHooks
- Aplicativos Lógicos do Azure com Conector da Grade de Eventos
- Automação do Azure por meio de WebHook
- Azure Functions com Gatilho de Grade de Eventos

## 🤝 Formas de Verificar a Assinatura
- **Handshake Síncrono:** No momento da criação da assinatura, um Evento de Validação de Assinatura é postado para o ponto de extremidade de destino
- **Handshake Assíncrono:** Para casos em que o ValidationCode não pode ser retornado de forma síncrona

# ⚙️ Filtrar Eventos

## 🔍 Métodos de Filtragem

### Filtragem de Tipo de Evento:
- Por padrão, todos os tipos de evento são enviados ao ponto de extremidade.
- Opção para enviar somente determinados tipos de evento.

### Filtro de Assunto:
- Especificar um valor inicial ou final para o assunto.
- Exemplo: Filtrar assuntos com `/blobServices/default/containers/testcontainer` para obter eventos específicos.

### Filtragem Avançada:
- Filtrar por valores nos campos de dados e especificar o operador de comparação.

# 📈 Explorar Hubs de Eventos do Azure

## 🌟 O que é o Hub de Eventos
- Plataforma de streaming de Big Data e serviço de ingestão de eventos
- Recebe e processa milhões de eventos por segundo

## 🔑 Componentes Principais
- **Cliente do Hub de Eventos:** Interface para desenvolvedores
- **Produtor do Hub de Eventos:** Fonte de dados de telemetria, logs, etc.
- **Consumidor do Hub de Eventos:** Cliente que lê e processa informações
- **Partição:** Sequência ordenada de eventos
- **Grupo de Consumidores:** Permite múltiplos aplicativos de consumo
- **Receptores de Evento:** Entidade que lê dados de um Event Hub
- **Unidades de Produtividade:** Unidades adquiridas para aumentar a capacidade

## 🗂️ Tabela
| Recurso | Descrição |
| --- | --- |
| **PaaS totalmente gerenciado** | Serviço totalmente gerenciado com pouca configuração |
| **Processamento em tempo real e em lote** | Modelo de consumidor particionado, permitindo múltiplos aplicativos |
| **Escalonável** | Ampliação automática para atender às necessidades de uso |
| **Ecossistema avançado** | Compatível com ecossistemas do Apache Kafka |

# 📊 Explorar a Captura de Hubs de Eventos

## 📈 Captura Automática de Dados
- Captura automática dos dados de streaming para uma conta do Armazenamento de Blobs do Azure ou do Azure Data Lake Store

## 💡 Processamento em Tempo Real e Baseado em Lote
- Permite processar pipelines em tempo real e baseados em lote no mesmo fluxo

## 🖼️ Descrição do Diagrama
| Parte | Descrição |
| --- | --- |
| **Hub de Eventos** | Caixa à esquerda com quatro partições: "Partição 1", "Partição 2", "Partição 3", e "Partição 4" |
| **Processo de Captura** | Ícone no meio rotulado como "Capture" |
| **Armazenamento** | Caixa à direita rotulada como "Armazenamento de Blobs do Azure" e "Armazenamento do Azure Data Lake", mostrando um grid com quadrados verdes e setas tracejadas indicando o fluxo de dados |

## ⏲️ Janelas da Captura
- Configure uma janela para controlar a captura
- Cada partição captura de forma independente e grava um blob de blocos completo durante o tempo de captura
