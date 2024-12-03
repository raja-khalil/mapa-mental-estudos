# Abordagem de SGBD versus Abordagem Tradicional

## Abordagem de BDs
### Abordagem Tradicional
- Via programação
- Problemas no gerenciamento
    - Devido à redundância
    - Esforço repetitivo
    - Estrutura

### Abordagem SGBDs
- Consulta ao sistema
- Representação de informações
- **Abstração**
    - Isolamento problema-dados
    - Determina estrutura
    - Manipulação
- **Isolamento**
- **Múltiplas Visões**
    - Acesso diferenciado
- **Auto-descrição**
    - Descrição específica e concisa
    - Gerenciamento otimizado
- **Compartilhamento**
    - Compartilhar com grupos distintos
    - Controle de concorrência
- **Transação Multiuser**
    - Multiusuário

### Comparação
- Múltiplas visões
- Compartilhamento e processamento de transações

## Natureza Auto-descritiva da Abordagem de Banco de Dados
### Auto-descrição
- Descrição de mim mesmo
- Descrição da estrutura e regras bem definidas
- DB Schema é a estrutura bem definida dos dados sem inserção dos dados
- **Modelos e Schemas**
    - Modelo relacional
    - NoSQL possuem uma autodescrição dentro do arquivo

### Abordagem Tradicional
- Estrutura dentro do programa

### Catálogo
- Atrelado à autodescrição do SGBD

## Isolamento Program/data e Abstração
### Isolamento de Dados e Programa
- **Isolamento**
- **Abstração**
    - Generalização
    - Transparência

### Abordagem Tradicional
- Estrutura rígida, qualquer mudança reflete na aplicação

### SGBD Relacional
- Partes separadas
    - Estrutura de dados
    - File processing
- Dados com tabelas e relacionamentos
- Não mexe na aplicação
- **Program-Data Independence**

## Suporte a Múltiplas Visões dos Dados
### Múltiplas Visões
- **Table Views**
    - Educação
    - Financeiro
    - Marketing
    - Vendas
    - Planejamento

### Formação das Views com Diversas Tabelas
- Pode ser somente leitura (read-only)
- Dados podem ser irrelevantes ou restritos
- Perspectivas distintas do mesmo contexto

## Compartilhamento de Dados e Processamento de Transações Multiusuários
### Integração para Prover Acesso ao Mesmo Tempo
- **Controle de Concorrência (Concurrency Control)**
- **Manutenção**
- **OLTP** (Processamento de Transações em Tempo Real)
    - Acesso simultâneo
        - Insert
        - Delete
        - Update
    - Performance
    - Processamento cliente-servidor - API
    - Software intermediário
    - Software de gerenciamento de transações
    - App multiuser
    - Gerenciador de transações concorrentes

### Processo
- Unidade de trabalho
- Cálculo lógico
- Acesso ao SGBD

### Isolamento
- Execução sem interferência

### Atomicidade
- Execução sem interferência
- Executa tudo ou nada

### Transaction-driven
- Operacional
- Processamento de dados
- Data mining, análises e decisão

### OLTP (Ambiente operacional)
- Ambiente de banco de dados - ELT process
- OLAP (Ambiente informativo)
- Ambiente de warehouse

## Abordagem em Banco de Dados - Quais são os Atores em Banco de Dados
### Atores
#### BD Simples
- Acesso único - poucas pessoas interessadas em acessar as informações

#### Big Organizations
- Grande quantidade de pessoas interessadas em acessar o sistema
    - **Design** - necessidade de modelar
    - **Usabilidade** - como ele vai funcionar
    - **Manutenção**

### Atores do Dia a Dia
- **Designer de Banco de Dados**
    - Identificar dados e requisitos
    - Representação e estrutura
    - Fase preliminar
    - Entender o contexto em que está inserido os dados
    - Modelagem
    - Projeto conceitual
- **Administrador - DBA**
    - Gerencia recursos
        - Base de dados
        - SGBD
        - Software adicionais
    - Orquestração
    - Autorização de acesso
