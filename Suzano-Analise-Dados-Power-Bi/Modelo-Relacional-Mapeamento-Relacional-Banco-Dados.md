# Modelo Relacional e Mapeamento Relacional com Banco de Dados

## Conceito de Modelo Relacional: Tupla, Atributo e Relação
### Conceito
- Modelo Relacional
    - Coleção de Relações
- Tabela x Arquivos
- Entidade

### Domínio
- Tupla
    - Instância
    - Linha
- Atributo
- Relação
- Valores atômicos
- Grupos: específico de nomes

### Descrição de uma Relação
- Esquema relacional
    - Ai: Atributo
    - Domínio

## Conceito de Modelo Relacional: Cardinalidade, Domínio e Relação
### Cardinalidade
- Total de instâncias

### Domínio
- Coleção de relação
    - Domínio
    - Papel (Role)

### Características da Relação
- Ordenação de tuplas na relação
- Relação
- Arquivos
- Tabelas

## Conceito de Modelo Relacional: Conjunto de Tuplas
### Ordenação de Valores dentro da Tupla
- Lista de tuplas
    - Ordenação
- Conjunto de tuplas
    - Nível abstrato
        - set of (<attribute>, <value>)
    - Não pode ter duplicidade

## Conceito de Modelo Relacional: Valores Nulos
### Valores Nulos nas Tuplas
- Valor desconhecido
- Valor existente mas indisponível
- Atributo não se aplica
- Valor indefinido

### Significado de Relação
- O predicado
    - Formado por um ou mais verbos
    - Declaração sobre a ação do sujeito

## Lógica de Predicado dentro do Mundo de SGBDs
### Lógica de Predicados
- Afirmações declarativas
- Validade de argumentos

### Características da Relação
- Uppercase
    - Relações - Q, R, S
- Lowercase
    - Estado de Relação - q, r, s
- Letras
    - Tuplas - t, u, v
- Nome Atributo
    - Papel

## Constraints de Modelo Relacional
### Dados do Contexto de Banco de Dados
#### Constraints
- Composição do mini-mundo
    - Relações
    - Constraints
- Categorizar
    - Inherent Model-based Constraints
        - Características das relações
        - DDL
    - Schema-based Constraints
    - Application-based Constraints

### Dependência de Dados
- Dependências funcionais
- Dependências multivaloradas
- Processo de normalização

## Constraints Baseado no Esquema de Banco de Dados
### Constraints de Domínio
- Constraints relacionado ao atributo
    - Time
    - Strings
    - Integer
    - Timestamp
    - Date
    - Float
- Relação é um conjunto de tuplas
- Ideia de repetição não existe
- Não pode ter duas linhas idênticas
- SK = subconjuntos de atributos
- Chave apresenta identificação daquela tupla
- Chave e superchave
- Chave candidata

### Constraint de Chaves
- Uniqueness constraints
- Chave primária e candidata

## SGBDs Esquemas Relacionais
### Esquema Relacional
- SGBD é um subconjunto de relações
- Estado de SGBD relacional
- Restrições de integridade
    - Status do SGBD
    - DDL - Data Definition Language

### Definição
- DDL - Data Definition Language
- DML - Data Manipulation Language
- DCL - Data Control Language
- DQL - Data Query Language

### Integridade
- Constraints de integridade
- Constraints de domínio, chave, not null
- Integridade de entidade
- Integridade referencial

## Integridade Referencial de Entidade e Chave Estrangeira
### Integridade
- Chave Primária ≠NULL
    - Consistência entre entidades
    - Integridade de entidade
    - Integridade referencial

### Chave Estrangeira
- Regras
    - Domínio dos Atributos de FK = Domínio dos Atributos da PK
    - Relação de referência com relação referenciada

### Outras Constraints
- Constraints - semântica
    - Depende do contexto do banco de dados
- Restrições de Estado
- Restrições de Transição

## Mapeando ER - Relacional
### Mapeando
- Logical database design
    - Design lógico do projeto
    - Mapeamento do Modelo de dados
    - ER ou EER para relacional

### Algoritmo de Mapeamento
- Referência
    - Atributos de valor único (single-values)
    - PK - Primary Key & Unique Key
    - Constraints de Entidade e Referencial

### Entidades Fortes (regulares)
- Relação
- PK
- Unique Constraint
- FK - Foreign Key

### Strong Entity Mapping
- Relação de entidade - Entity Relation

### Algoritmo de Mapeamento
- Entidades Fracas (dependentes)

### Mapeamento de Entidade Fraca
- Entidade fraca identificada pela Chave (PK e FK)

## Mapeamento de Relacionamento Binário 1:1
### Algoritmo de Mapeamento
- Abordagem
    - Foreign Key
    - Merge dos relacionamentos
    - Cross-reference

### Relacionamento Binário 1:1
- Participação total
- Abordagem FK
- Merge
    - 2 entidades em 1 entidade
        - Relacionamento Total
- Cross-reference
    - M:N normalmente ocorre
    - Gera um nova entidade
    - Difícil acontecer com 1:1

## Mapeamento de Relacionamento Binário 1:N
### Abordagem
- Foreign Key
- Relationship Relation

## Mapeamento de Relacionamento Binário N:M
### Abordagem
- Relationship Relation

## Mapeando Atributos para o Modelo Relacional
### Atributos Compostos
- Abordagem
    - Componentes simples

### Atributos Multivalorados
- Abordagem
    - Relationship Relation

## Mapeamento de Relacionamento N-ários
### Relacionamento N-ário
- Abordagem
    - Relationship Relation

### Resumo
- Modelo ER
    - Entidade
    - Relação 1:1 ou 1:N
    - Relação M:N
    - Relacionamento N-ário
- Modelo relacional
    - Relação (Entidade)
    - FK ou relação
    - Relação ou 2 FKs
    - Relação ou N FKs

## Mapeando Componentes do ERR
### Subclasse
- Especialização
    - Única tabela
    - Múltiplas tabelas

### Superclasse e Subclasses
- Opções
    - Múltiplas relações - Sub/superclasse
    - Múltiplas relações - Subclasse
    - Relação única - 1 tipo de atributo
    - Relação única - múltiplos tipos de atributos

### Relação Única - 1 tipo de atributo

### Relação Única - Múltiplos Atributos Type

### Herança Múltipla
- Mesmo atributo chave
- Mapeamento: Opções anteriores

### Union Type
- Superclasses
- Tipos de Entidades diferentes
- Algoritmo de Mapeamento
    - Chave Substituta
        - Chave primária
        - Chave Estrangeira
