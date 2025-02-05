# 🌐 Blueprints, Política e Bloqueio de Recursos no Azure

## 🎯 Azure Policy
- **Objetivo**: Impor padrões organizacionais e avaliar a conformidade em escala.
- **Funções Principais**:
  - 📊 Governança e Consistência: Conformidade regulatória, segurança, custo e gerenciamento.
  - 🔍 Avaliação e Identificação: Recursos não atendem às políticas.
  - 📋 Políticas e Iniciativas: Armazenamento, rede, computação, central de segurança e monitoramento.
  - 🚫 Non-Compliant: Recursos mantidos como não conformes.
  - ✅ Compliant: Itens atendidos.

## 🔒 Gerenciando Bloqueios de Recursos
- **Objetivo**: Proteger recursos do Azure contra exclusão ou modificação acidental.
- **Tipos de Bloqueio**:
  - | Tipo      | Ler | Atualizar | Excluir |
  |-----------|-----|-----------|---------|
  | Excluir   | ✅   | ✅         | ❌       |
  | ReadOnly  | ✅   | ❌         | ❌       |

- **Funcionalidades**:
  - Níveis de Bloqueio: Assinatura, grupo de recursos ou nível de recursos individuais.

## 🔑 Portal de Confiança do Serviço
- **Objetivo**: Acesso a todas as regras seguidas pela Microsoft.
- **Link Público**: [Portal de Confiança do Serviço](https://servicetrust.microsoft.com/)

## 📊 Microsoft Purview
- **Objetivo**: Soluções de governança, risco e conformidade de dados.
- **Funcionalidades**:
  - 🕵️‍♂️ Descoberta de Dados Automatizado: Identificação automática de dados.
  - 🔒 Classificação de Dados Confidenciais: Categorização de dados sensíveis.
  - 🔄 Linhagem de Dados de Ponta a Ponta: Rastreabilidade do ciclo de vida dos dados.

## 🔗 Referências
1. 📚 Microsoft Azure Documentation. (2023). *Azure Policy Overview*. Recuperado de [Azure Documentation](https://docs.microsoft.com/en-us/azure/governance/policy/overview)
2. 📚 Microsoft Learn. (2023). *Manage resource locks*. Recuperado de [Microsoft Learn](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/lock-resources)
3. 📚 Microsoft Purview. (2023). *Data governance solutions*. Recuperado de [Microsoft Purview](https://www.microsoft.com/en-us/security/business/microsoft-purview)

## 🔄 Conclusão
Esta anotação fornece uma visão abrangente sobre Blueprints, Política e Bloqueio de Recursos no Azure, utilizando técnicas de anotação como Bullet Points, Tabelas, Palavras-Chave e Referências para apresentação clara e organizada.

## 📝 Resumo dos Pontos Abordados
- **Introdução** ao conceito de Blueprints, Política e Bloqueio de Recursos no Azure.
- **Detalhamento** do Azure Policy e suas funcionalidades.
- **Gerenciamento** e tipos de bloqueios de recursos.
- **Acesso** ao Portal de Confiança do Serviço.
- **Funcionalidades** do Microsoft Purview para governança de dados.
- **Referências** bibliográficas que complementam