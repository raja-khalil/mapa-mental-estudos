# 🧠 Mapa Mental: Plataforma de Identidade da Microsoft

## 🌐 Introdução
- **Plataforma de Identidade da Microsoft**: Conjunto de ferramentas que inclui serviços de autenticação, bibliotecas de código aberto e ferramentas de gerenciamento de aplicativos.
- **Objetivo**: Criar aplicativos nos quais os usuários possam entrar usando identidades da Microsoft ou contas de redes sociais.

## 🔍 Explorar a Plataforma de Identidade

### 📚 Componentes Principais
- **Registro de Aplicativo**
- **SDK do Cliente**
- **Autenticação e Ponto de Extremidade de Token**
- **Audiência de Destino**

## 🏢 Explorar as Entidades de Serviço

### 🔑 Tipos de Entidades
- **Locatário Único**: Acessível somente em seu locatário.
- **Multilocatário**: Acessível em outros locatários.
- **Objeto de Aplicativo**
- **Objetivo da Entidade de Serviço**: Aplicativo, Identidade Gerenciada, Herdado

### 🔄 Relação entre Objetos de Aplicativo e Entidades de Serviço
- **Relação 1:1** com aplicativo de software
- **Relação 1:N** com objeto de entidade de serviço correspondente

## 🛡️ Descobrir Permissões e Consentimento

### ✅ Tipos de Permissões
- **Permissões Delegadas**: Para aplicativos com usuário conectado.
- **Permissões de Aplicativo**: Para aplicativos sem usuário conectado.

### 📝 Tipos de Consentimento
- **Consentimento do Usuário Estático**
- **Consentimento Incremental e Dinâmico do Usuário**
- **Consentimento do Administrador**

## 🔒 Descobrir o Acesso Condicional

### 🔐 Métodos de Proteção
- **Autenticação Multifator**
- **Intune**: Somente dispositivos inscritos.
- **Restrição de Locais**: Locais de usuário e intervalos de IP.

### ⚙️ Impacto nos Aplicativos
- Aplicativos executando o fluxo em nome de.
- Aplicativos acessando vários serviços/recursos.
- Aplicativos de página única usando MSAL.js.
- Aplicativos Web que chamam um recurso.

## 🛠️ Implementar a Autenticação com MSAL

### 📖 Introdução
- **MSAL**: Biblioteca que permite adquirir tokens da plataforma de identidade da Microsoft para autenticar usuários e acessar APIs Web seguras.

### 📊 Explorar a Biblioteca MSAL

#### 🚀 Recursos
- **Microsoft Graph**
- **Suporte a Várias Arquiteturas**: .NET, JavaScript, Java, Python, Android, iOS

### 📂 Cenários de Aplicativos
- **Aplicativos Web**
- **APIs da Web**
- **Aplicativos de Página Única (JavaScript)**
- **Aplicativos Nativos e Móveis**
- **Daemons e Aplicativos do Lado do Servidor**

### 🔁 Fluxos de Autenticação
- **Código de Autorização**: Tokens em nome do usuário.
- **Credenciais do Cliente**: Sem interação do usuário.
- **On-Behalf-Of**: Chama API de serviço que chama Microsoft Graph.
- **Implícita**: Aplicativos baseados em navegador.
- **Código do Dispositivo**: Login em dispositivo usando outro dispositivo com navegador.
- **Windows Integrado**: Token de acesso automático em computadores Windows.
- **Nome de Usuário/Senha**: Login com nome de usuário e senha.

### 🔧 Inicializar Aplicativos Cliente
- **Construtores Recomendados**: PublicClientApplicationBuilder, ConfidentialClientApplicationBuilder
- **Modificadores**:
  - `.WithAuthority()`
  - `.WithTenantId(String tenantId)`
  - `.WithClientId(String clientId)`
  - `.WithRedirectUri(String redirectUri)`
  - `.WithComponent(String component)`
  - `.WithDebugLoggingCallback()`
  - `.WithLogging()`
  - `.WithTelemetry(TelemetryCallback telemetryCallback)`

## 🔗 Implementar Assinaturas de Acesso Compartilhado

### 📜 Introdução
- **SAS**: URI assinado que aponta para recursos de armazenamento com um token contendo parâmetros de consulta.

### 🔎 Descobrir SAS

#### 🔑 Tipos de SAS
- **SAS de Delegação do Usuário**
- **SAS de Serviço**
- **SAS de Conta**

#### 🛡️ Práticas Recomendadas
- Usar HTTPS.
- Preferir SAS de delegação de usuário.
- Definir tempo de expiração curto.
- Aplicar privilégios mínimos necessários.
- Avaliar se SAS é a solução correta.

#### 📂 Usar SAS para Acessar Dados
- **Componentes**:
  - `sp=r`
  - `st=202-01-20T11:42:32Z`
  - `se=2020-01-20T19:42:32Z`
  - `sv=2019-02-02`
  - `sr=b`
  - `sig=<…>`

#### ⚙️ Quando Usar SAS
- **Serviço de Proxy Front-End**: Autentica e valida regras de negócio.
- **Serviço Leve**: Autentica e gera SAS para acesso direto ao armazenamento.

### 📂 Explorar Políticas de Acesso Armazenadas
- **Controle Adicional**: Nível de serviço no lado do servidor.
- **Definir ACL**: Criar ou modificar política de acesso.

## 🌟 Explorar o Microsoft Graph

### 🚀 Introdução
- **Microsoft Graph**: Gateway para dados e inteligência em Microsoft 365.
- **Modelo de Programação Unificado**: Acesso a dados do Microsoft 365, Windows e Enterprise Mobility + Security.

### 🔗 Consultar Microsoft Graph Usando REST

#### 📂 Estrutura REST
- `{HTTP method} https://graph.microsoft.com/{version}/{resource}?{query-parameters}`
- **Métodos HTTP**: GET, POST, PATCH, PUT, DELETE
- **Versões Suportadas**: v1.0, beta
- **Recursos**: Entidades ou tipos complexos com propriedades
- **Parâmetros de Consulta**: OData ou personalização

### 💻 Consultar Microsoft Graph Usando SDKs

#### 🚀 Ferramentas
- **Microsoft.Graph**: Ferramenta de mapeamento relacional de objetos.
- **Microsoft.Graph.Core**: Biblioteca principal para chamadas ao Microsoft Graph.

#### 🔑 Autenticação
- **Integração com MSAL**: Provedores compatíveis com diversos fluxos de autenticação.
- **Wrapper MSAL**: Auxiliares de autenticação, tokens automáticos, redução de complexidade.

### 💡 Melhores Práticas para Microsoft Graph

#### 🔐 Autenticação
- **Cabeçalho de Autorização HTTP**: Token do Portador.
- **Construtor de Cliente do Grafo**: Biblioteca cliente do Microsoft Graph.

#### 🛡️ Consentimento e Autorização
- **Mínimo de Privilégios**
- **Tipo de Permissão Correta**
- **Experiência do Usuário e Administradores**

#### ⚙️ Lidar com Respostas
- **Paginação**
- **Enumerações Evolutivas**

#### 📂 Armazenar Dados Localmente
- **Somente se Necessário**
- **Implementar Políticas de Retenção e Exclusão**

---
Espero que esse mapa mental ajude na organização e compreensão das informações de forma mais clara e eficiente! Se precisar de ajustes ou mais alguma coisa, estou aqui para ajudar.