- **Usuário Final**
    - Interessados em consumir os resultados finais
    - Categorizados
    - Acesso via Query
        - Update
        - Reports
    - API para consultas
    - **Classificação**
        - **Casuais**
        - **Ingênuos**
            - Canned Transactions
                - Capsulado em linguagem de programação
                - API gráfica
        - **Sofisticados**
            - Noção ou conhecimento prévio do sistema
                - Cientistas
                - Engenheiros
                - Entendem como funcionam as queries SQL
        - **Standalone**
            - BD pessoal
                - Acesso e consulta
                - Só ele acessa essa base de dados
- **Quem Programa**
    - Engenheiro de Software
        - Análise de sistemas
        - Desenvolvimento da aplicação
        - Teste e documentação da aplicação

## Workers em Background - Banco de Dados
### Não Diretamente Ligado ao SGBD
#### Atores
- **Designer do Sistema**
    - Implementação dos módulos e interface
- **Pessoal de Operação e Manutenção**
    - Ambiente de hardware e software do SGBD
- **Implementação do Sistema**
    - Implementação dos módulos e interface
- **Desenvolvedores de Ferramentas**
    - Ferramentas opcionais para diversos fins
        - Segurança
        - Performance
        - Análise

## Vantagens de Utilizar a Abordagem de SGBDs
### Controle de Redundância
- Evita
    - Desperdício de recursos
    - Redundância de informações
    - Inconsistência
    - Updates desnecessários
- Cada um acessa o SGBD

### Restrição de Acesso
- Sistema de Gerenciamento
    - Update
    - Restricted view
    - Read-only
- Quem faz é o DBA
- Subsistema Secundário
    - Assinatura digital
    - Certificação

### Storage - Prove Persistência
- **Impedance Mismatch Problem**
    - Falta de match - falta de estrutura entre o sistema e SGBD
    - Estruturas diferentes entre eles
        - Normalmente na programação, paradigma ao objeto
        - SGBD é modelo relacional
    - Problemas
        - Definição de dados
        - Recuperação de informações

### Estrutura de Armazenamento
- Normalmente é estruturada - em árvores
- Intuitiva
- Técnicas para recuperação mais rápida, maior recorrência
    - **Caching**
        - Liberar rapidamente
    - **Buffering**
        - Inserindo informações
    - **Indexação**
        - Tornando acesso mais rápido

### Backup e Recovery
- Backup - réplica dos BD em local diferente
- Recovery - falha por desastres - estado inválido de BD

### Interface Multi-user
- Acesso concorrente de informações

### Representação de Relações Mais Complexas
- Variedade de dados inter-relacionados

### Integridade dos Dados
- Integridade de referência
- **Tipos**
    - Regras de domínio
    - Asserções
    - Integridade Referencial
    - Gatilhos
    - Dependência Funcionais
- Representa a regra de negócio

### Inferência com Ações com Regras - Triggers
- Regra declarativa

### Storage - Prove Estrutura

### Backup e Recovery

## Ganhos em Utilizar SGBDs
### Padronização
- Tipo de dados
- Display
- Relatórios
- Boas práticas
- Estrutura

### Redução de Tempo no Desenvolvimento da Aplicação
- Features do app descontinuadas: retrieval

### Flexibilidade
- **Etapas**
    - Requisitos
    - Desenvolvimento
    - Testes
    - Aprimoramento
- Modificação

### Disponibilidade de Informações Atualizadas
- Update imediato

### Economia de Escala
- Operacional e Gerenciamento
- Baixo custo operacional e de gerenciamento

## Quando Não Usar SGBDs
### Custo
- Investimento inicial
- Generalidade na definição e processamento
- Segurança, controle de concorrência, Recovery, funções de integridade

### Não se Usa
- Acesso unário
- **BD Simples**
    - Zero mudanças
    - Arquivo .CSV
- Embedded Systems
- Real-time

### Sistemas que Não Usam
- Sistema de Rede Comutação
- Sistema de Geolocalização
- Autocad

## Modelagem de Dados para Banco de Dados
### Introdução à Modelagem de Dados
#### Por que Modelar?
- Compressão do sistema
- Construção
    - Planta Baixa
- Desenvolvimento
    - Protótipos
- Eletrônicos
    - Esquema de circuitos
- Otimizar tempo de implementação

### Modelagem
- Representação
- Modelo
- Referência
- A modelagem é uma representação
- Pode ser:
    - Software
    -