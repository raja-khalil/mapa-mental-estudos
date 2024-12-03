# Contextualização do Cenário na Área de Banco de Dados

## Cenário de Dados
- 📊 **Alto volume de dados**
    - Auxilia em tomadas de decisão mais específicas
    - Identificação de público-alvo, comportamento e padrões
    - Aumento do processamento e complexidade
    - Aumento do poder computacional e capacidade de armazenamento

### Paradigma do Big Data
- ⚡ **Velocidade**
- 🔄 **Variedade**
- 📚 **Volume**
- Grande quantidade de dados produzidos diariamente

## O que são Bancos de Dados
- 💾 Dados com fatos relacionados
- Armazenamento em um database
- Relacionamentos entre os dados
- Acesso aos dados por meio de API

## Sistema de Gerenciamento de Banco de Dados (SGBDs)
### Etapas
- 🛠 **Definição**
    - Tipos de dados, regras, diretrizes
- 🏗 **Construção**
    - Inserção de dados, mapeamento, estrutura, acesso aos dados
- 🔧 **Manipulação**
    - Recuperação de informação, geração de relatórios, updates, compilação
- 🔗 **Compartilhamento**
    - Acesso, simultaneidade, bloqueio e liberação de tabelas
- ♻ **Ciclo de Vida Longo**
    - Sem comprometimento da base
- 🛡 **Proteção**
    - Mal funcionamento do sistema, restrição de acesso a perfis

### Tipos de Dados e Metadados
- Metadados: Informações que fornecem uma descrição concisa dos dados contidos no BD

## Breve Histórico de SGBDs
### Surgimento
- 📅 **1960** – Gerenciamento de banco de dados
    - **Modelo Hierárquico**
        - Voltado para informação, busca registros e instâncias
    - **Modelo de Rede**
        - Links que são ponteiros entre os nós
        - Surgiu em 1964, precisa conhecer a estrutura física do BD
    - **IBM**
        - Objetivo de diminuir custo de pessoal
- 📅 **1970** – Modelo Relacional
- 📅 **1980** – Democratização do Acesso à Tecnologia
    - Saímos de 8 MB para terabytes
    - Feedback positivo
    - Sistemas destruídos
    - Desenvolvimento dos sistemas
- 📅 **1990** – Paradigma de Orientação a Objetivo
- 📅 **2002** – Surgimento do NoSQL

## Modelo de BD Relacional
- Criado por Ted Codd (1970)
- Teoria de Conjunto
- Estrutura mais generalista
- Transparência para o usuário
- IBM não foi a primeira empresa a trazer
- SQL
- DB Honeywell Information Systems Inc.
- Oracle 2 (1980)
- IBM SQL/DS (1980)
- Oracle 3 (1983)

## Modelo de Banco de Dados Relacional
### Componentes
- Álgebra Relacional
- Relações
- TAD para armazenamento
- Transparência

### Usuários
- Convencional
    - Manipulação dos dados
    - Recuperar informações
    - Alterar e extrair informações
    - Modificações duráveis
- Administrador BD
    - Definir tabelas e estruturas para os dados
    - Comandos traduzidos pelo processador LDD
- Outros Perfis
    - Design de BD

### Linguagens
- LDD (Linguagem de Definição de Dados)
    - Tradução
    - Mecanismos de execução
    - Gerenciador
- LMD (Linguagem de Manipulação de Dados)

### Armazenamento
- Storage e Buffer
- Gerenciador de Armazenamento
    - Movimentação de memória
- Gerenciador de Buffer
    - Troca de informações de memória

## SGBDs Mais Utilizados Pelo Mercado (2022)
- **Oracle PL**
    - Pioneiro
    - Maior performance
    - Usado por grandes corporações
    - Projeto para trabalhar em Grids
    - Alta escalabilidade, manutenção e segurança
- **MySQL**
    - Aplicação Web
    - Leve
    - Boa integração com PHP
    - Mantido pela Oracle
- **SQL Server**
    - Mantido pela Microsoft
    - Mais sofisticado
    - Integração com BI
    - Aplicações críticas
    - Integrado com Excel
    - Desconto para Instituições Educacionais
    - Soluções de gerenciamento
- **PostgreSQL**
    - Open Source
    - Robusto
    - Recursos clicos parciais (modelo de dados híbridos)
    - Primeira opção para programadores Python
