# 🌐 Descubra as filas de mensagens do Azure

## 🌟 Introdução
- **Azure** dá suporte a dois tipos de mecanismos de fila:
  - **Filas de Barramento de Serviço** 🚌: Compatível com enfileiramento, publicação/assinatura e padrões avançados.
  - **Filas de Armazenamento** 📦: Permitem armazenar um grande número de mensagens.

## 🎯 Escolher uma solução de fila de mensagens

### ✅ Considere usar filas de Barramento de Serviço quando:
- 📬 Receber mensagens sem necessidade de sondar a fila.
- 📜 Necessidade de entrega ordenada PEPS (primeiro a entrar, primeiro a sair).
- 🔄 Suporte à detecção automática de duplicatas.
- 🔄 Processamento de mensagens como fluxos paralelos de longa execução.
- 📦 Mensagens que podem exceder 64 KB (até 256 KB).

### ✅ Considere usar filas de Armazenamento quando:
- 🗃️ Armazenamento de mais de 80 GB de mensagens.
- ⏲️ Acompanhamento do progresso do processamento de uma mensagem.
- 📝 Necessidade de logs do lado do servidor de todas as transações executadas em suas filas.

## 🔍 Explorar o Barramento de Serviço do Azure

### 🌟 Cenários mais comuns:
1. **Mensagens** ✉️: Transferir dados corporativos (ex.: ordens de venda/compra, diários, movimentos de estoque).
2. **Separar aplicativos** 🖥️: Aprimorar a confiabilidade e a escalabilidade dos aplicativos.

### 📌 Pontos adicionais:
- **Tópicos e assinaturas** 🗂️: Habilitar relações de 1 para n entre editores e assinantes.
- **Sessões de mensagens** 💬: Implementar fluxos de trabalho que exijam ordenação ou adiamento de mensagens.

### ⚖️ Comparação entre os níveis Premium e Standard:
| **Recursos**                               | **Premium**               | **Standard**                    |
|--------------------------------------------|---------------------------|---------------------------------|
| **Taxa de transferência**                  | Alta                      | Variável                        |
| **Desempenho**                             | Previsível                | Latência variável               |
| **Preço**                                  | Fixo                      | Pré-pago variável               |
| **Capacidade de escalar a carga de trabalho** | Verticalmente             | N/D                             |
| **Tamanho da mensagem**                    | Até 100 MB                | Até 256 KB                      |

## 🗂️ Descubra filas, tópicos e assinaturas do Barramento de Serviço

### 📨 Filas
- Oferecem entrega de mensagem tipo FIFO (primeiro a entrar, primeiro a sair) para um ou mais consumidores concorrentes.

### 🔄 Modos de recebimento:
- **Recebimento e exclusão** 🗑️: Mensagens são removidas da fila após recebidas.
- **Bloqueio de espiada** 🔒: Mensagens são bloqueadas temporariamente para que não sejam processadas por outros consumidores.

### 🗂️ Tópicos e assinaturas:
- **Publicação e assinatura** 📰: Comunicação de um para muitos.

### 🔧 Regras e ações:
- Configurar assinaturas para localizar mensagens com propriedades desejáveis e modificar essas propriedades.
- Usar ações de filtro para copiar um subconjunto de mensagens para a fila de assinatura virtual.

## 💬 Explorar o conteúdo e a serialização de mensagens no Barramento de Serviço

### 🔄 Padrões de roteamento e correlação de mensagens:
- **Solicitação/resposta simples** 🔄: Editor envia uma mensagem para uma fila e espera uma resposta.
- **Solicitação/resposta multicast** 📬: Editor envia a mensagem para um tópico e vários assinantes podem consumi-la.
- **Multiplexação** 🔀: Sessão permite a multiplexação de fluxos de mensagens relacionadas por meio de uma fila/assinatura.
- **Solicitação/resposta multiplexada** 🔄: Multiplexação de fluxos de mensagens relacionadas por meio de uma fila/assinatura.

### 📜 Serialização de payload:
- **ContentType** 📦: Propriedade que descreve o conteúdo.
- **BrokeredMessage** 📨: Instâncias criadas passando objetos .NET arbitrários para o construtor.
- **Protocolos de serialização**:
  - **SBMP herdado** 🛠️: Objetos serializados com o serializador binário padrão ou fornecido externamente.
  - **AMQP** 🔄: Objeto serializado em AMQP Bytes.

## 📦 Explorar o Armazenamento de Filas do Azure

### 🗂️ Explorar o Armazenamento de Filas do Azure:
- **Serviço** 📦: Armazenamento de grandes quantidades de mensagens.
- **Limite de tamanho de mensagem** 📏: Até 64 KB.
- **Componentes**:
  - **Formato de URL** 🌐: `https://<conta>.queue.core.windows.net/<fila>`
  - **Conta de Armazenamento** 🏦: Acesso ao Armazenamento do Azure.
  - **Fila** 📂: Conjunto de mensagens.
  - **Mensagem** 📨: Formato qualquer, até 64 KB. Vida útil máxima configurável.

### 🛠️ Criar e gerenciar filas e mensagens do Armazenamento de Filas do Azure usando o .NET:

#### 📦 Pacotes NuGet necessários:
1. **Azure.Core para .NET** 📦: Primitivos compartilhados, abstrações e auxiliares.
2. **Azure.Storage.Common para .NET** 📂: Infraestrutura compartilhada.
3. **Azure.Storage.Queues para .NET** 📬: Trabalho com armazenamento de Filas do Azure.
4. **System.Configuration.ConfigurationManager para .NET** 🛠️: Acesso aos arquivos de configuração.
