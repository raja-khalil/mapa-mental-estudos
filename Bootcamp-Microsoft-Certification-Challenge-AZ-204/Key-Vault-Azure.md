# 🌐 Azure Key Vault e Implementação de Identidades Gerenciadas

## Introdução
- **Azure Key Vault:**
  - Serviço de nuvem para armazenar e acessar segredos de maneira segura 🔒
  - Segredos incluem chaves de API, senhas, certificados ou chaves de criptografia 🗝️
- **Desafio de Identidades Gerenciadas:**
  - Gerenciamento de segredos e credenciais para proteger a comunicação entre componentes 📡
  - Solução: Identidades gerenciadas eliminam a necessidade de gerenciamento de credenciais pelos desenvolvedores 👥

## Funcionalidades do Azure Key Vault
- **Gerenciamento de Segredos:** Armazenamento seguro e controle rigoroso 🔐
- **Gerenciamento de Chaves:** Solução para gerenciamento de chaves 🔑
- **Gerenciamento de Certificados:** Provisione, gerencie e implante certificados SSL/TLS públicos e privados 📜

## Benefícios do Azure Key Vault
- **Segredos de Aplicativos Centralizados:** Controle a distribuição de segredos 📦
- **Segurança:** Armazenamento seguro com autenticação e autorização adequadas 🛡️
- **Monitoramento:** Habilitação de registro em log para monitorar a atividade 📊
- **Administração Simplificada:** Seguir o ciclo de vida e ter alta disponibilidade 🔄

## Melhores Práticas do Azure Key Vault
- **Autenticação:** Utilizar identidades gerenciadas para recursos do Azure ✅
- **Uso de Cofres Separados:** Utilizar cofres de chaves separados por aplicativo e ambiente 📂
- **Controle de Acesso:** Controlar o acesso aos cofres 🚧
- **Backup Regular:** Realizar backups regulares do cofre 💾
- **Registro em Log e Alertas:** Ativar registro em log e alertas 📈
- **Opções de Recuperação:** Configurar opções como exclusão temporária e proteção contra limpeza 🧹

## Autenticação no Azure Key Vault
- **Identidades Gerenciadas:** Uso recomendado de identidades gerenciadas atribuídas pelo sistema 🆔
- **Registro do Aplicativo:** Registro do aplicativo com o locatário do Azure AD 📝
- **No Código do Aplicativo:** Utilização do SDK do Key Vault com a biblioteca de clientes do Azure Identity 💻
- **Usando REST:** Envio de tokens de acesso no cabeçalho de autorização HTTP 📡

## Adquirir um Token de Acesso
- **Solicitação de Token:** Aplicativo cliente solicita identidades gerenciadas para o token de acesso dos recursos do Azure 📨
- **Base do Token:** Token baseado nas identidades gerenciadas para a entidade de serviço dos recursos do Azure 🔏
- **Recomendação:** Uso do `DefaultAzureCredential` 🛠️

## Implementação de Identidades Gerenciadas

### Tipos de Identidades Gerenciadas
- **Atribuída pelo Sistema:** Habilitada diretamente em um serviço do Azure ⚙️
- **Atribuída pelo Usuário:** Criada como recurso autônomo do Azure 🧩

### Características de Identidades Gerenciadas
| Característica      | Atribuída pelo Sistema               | Atribuída pelo Usuário                  |
|---------------------|--------------------------------------|-----------------------------------------|
| **Criação**         | Parte de um recurso do Azure         | Recurso independente do Azure           |
| **Ciclo de Vida**   | Compartilhado com o recurso pai      | Independente                            |
| **Compartilhamento**| Não compartilhável                   | Compartilhável                          |

### Cenário de Uso
- **Para criar aplicativos usando recursos do Azure:** 
  - Máquinas virtuais, Serviço de Aplicativos, Funções, Contêineres, Armazenamento e Serviço de Kubernetes 🖥️
- **Para acessar serviços que suportam autenticação do Microsoft Entra:** 
  - Seu aplicativo e Serviços do Azure 🗂️

### Fluxo de Autenticação de Identidades Gerenciadas
1. Solicitação ao ARM para habilitar identidade 📨
2. Criação de entidade de segurança no Microsoft Entra ID 🛠️
3. Configuração da identidade na VM 🖥️
4. Solicitação de token pelo código na VM 📥
5. Chamada ao Microsoft Entra ID para obter token de acesso 📡
6. Envio do token em chamada para serviços que suportam autenticação do Microsoft Entra ID 📊