- **MongoDB**
    - NoSQL
    - Orientado a documentos
    - Dados em blocos
    - Escalabilidade e performance
- **Redis**
    - NoSQL
    - Chave-valor
    - Popular e escalável
    - Dados acessados com mais regularidade
    - Simplicidade e performance
    - Roda na RAM – leitura rápida
- **ElasticSearch**
    - Relatório de log
    - Mecanismo de busca centralizado
    - Empresas relacionadas à inovação
    - Interface simples e RESTful
- **Access**
    - Simples
    - Ambiente Windows
    - Barato
    - Integra com Office
- **MariaDB**
    - Originado do MySQL
    - Método de busca mais otimizado
    - Mais performance para usuários
- **Cassandra**
    - Ambiente de gerenciamento de larga escala
    - Diferentes servidores
    - Desenvolvido pelo Facebook
    - Motor de busca
    - Open source
    - No ciclo

## A Era dos Dados e o Futuro da Modelagem
### Contexto Majoritário
- Modelo relacional usa maior parte do mercado
- Sistemas corporativos

### Pesquisa Científica
- Mapeamento de DNA
- Simulação de fala
- Grande volume de dados
- Não comumente usados pelas empresas
- Quantidades de dados e heterogeneidade
- Computação paralela e distribuída
- Nº de tarefas computacionais
- Poder computacional

### 4º Paradigma
- Paradigma científico
- Instrumentos e simulações que geram grande volume de dados
- Novo modelo baseado na análise e exploração de dados (e-Ciência)
- Modelo anterior: empírico (1º), teórico (2º) e computacional (3º)
- Ciência baseada em dados
- Inteligência artificial e estatística
- Identificação de padrões e extração de informações significativas
- ⚡ **Velocidade**
- 🔄 **Variedade**
- 📚 **Volumes**

### Requisitos
- Composição, execução, análise
- Abstração, reprodutividade, reutilização
- Escalabilidade

### Experimentos de Largas Escalas
- Paralelismo: Capacidade de processar operações concorrentes
- Big Data: Processamento paralelo de dados persistentes e particionados
- Cloud: Recursos de terceiros – Soluções de tecnologia como serviço
    - AWS
    - Azure

## HPC (High Performance Computing)
- Nós de processamento
- Sistemas de arquivos paralelos – sem persistência
- Modelos: MPI, OpenMP, OpenCL
- Acesso HFF5 e NetCDF

## Big Data
- Processamento e armazenamento: nós de processamento
- Sistema de arquivos paralelos – persistentes
- Modelos: MapReduce, Spark, SGBDs paralelos

## Novo Cenário e Novas Tecnologias
### Data Carrier
- Mercado de dados

### Engenheiro de Dados
- Desenho/construção
- Sustentação das soluções de dados
- Extração de dados de fontes heterogêneas
- Disponibilizar os dados para serem consumidos pelos analistas e cientistas

### Cientista de Dados
- Modelagem e reconhecimento de padrões/predição
- Busca responder perguntas atreladas ao contexto do negócio
- Busca insights através de técnicas de modelagem

### Analista de Dados
- Criação de dashboards
- Apresentação visual dos dados
- Busca entender o comportamento do negócio a partir dos dados
- Realiza o diagnóstico, identifica possíveis motivos para comportamentos e verifica métricas
- Ligado a regra de negócios

## Decisões Data-Driven
- Análise de dados
- Área estratégica
- Gerenciamento e Marketing
- Análise e interpretação antes de decidir
- Focado no consumidor

## Modelos NoSQL
- Documentos
- Wide-columns
- Key-Value
- Grafos
- Orientado à objetos
- Eventos de grande porte (ex.: Black Friday)
- **Not Only SQL**
    - **MongoDB**
        - Baixa curva de aprendizado
        - Baseado em JSON
        - Escalabilidade horizontal
        - Multi-plataforma
        - Transações ACID para multi-documentos
        - Consultas: Suporta JavaScript
    - **Cassandra**
        - Origem: Facebook
        - Open-Source: 2008
        - Performático
        - Descentralizado
        - Consultas: CQL
    - **Redis**
        - Orientado à Key-Value
        - Escrito em C em 2009
        - Compatível com outras linguagens
        - Performático
        - Suporte: String, list, maps, sets, JSON, Graphs
    - **Neo4j**
