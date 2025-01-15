# 🌐 Serviço de Aplicativos do Azure

## 📝 Introdução
- **Baseado em HTTP** para hospedar aplicativos web, APIs REST e back-ends móveis.
- Aplicativos executados e dimensionados em **Windows** e **Linux**.

## 🔧 Recursos Principais

### 💰 Dimensionamento e Custo
- **Dimensionamento Automático**
  - Ajusta o número de instâncias conforme demanda.
  - Monitora métricas dos recursos e ajusta automaticamente.
  - Expande e reduz horizontalmente.
  - **Fatores:**
    - **Métricas de Dimensionamento:** Percentual de CPU, Porcentagem de Memória, Comprimento da Fila de Disco, Comprimento da Fila HTTP, Entrada/Saída de Dados.
    - **Condições:** Baseadas em métricas ou cronogramas (hora do dia, dia da semana).

### 🔗 Integração e Implantação
- **Integração/Implantação Contínuas**
  - Ferramentas: Azure DevOps, GitHub, Bitbucket, FTP, Repositório Git Local.
- **Tipos de Implantação**
  - **Automatizada:** Azure DevOps, GitHub, Bitbucket.
  - **Manual:** Git, CLI, Zipdeploy, FTP/S.
- **Slots de Implantação**
  - Testar em ambientes separados antes de produção.
  - Trocar configurações e conteúdo entre slots.

### 🖥️ Planos e Camadas de Serviço
- **Planos do Serviço de Aplicativo**
  - Define um conjunto de recursos de computação.
  - Pode ser ampliado ou reduzido conforme necessário.
- **Camadas de Uso:**

| Camada       | Descrição                               | Recursos                           |
|--------------|-----------------------------------------|------------------------------------|
| Compartilhado| Recursos compartilhados para dev/teste  | Não escalável horizontalmente      |
| Básico       | Computação dedicada para dev/teste      | Limitado ao dimensionamento manual |
| Padrão       | Executar cargas de trabalho de produção | Escalável horizontalmente          |
| Premium      | Desempenho e escalabilidade aprimorados | Escalável horizontalmente          |
| Isolado      | Alto desempenho, segurança e isolamento | Escalável horizontalmente          |

## ⚙️ Configurações do Aplicativo Web

### 📑 Definir Configurações
- **Adicionar e Editar Configurações**
  - **Nova Configuração de Aplicativo**
  - **Edição Avançada** para configurações em massa.
- **Cadeias de Conexão**
  - Segue os mesmos princípios de outras configurações de aplicativos.
  - Vinculáveis a slots de implantação.

### 🛠️ Configurações Gerais
- **Configurações de Pilha**
  - Define a pilha de software, incluindo versões da linguagem e do SDK.
- **Configurações de Plataforma**
  - Número de bits (32 ou 64 bits), Protocolo WebSocket, Always On, Versão do Pipeline Gerenciado, Versão HTTP, Afinidade ARR.
- **Depuração**
  - Habilitar depuração remota para ASP.NET, ASP.NET Core ou Node.js.
- **Certificados de Cliente de Entrada**
  - Autenticação mútua TLS para restrição de acesso.
- **Mapeamento de Caminho**
  - **Linux e Contêineres:** Adicionar armazenamento personalizado.
  - **Windows (não conteinerizado):** Personalizar mapeamentos do IIS e aplicativos virtuais.

### 📝 Habilitar Log de Diagnósticos

| Tipo                          | Plataforma              | Descrição                                                        |
|-------------------------------|-------------------------|------------------------------------------------------------------|
| **Aplicação**                 | Windows e Linux         | Mensagens geradas pelo código do aplicativo.                     |
| **Servidor Web**              | Windows                 | Dados de solicitação HTTP brutos no formato W3C.                 |
| **Erros Detalhados**          | Windows                 | Cópias das páginas de erro .html enviadas ao navegador do cliente|
| **Solicitação de Rastreamento** | Windows               | Informações de rastreamento sobre falhas.                        |
| **Implantação**               | Windows e Linux         | Automático, sem configurações de definição.                      |

### 🔐 Certificados de Segurança
- **Opções de Adição**
  - Certificado gerenciado gratuito.
  - Comprar um certificado.
  - Importar do Key Vault.
  - Carregar certificado privado ou público.

## 🔍 Dimensionamento de Aplicativos no Azure

### 📊 Fatores de Dimensionamento Automático
- **Condições de Dimensionamento**
  - Métrica (uso da CPU, fila de disco) ou cronograma (hora do dia, dia da semana).
- **Métricas:**

| Métrica                  | Descrição                                    |
|--------------------------|----------------------------------------------|
| **Percentual de CPU**    | Uso da CPU em todas as instâncias            |
| **Porcentagem de Memória** | Uso da memória em todas as instâncias      |
| **Fila de Disco**        | Comprimento das solicitações de E/S pendentes|
| **Fila HTTP**            | Número de solicitações do cliente            |
| **Entrada de Dados**     | Número de bytes recebidos                    |
| **Saída de Dados**       | Número de bytes enviados                     |

### 🚀 Habilitação do Dimensionamento Automático
- **Tipos de Preço**
  - Nem todos suportam dimensionamento automático.
- **Adicionar Condições**
  - Condição de dimensionamento padrão criada, podendo ser editada ou adicionar mais.
- **Criar Regras**
  - Com base no calendário, métrica ou ambos.
- **Monitorar**
  - Alterações exibidas no gráfico "Histórico de Execuções".
  - Controla o número de instâncias e condição que disparou a alteração.

### 💡 Práticas Recomendadas
- Valores mínimos e máximos com margem suficiente.
- Escolher estatísticas apropriadas para métricas.
- Escolher limites cuidadosamente.
- Verificar conflitos em múltiplas regras.
- Selecionar contagem de instância de segurança padrão.
- Configurar notificações.

## 🔄 Slots de Implantação no Azure

### 🔧 Ambientes de Preparo
- **Benefícios**
  - Validar alterações antes da produção.
  - Garantir que instâncias estejam aquecidas antes da produção.
  - Troca mantém aplicativo de produção anterior no slot de preparo.

### 🔄 Troca de Slots
- **Passos**
  - Aplicar configurações do slot de destino às instâncias do slot de origem.
  - Esperar reinicialização das instâncias.
  - Disparar inicialização do cache local, se habilitado.
  - Preparação personalizada, se habilitada.
  - Trocar slots após sucesso na ativação de instâncias.
  - Aplicar configurações e reiniciar instâncias do slot de origem.

### 🔁 Trocar Slots de Implantação
- **Métodos**
  - Página "Slots de Implantação" e "Visão Geral".
  - Configurar troca automática.
  - Alternância com visualização.
  - Preparação personalizada.
  - Reverter e monitorar troca.

## 🔀 Roteamento de Tráfego

### 🔄 Produção Automática
- **Método**
  - Página de recursos do aplicativo.
  - Selecionar "Slots de Implantação".
  - Especificar percentual de tráfego (0 a 100).

### 🔄 Produção Manual
- **Método**
  - Parâmetro de consulta `x-ms-routing-name` para rotear para slot específico.
  - Útil para aceitação ou recusa de versão beta.
