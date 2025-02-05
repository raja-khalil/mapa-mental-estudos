# 🌐 Grade de Eventos do Azure e Hubs de Eventos do Azure

## 📝 Introdução
- **Grade de Eventos do Azure:**
  - 🔄 Integrada aos serviços do Azure
  - 📉 Reduz custos e elimina sondagem constante
  - 🚀 Roteia eventos de forma eficiente e confiável

- **Hubs de Eventos do Azure:**
  - 📊 Plataforma de streaming de Big Data
  - ⚡ Processa milhões de eventos por segundo
  - 🗄️ Transforma e armazena dados

## 🔍 Explorar a Grade de Eventos do Azure

### 🔷 O que é a Grade de Eventos
- Backplane de eventos
- Suporte nativo para eventos do Azure
- Criação de eventos com tópicos personalizados
- Uso de filtros para roteamento de eventos

### 📊 Cinco Conceitos Fundamentais
1. **Eventos:** Descrevem o que está acontecendo no sistema
2. **Origens do Evento:** Onde o evento acontece
3. **Tópicos:** Ponto de extremidade onde a fonte envia eventos
4. **Assinaturas do Evento:** Informa quais eventos você quer receber
5. **Manipuladores de Evento:** Local para onde o evento é enviado para processamento

### 🖼️ Diagrama da Grade de Eventos
| Origens de Evento | Grade de Eventos | Manipuladores de Evento |
| --- | --- | --- |
| Armazenamento de Blobs, Grupos de Recursos, Assinaturas do Azure, Hubs de Eventos, Serviço de Mídia do Azure, Hub IoT, Barramento de Serviço, Azure Mapas, Fontes de CloudEvents, Eventos Personalizados | Ícone Central | Código Sem Servidor (Funções), Workflow e Integração Sem Servidor (Aplicativos Lógicos), Armazenagem em Buffer e Consumidores (Hubs de Eventos, Filas de Armazenamento), Outros Serviços e Aplicativos (Conexões Híbridas, WebHooks, Automação do Azure) |

## 📜 Descobrir os Esquemas de Evento

### 📋 Propriedades do Evento
| Propriedade | Tipo | Obrigatório |
| --- | --- | --- |
| tópico | string | Não |
| subject | string | Sim |
| eventType | string | Sim |
| eventTime | string | Sim |
| ID | cadeia de caracteres | Sim |
| data | objeto | Não |
| dataVersion | string | Não |
| metadataVersion | string | Não |

### 📝 Exemplo de Evento do Armazenamento de Blobs do Azure
```json
[
  {
    "topic": "...",
    "subject": "...",
    "eventType": "Microsoft.Storage.BlobCreated",
    "eventTime": "2017-06-26T18:41:00.9584103Z",
    "id": "831e1650-001e-001b-66ab-eeb76e069631",
    "data": {
      "api": "PutBlockList",
      "eTag": "0x8D4BCC2E4835CD0",
      "storageDiagnostics": {
        "batchId": "b68529f3-68cd-4744-baa4-3c0498ec19f0"
      },
      "clientRequestId": "6d79dbfb-0e37-4fc4-981f-442c9ca65760",
      "requestId": "831e1650-001e-001b-66ab-eeb76e000000",
      "contentType": "application/octet-stream",
      "contentLength": 524288,
      "blobType": "BlockBlob",
      "sequencer": "00000000000004420000000000028963",
      "url": "https://test.blob.core.windows.net/container/blob"
    },
    "dataVersion": "",
    "metadataVersion": "1"
  }
]
