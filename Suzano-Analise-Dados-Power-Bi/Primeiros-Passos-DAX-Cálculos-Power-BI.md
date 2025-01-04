# 🌟 Primeiros Passos com DAX e Cálculos com Power BI

## 🔍 O que é DAX?
- **DAX (Data Analysis Expressions)**: Linguagem usada para cálculos complexos e agregações de dados no Power BI, Power Pivot e Analysis Services.

## 🧠 Medidas DAX
- **Medidas Rápidas**: Criadas via interface gráfica, sem necessidade de código DAX.
- **Medidas com DAX**: Criadas manualmente com fórmulas DAX.
- **Exemplos**:
  - `AVERAGE`: Média aritmética.
  - `AVERAGEX`: Média por expressão.

## 📝 Colunas Calculadas
- **Definição**: Valores calculados para cada linha de uma tabela.
- **Métodos de Criação**:
  1. Na Origem (ex.: consulta SQL)
  2. Power Query
  3. DAX no Power BI Desktop
- **Exemplo**: `[New Column] = [Column1] + [Column2]`
- **Considerações**: Aumenta o espaço no arquivo `.pbix`.

## 📊 Estrutura da DAX
- **Sintaxe Básica**: Nome da Medida = Função de Agregação + Tabela Referência.
  - Exemplo: `Total Sales = SUM(Sales[SalesAmount])`

## 🔄 Funções Padrão vs. Iteradoras
- **Funções Padrão**: `SUM`, `COUNT`, `MIN`
- **Funções Iteradoras**: `SUMX`, `COUNTX`, `MINX`
- **Vantagens das Iteradoras**: Melhor desempenho e menor espaço.

## ⚡ Criando Medidas Rápidas no Power BI Desktop
1. **Acesso**: Clique com o botão direito na tabela e selecione "Nova Medida Rápida".
2. **Configuração**: Selecione tipo de medida e configure os parâmetros.
3. **Aplicação**: Medida criada automaticamente.

## 🔍 Comparando os Tipos de Medidas
| Características        | Medidas Padrão              | Medidas Rápidas               |
|------------------------|-----------------------------|-------------------------------|
| **Criação**            | Código DAX manual           | Interface gráfica             |
| **Complexidade**       | Cálculos avançados          | Cálculos comuns simplificados |
| **Flexibilidade**      | Altamente flexível          | Limitada a medidas predefinidas|
| **Contexto de Uso**    | Usuários avançados          | Iniciantes ou cálculos rápidos |

## 🔍 Entendendo o Contexto com DAX
- **Impacto do Contexto**: Filtros, relações entre tabelas e fórmulas afetam medidas.
- **Tipos de Contextos**:
  1. **Linha**: Baseado na linha atual.
  2. **Várias Linhas**: Interação de cálculos em várias linhas.
  3. **Consulta**: Subconjunto de dados recuperados.
  4. **Filtro**: Restrições de filtro aplicadas aos dados.

## 🔧 Funções Relacionadas ao Contexto
| Função              | Descrição                                                                                 | Exemplo                                               |
|---------------------|-------------------------------------------------------------------------------------------|-------------------------------------------------------|
| **ALL**             | Remove todos os filtros de uma tabela ou coluna específica.                               | `ALL(Sales)`                                          |
| **ALLCROSSFILTERED**| Remove filtros cruzados entre duas ou mais tabelas.                                       | `ALLCROSSFILTERED(Sales)`                             |
| **ALLEXCEPT**       | Remove todos os filtros em uma tabela, exceto os especificados.                           | `ALLEXCEPT(Sales, Sales[Region])`                     |
| **ALLNOBLANKROW**   | Remove todos os filtros de uma tabela, exceto a linha em branco.                          | `ALLNOBLANKROW(Sales)`                                |
| **ALLSELECTED**     | Retorna todas as linhas no contexto atual filtrado por seleções do usuário.               | `ALLSELECTED(Sales)`                                  |
| **CALCULATE**       | Avalia uma expressão em um contexto modificado pelos filtros especificados.               | `CALCULATE(SUM(Sales[SalesAmount]), Sales[Region] = "West")` |
| **CALCULATETABLE**  | Avalia uma expressão de tabela em um contexto modificado pelos filtros especificados.     | `CALCULATETABLE(Sales, Sales[Region] = "West")`       |
| **EARLIER**         | Retorna o valor de uma coluna no contexto anterior a uma operação de iteração.            | `CALCULATE(SUM(Sales[SalesAmount]), EARLIER(Sales[SalesAmount]))` |
| **EARLIEST**        | Similar ao `EARLIER`, mas retorna o valor mais antigo no contexto de iteração.            | `CALCULATE(SUM(Sales[SalesAmount]), EARLIEST(Sales[SalesAmount]))` |
| **FILTER**          | Retorna uma tabela que representa um subconjunto de outra tabela filtrada por uma condição.| `FILTER(Sales, Sales[SalesAmount] > 100)`             |
| **KEEPFILTERS**     | Mantém os filtros que já foram aplicados, mesmo se o `CALCULATE` tentar removê-los.       | `CALCULATE(SUM(Sales[SalesAmount]), KEEPFILTERS(Sales[Region] = "West"))` |
| **LOOKUPVALUE**     | Retorna o valor de uma coluna em uma tabela que corresponde aos critérios de pesquisa.     | `LOOKUPVALUE(Sales[SalesAmount], Sales[ProductID], 123)` |
| **REMOVEFILTER**    | Remove filtros de uma coluna ou tabela específica.                                         | `REMOVEFILTER(Sales[Region])`                         |
| **SELECTEDVALUE**   | Retorna o valor de uma coluna se apenas um valor estiver no contexto atual; caso contrário, retorna um valor alternativo. | `SELECTEDVALUE(Sales[Region], "No Region Selected")`  |

## 🔧 Explorando as Possibilidades com Filtros
- **Verificação das Fórmulas**: Sintaxe DAX, tabelas envolvidas, filtros e relacionamentos.
- **Complexidade**: Contextos complexos dificultam a solução de erros.

## 🌈 Exploração das Funções DAX e Tipos
Existem cerca de 250 funções DAX no Power BI, categorizadas em diferentes grupos:

- **Novas Funções do DAX**
- **Funções Financeiras**: `PMT`
- **Funções Informativas**: `ISBLANK`
- **Funções Lógicas**: `IF`
- **Funções Matemáticas e Trigonométricas**: `SUM`, `ROUND`
- **Funções de Agregação**: `SUMX`
- **Funções de Data e Hora**: `TODAY`, `DATEDIFF`
- **Funções de Filtro**: `FILTER`

## 🚀 Outros Recursos do DAX

### Modificação de Relacionamentos
- **`USERELATIONSHIP`**: Especifica qual relacionamento usar quando existem múltiplos.
  - Exemplo: `CALCULATE(SUM(Sales[SalesAmount]), USERELATIONSHIP(Sales[Date], Dates[Date]))`

---

Estas anotações fornecem uma visão geral completa para iniciar com cálculos e análises no Power BI, abrangendo desde os conceitos básicos de DAX até o entendimento dos contextos e filtros que afetam as medidas. Espero que este mapa mental seja útil para você!
