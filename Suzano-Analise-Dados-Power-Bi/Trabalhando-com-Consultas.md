# Trabalhando com Consultas

## Primeiros Passos com SQL
### Introdução ao SQL
- 📚 **Linguagem para**
    - Manipulação de dados
    - Execução de operações
        - DBAs, BI, Devs, DS
    - Surgiu em 1970
- 🎯 **Objetivo**
    - Modificação de dados e estrutura
    - Adicionar, remover ou atualizar linhas
    - Recuperação de um subconjunto de info do BD
    - OLTP ou OTAP
- 📊 **Classificação**
    - DDL - Data Definition Language
    - DML - Data Manipulation Language
    - DCL - Data Control Language
    - DQL - Data Query Language

### Sublinguagens: Classificação de SQL - DDL
- 🛠️ **Comandos**
    - Create | Drop | Alter
    - Insert | Update | Delete
    - Rename | Truncate | Merge
- 👤 **Usuário**
- 📐 **Esquema**
- 📄 **Statements**
- 🔍 **Indexing**

### Continuando com as Classificações (DML, DCL, e DQL)
- 🛡️ **DCL**
    - Usado por DBAs
        - Grant | Revoke
- 🔍 **DQL**
    - Select
- 📝 **Statement**
    - Estado do BD
        - Comando/Instrução
        - Reconhecido pelo BD
        - Retorno: registro de dados
    - 📜 **Cláusula SQL**
        - Comandos
            - Função: Instrução
            - Algumas são obrigatórias
        - **Quais são**
            - Select
            - From
            - Where
            - Order By
            - Group By
            - Having
        - **Termos - SQL**
            - Identificador
            - Operador
            - Constante
            - Expressão

### Tipos de Dados no MySQL
- 🔤 **Caracteres**
    - Fixo - 255 bytes
    - Variável - 65,535 bytes
- 📄 **Text Types**
    - Mediumtext - 16,777,215 bytes
    - Longtext - 4,294,967,295 caracteres
- 🔡 **Conjunto de Caracteres**
    - Alfabeto, Português, Inglês
    - SHOW CHARACTER SET
    - Maxlen > 1 = multibyte character set
- 📊 **Dados Numéricos**
    - < 64 KB
- 🗓️ **Dados Temporais**
    - Date, Datetime, Timestamp, Year, Time

### Constraints: Especificando Restrições no SQL
- ❌ **NOT NULL**
- 🔑 **PK e SK**
- 🛠️ **Default**
    - Valor padrão
- ✅ **Check**
    - Domain
- 🗑️ **Delete**
    - Comportamento
- 🔑 **Primary Key**
    - Definida no CREATE TABLE
- 🌟 **UNIQUE**
- 🔗 **Referential Triggered Action**

### Queries / Inserção com SQL
- 🔎 **Queries**
    - Comportamento
        - Multiset - not set
        - Duplicações (Redundâncias)
        - DISTINCT
        - Mapping
            - Projeção de Atributos
        - **Operadores**
            - =, <, ≤, >, ≥, <> (SQL)
            - +, -, *, / (Operadores básicos)
            - AND, OR, XOR, NOT (Operadores booleanos)
            - TRUE, FALSE (Operadores lógicos)
    - 🔧 **DML**
        - Subconjunto do SQL
        - Mais utilizado
        - **Comandos**
            - INSERT, DELETE, UPDATE

### Nomes, Aliasing e Variação de Tuplas - SQL
- 📛 **Nomes de Atributos**
    - Identificando a Tabela
- 👥 **Quando usar Aliasing**
    - Quando há ambiguidade
    - Esclarecimento
    - Diferenciar atributos
    - Renomear atributos
        - Nomenclatura diferente
        - Referência múltiplas

### When Good Statements Go Bad
- ⚠️ **Problemas**
    - PK e FK inexistente
    - Valores violados
    - Conversão inválida de datas

### MySQL & PostgreSQL
- 🐘 **PostgreSQL**
    - Otimizado para aplicações completas
    - Grande volume de dados/informações críticas
        - E-commerce / Médio porte
- 🐬 **MySQL**
    - Agilidade e versatilidade
    - Operações mais simples
    - Processamento e tempo curto de resposta
        - Site / Fórum / Portal
