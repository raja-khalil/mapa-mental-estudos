# 💡 Solucionar Problemas Usando o Application Insights

## 🌟 Introdução
- **Instrumentação e monitoramento**: Maximizam a disponibilidade e desempenho dos aplicativos.
- **Application Insights**: Extensão do Azure Monitor, fornece recursos de APM (Monitoramento de Desempenho do Aplicativo).
- **Coleta de Dados**: Métricas e telemetria, descreve atividades e integridade do aplicativo. Também coleta e armazena dados de log de rastreamento.

## 🔍 Explorar o Application Insights

### 🛠️ Recursos
| Recurso | Descrição |
| --- | --- |
| **Live Metrics** | Atividade em tempo real do aplicativo implantado sem afetar o ambiente do host. |
| **Disponibilidade** | Monitoramento de Transações Sintéticas para testar a disponibilidade e capacidade de resposta. |
| **Integração do GitHub/DevOps** | Criação de itens de trabalho no contexto dos dados do Application Insights. |
| **Uso** | Identificação de recursos populares e análise de interação do usuário. |
| **Detecção inteligente** | Detecção automática de falhas e anomalias com telemetria proativa. |
| **Mapa de aplicativo** | Visão geral da arquitetura do aplicativo e indicadores visuais de integridade. |
| **Rastreamento distribuído** | Visualização do fluxo de ponta a ponta de uma execução ou transação. |

### 📈 O que o Application Insights Monitora:
- Taxas, tempos de resposta e taxas de falha de solicitação
- Taxas de dependência, tempos de resposta e taxas de falha
- Exceções
- Exibições de página e desempenho de carga
- Chamadas AJAX de páginas da Web
- Contagens de sessão e usuários
- Contadores de desempenho
- Diagnóstico do host
- Logs de rastreamento de diagnóstico
- Eventos e métricas personalizados

### 🚀 Começar a Monitorar e Analisar o Desempenho:
- Em tempo de execução
- Em tempo de desenvolvimento
- Instrumentar suas páginas da Web
- Analisar o uso do aplicativo móvel
- Testes de disponibilidade

## 📊 Descobrir Métricas Baseadas em Log

### 📝 Métricas Baseadas em Log:
- Armazenamento de eventos como logs pelo back-end do Application Insights.
- Análise e diagnóstico de dados baseados em eventos dos logs.
- Retenção de eventos completos para valor analítico e diagnóstico.
- Desafios na coleta de grandes volumes de telemetria.

### 📉 Métricas Pré-Agregadas:
- Armazenamento como séries temporais pré-agregadas com dimensões principais.
- Pré-agregação de métricas durante a coleta pelos SDKs mais recentes.
- Agregação de eventos recebidos pelo ponto de extremidade do Application Insights para SDKs sem pré-agregação.

## ⚙️ Instrumentação Automática
- Habilitar monitoramento com Application Insights sem alterar o código.
- Configuração do agente para coleta automática de telemetria.
- Visualização de métricas, solicitações e dependências no Application Insights.

### 🔄 Instrumentação para Rastreamento Distribuído:
- Habilitar rastreamento distribuído via SDKs do Application Insights.
- Habilitar rastreamento por meio do OpenCensus.

## 🧪 Selecionar um Teste de Disponibilidade
- Configuração de testes para endpoints HTTP ou HTTPS.
- Sem necessidade de alterações no site testado.
- Testes podem ser para APIs REST de terceiros.
- Até 100 testes de disponibilidade por recurso do Application Insights.
- Tipos de testes de disponibilidade:
  - Teste padrão
  - TrackAvailability personalizado

## 🛠️ Solucionar Problemas de Desempenho com o Mapa do Aplicativo
- Identificação de gargalos e falhas em componentes distribuídos.
- Cada nó representa um componente ou dependência, com KPIs de integridade e alertas de status.
- Diagnóstico detalhado ao clicar em componentes.
- Componentes são partes independentes dos aplicativos distribuídos/de microsserviços.

## 📚 Referências
- Microsoft Docs: [Application Insights Overview](https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview)
- Livro: "Azure Monitoring and Management" por Avinash Valiramani