### Configuração de Identidades Gerenciadas
- **Identidade Atribuída pelo Sistema:** Criação ou habilitação de VM com identidade gerenciada atribuída pelo sistema 🆔
- **Identidade Atribuída pelo Usuário:** Criação da identidade e associação à VM 🧩
- **SDKs Compatíveis:** .NET, Java, Node.js, Ruby: Suporte para gerenciamento de recursos habilitados com identidade gerenciada 📦

## Implementar a Configuração de Aplicativos do Azure

### Introdução
- **Serviço:** Gerenciar centralmente as configurações de aplicativos e os sinalizadores de recursos 🛠️
- **Desafio:** Programas na nuvem possuem muitos componentes distribuídos, o que pode levar a erros difíceis de resolver durante a implantação ☁️

### Benefícios da Configuração de Aplicativos do Azure
- **Serviço Gerenciado:** Configurável em minutos 🕒
- **Representações e Mapeamento de Chave Flexível:** Flexibilidade na gestão de chaves 🔑
- **Marcação com Etiquetas:** Facilita a organização 📋
- **Reprodução Pontual de Configurações:** Recuperação de configurações específicas 📅
- **Interface de Gerenciamento de Sinalizadores:** Interface dedicada para sinalizadores de recursos 💡
- **Comparação de Conjuntos de Configurações:** Comparação com definições personalizadas 📊
- **Segurança Aprimorada:** Identidades gerenciadas do Azure 🔒
- **Criptografia de Dados:** Criptografia em repouso e em trânsito 🔏
- **Integração Nativa:** Suporte a estruturas populares 🔄

### Cenários de Implementação
- **Centralização:** Gerenciamento e distribuição de dados de configuração hierárquicos para diferentes ambientes e geografias 🗂️
- **Alterações Dinâmicas:** Mudança das configurações de aplicativos sem reimplantar ou reiniciar o aplicativo 🔄
- **Controle de Recursos:** Gerenciamento da disponibilidade de recursos em tempo real 📡

### Adicionar um Repositório de Configuração de Aplicativos
| Linguagem / Estrutura          | Conexão                                                                                               |
|--------------------------------|-------------------------------------------------------------------------------------------------------|
| .NET Core e ASP.NET Core       | Provedor de configuração de aplicativos para .NET Core                                                |
| .NET Framework e ASP.NET       | Construtor de Configuração de Aplicativos para .NET                                                   |
| Java Spring                    | Cliente de configuração de aplicativos para Spring Cloud                                              |
| JavaScript/Node.js             | Cliente de configuração de Aplicativos para JavaScript                                                |
| Python                         | Cliente de Configuração de Aplicativo para Python                                                     |
| Outros                         | API REST de configuração de Aplicativos                                                               |

### Criar Pares de Chaves e Valores
- **Chaves:**
  - Nomeação de chaves simples ou hierárquica 🗂️
  - Uso de etiquetas para chaves 📋
  - Versão de valores de chaves não controlada automaticamente 📜
  - Consulta de valores de chaves identificados por chave e etiqueta (opcional) 🔍
- **Valores:**
  - Cadeias de caracteres Unicode 📝
  - Tipo de conteúdo definido pelo usuário (opcional) 🔣
  - Dados de configuração criptografados em repouso e em trânsito 🔏

### Gerenciar Recursos de Aplicativos
- **Conceitos básicos:**
  - Sinalizador de recursos: Variável binária (ativado ou desativado) ⚙️
  - Gerenciador de recursos: Pacote de aplicativos que processa sinalizadores de recursos 🛠️
  - Filtro: Regra para avaliar o estado de um sinalizador de recursos 🔍
- **Componentes:**
  - Aplicativo que usa sinalizadores de recursos 📱
  - Repositório separado para sinalizadores de recursos e seus estados 🗂️

### Declaração do Sinalizador de Recursos
- **Declaração:**
  - Nome e lista de filtros para avaliar o estado do recurso 📝
  - Lista de filtros percorrida até um determinar que o recurso deve ser habilitado 🔄
  - Suporte ao `appsettings.json` como fonte de configuração ⚙️
- **Repositório:**
  - Externalização dos sinalizadores de recursos usados no aplicativo 📤
  - Azure App Configuration como repositório centralizado 🗂️

### Proteger Dados de Configuração de Aplicativos
| Método                              | Descrição                                                                                                                                               |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Criptografia com Chaves Gerenciadas | Habilitar capacidade de chave gerenciada pelo cliente na Configuração de Aplicativos do Azure, Azure Key Vault com exclusão reversível e proteção de limpeza habilitadas, e uma chave RSA ou RSA-HSM no Key Vault 🔑|
| Permitir Uso de Chaves do Key Vault | Atribuir uma identidade gerenciada e conceder permissões de identidade na política de acesso do