- 🔄 **Ponderação**
    - Precisa de Rollback? MySQL não possui Enterprise
    - Precisa de Agilidade? Facilidade de utilização
    - Operação mais simplificada - MySQL

## Criando Queries com Funções e Cláusulas de Agrupamento
### ORDER BY: Cláusula de Ordenação com SQL
- 📜 **Recuperação dos dados é ordenada?**
    - Os dados não vêm ordenados e precisam de ORDER BY
- 🗂️ **ORDER BY**
    - Cláusula SQL
    - Ordenação por coluna
    - Expressão baseada em dados
    - De um valor
    - Pode ser ascendente (ASC) ou descendente (DESC)
- 📜 **WHERE Statement**
    - Definição formal
        - Critério a ser considerado na query ao recuperar a informação. A tupla (linha ou instância) deve conter a condição definida em WHERE

### Ordenação com SQL - Utilizando Expressões
- 📋 **Com dados derivados**
    - Ordenação dos dados para trazer consistência e sequência
    - Alias para fornecer nomenclatura adequada a dados derivados ou armazenados

### Como Ordenar os Registros
- 🔢 **Operadores numéricos**
- 🏷️ **Nomes dos atributos**
- De um atributo
- DESC ou ASC

### Funções de Agregação com SQL
- 📊 **Funções de Agrupamento**
    - Agregar
    - Aglutinar
    - Agrupar
- 📋 **Agrupamento de Registros**
    - COUNT: Registro
    - SUM: Somatório
    - MIN: Valor mínimo - Atributo
    - MAX: Valor máximo - Atributo
    - AVERAGE: Média de valor - Atributo

### GROUP BY: Cláusula de Agrupamento com SQL
- 📋 **Agrupamento de Registros**
    - Atributos de relacionamentos
    - Grupos de valores

### Entendendo o HAVING Statement
- 📜 **SELECT**
    - Seleciona tabela e atributos
- 📋 **GROUP BY**
    - Grupo de valores
- 🔍 **HAVING**
    - Filtragem dos grupos
    - Condição sobre a informação sobre o grupo
    - Preferência de execução das cláusulas

## Agrupamento de Registros e Tabelas com JOIN Statement
### CASE Statement
- 🔄 **Troca de um valor**
- Condição para troca
- Mapeamento de valores de correspondência
- Condição
    - WHEN, THEN

### Agrupamento com CASE Statement
- 📋 **Agrupando CASE Statement**

### O Caso Zero/Null Trick
- 🧩 **Filtro - Valores distintos**
- SELECT QUERY
- WHERE, não precisa usar WHERE
- Combinar operadores com CASE
    - MAX, AVG, MIN
    - AND, OR, NOT
    - COUNT

### Entendendo Queries de Múltiplas Tabelas com JOINs
- ✖️ **A junção vem um produto cartesiano**
    - 📋 **Cross JOIN Statement**
        - Vai ter repetição
    - Quando coloca atributo de condição de junção acaba com repetição
        - 📜 **Comando para Cross**
            - SELECT
            - FROM
            - JOIN
        - 📜 **Comando para junção**
            - INNER JOIN
                - SELECT
                - FROM
                - JOIN
                - ON

### Queries com INNER JOIN
- 🔄 **O tipo mais utilizado**
- Registro em duas ou mais tabelas
- Se não combinar vai ter falha de linhas excluídas
- 📋 **INNER JOIN**
    - Mais comum dos JOINs
    - Linhas não correspondentes excluídas
    - Atributos de junção
    - Mescla tabelas
    - 1+ atributos de junção
    - 2+ tabelas
- 📜 **USING** é usado para atributos com o mesmo nome

### Agrupamento com Mais de Duas Tabelas e JOIN
- 📋 **3 ou + tabelas com JOIN**
    - 3 tabelas
    - 2 tipos de JOINs
    - 2 subcláusulas

### A Ordem Importa em Queries JOIN?
- SGBD interpreta e escolhe a sequência de comando
- SGBD escolhe um ponto de partida
- 📜 **Tem como especificar a ordem para o SGBD?**
    - STRAIGHT_JOIN
    - FORCE ORDER

### Nested (Subqueries