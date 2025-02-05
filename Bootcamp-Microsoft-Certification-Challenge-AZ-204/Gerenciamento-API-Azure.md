# 🌐 Gerenciamento de API Azure

## 📚 Introdução
- **Propósito**: Publicar APIs para parceiros externos e desenvolvedores internos.
- **Benefícios**: Integração eficiente e segura dos dados e serviços.

## 🗂️ Conceitos Principais
### 🛠️ Papel do Gerenciamento de API
- Funcionalidades essenciais para um programa de API bem-sucedido.
- Envolvimento do desenvolvedor, insights de negócios, análise, segurança e proteção.

### 🔧 Componentes do Sistema
- **Gateway de API**
- **Portal do Azure**
- **Portal do Desenvolvedor**

### 📦 Produtos
- Exibem as APIs para os desenvolvedores.

### 👥 Grupos
- Gerenciam a visibilidade dos produtos para os desenvolvedores.

### 👨‍💻 Desenvolvedores
- Representam as contas de usuário em uma instância de serviço de Gerenciamento de API.

### 📜 Políticas
- Permitem alterações no comportamento da API através de configurações no portal do Azure.

### 🖥️ Portal do Desenvolvedor
- Aprender sobre a API.
- Ver e chamar operações.
- Assinar produtos.

## 🌉 Exploração de Gateways de API
### 🔄 Função do Gateway de API
- Proxy reverso, encaminhamento de solicitações.
- Aplicação de políticas e coleta de telemetria.
- Autenticação, terminação SSL e limitação de taxa.

### ⚠️ Problemas Sem um Gateway
- Complexidade do código do cliente.
- Acoplamento entre cliente e back-end.
- Várias chamadas de serviço para uma única operação.
- Necessidade de protocolos amigáveis ao cliente.

### 🛠️ Padrões de Design
- **Roteamento de Gateway**: Proxy reverso para rotear solicitações.
- **Agregação de Gateway**: Agrega várias solicitações em uma única.
- **Descarregamento de Gateway**: Transfere funcionalidades para o gateway.

## 🛡️ Exploração de Políticas de Gerenciamento de API
### 📜 Papel das Políticas
- Alteram o comportamento da API.
- Aplicadas no gateway, podem mudar solicitações de entrada e respostas de saída.

### ⚙️ Configuração de Política
- Documento XML com instruções de entrada e saída.
- Divididas em: entrada, back-end, saída e erro.

### 🔄 Tipos de Políticas
- **Inbound (Entrada)**
- **Backend (Backend)**
- **Outbound (Saída)**

### 🔧 Políticas Específicas
- **Fluxo de Controle**: Condicional com base em expressão booleana.
- **Encaminhar Solicitação**: Encaminhamento para o serviço de back-end.
- **Limite de Simultaneidade**: Limitação do número de execuções.
- **Registro no Hub de Eventos**: Envio de mensagens para um centro de evento.
- **Resposta Fictícia**: Abortar e retornar resposta simulada.
- **Repetir**: Reexecuta até que a condição seja atendida.

## 🔒 Proteção de APIs
### 🔑 Uso de Assinaturas
- **Escopo de Chave de Assinatura**:
    - **Todas as APIs**: Aplica-se a todas as APIs acessíveis por meio de gateway.
    - **Única API**: Aplicável a uma única API importada.
    - **Produto**: Coleção de uma ou mais APIs com diferentes regras de acesso.

### 🗝️ Aplicativos Chamando APIs
- Solicitações precisam incluir a chave.
- Chaves de assinatura podem ser regeneradas.
- Assinaturas possuem duas chaves: primária e secundária.

### 🛡️ Uso de Certificados
- **Autenticação do Cliente**:
    - **AC (Autoridade de Certificação)**: Certificados assinados por uma AC específica.
    - **Impressão Digital**: Certificados com uma impressão digital especificada.
    - **Assunto**: Certificados com uma entidade especificada.
    - **Data de Validade**: Certificados não expirados.

- **Verificação de Certificados**:
    - Quem emitiu o certificado.
    - Se o certificado é proveniente do parceiro.

- **Políticas de Autorização de Certificado**:
    - Verificação da impressão digital.
    - Verificação do emissor e da entidade.

## 📝 Conclusão
- **Gerenciamento de API Azure**: Ferramenta poderosa para publicar, proteger e gerenciar APIs de forma eficaz.
- **Componentes**: Gateways, políticas e proteções garantem a segurança e eficiência.

---

Este mapa mental deve facilitar a compreensão do Gerenciamento de API Azure de maneira visual e organizada. 📊
