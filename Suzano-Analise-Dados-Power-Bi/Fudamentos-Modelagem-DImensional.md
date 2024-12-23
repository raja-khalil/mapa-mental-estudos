### 🌟 Fundamentos de Modelagem Dimensional 🌟

#### 1. Conceito de Modelagem Dimensional
- Organiza dados em torno de:
  - **Fatos** 📊 (ex: vendas, pedidos)
  - **Dimensões** 🌐 (ex: tempo, local, produto)

#### 2. Estrutura do Modelo Dimensional
- **Tabelas Fato** 🗃️: Dados quantitativos e chaves para dimensões
- **Tabelas Dimensão** 📋: Atributos descritivos

#### 3. Esquemas Utilizados
- **Esquema Estrela** ⭐:
  - **Mapeamento com desnormalização**
  - Mínimo 3 tabelas dimensão
- **Esquema Floco de Neve** ❄️:
  - Normalização, junções entre dimensões
- **Esquema Constelação** 🌌:
  - Múltiplas estrelas, compartilhamento de dimensões

#### 4. Benefícios
- **Simplicidade** ✅
- **Performance** 🚀
- **Flexibilidade** 🔄

#### 5. Demandas
- **Performance** ⚡
- **Escalabilidade** 📈
- **Disponibilidade** 🌍

#### 6. Sistemas de Dados

##### Modelo Transacional (Tradicional) 🏢
- Suporte a operações do dia a dia
- Cenário otimizado para inserir, atualizar e deletar dados
- Mantém a integridade e consistência dos dados
- Utiliza Sistemas de Gerenciamento de Banco de Dados (SGBDs)

##### Modelo Dimensional (Analítico) 📊
- Permite redundância para facilitar consultas analíticas
- Estrutura ajustável conforme as necessidades
- Desenvolvido para realizar análises e relatórios
- Utiliza cubos de dados para permitir consultas multidimensionais

#### 7. Granularidade dos Dados
- **O que é**: Nível de detalhe dos dados na tabela fato
- **Como Definir**: 
  - Unidade Pequena (Grão ou Granularidade) 🔍
  - Maior Grão = Menos detalhes
  - Trade-off ⚖️ entre detalhe e complexidade

---

### 🌀 Slowly Changing Dimensions (SCD)
- **SCD-0** 🚫: 
  - Não há modificação (`TRUNCATE TABLE` - sem histórico)
- **SCD-1** 🔄: 
  - Atualização dos valores (`UPDATE` ou `INSERT` - sem rastreamento de mudanças)
- **SCD-2** 🕒: 
  - Preocupação com histórico, múltiplos métodos de rastrear mudanças
- **SCD-3** 🆕: 
  - Novos atributos para manter estado específico
- **SCD-4** 📚: 
  - Manutenção do histórico com tabela de histórico (mesma estrutura)
- **SCD-5** 🌀: 
  - Combinação de técnicas de SCD-1 e SCD-2
- **SCD-6** 💡: 
  - Junção dos tipos 1, 2 e 3

---

### 🔍 Análises com Bancos de Dados Relacionais
- **Sim**: Bancos de dados relacionais permitem realizar análises e responder perguntas de forma eficiente utilizando consultas SQL.

---

### 📊 Conclusão
A modelagem dimensional é essencial para a criação de Data Warehouses eficientes e de fácil entendimento, melhorando a capacidade de análise e tomada de decisão nas organizações.

Espero que estas anotações estejam claras e organizadas de acordo com as suas expectativas. Se precisar de mais informações ou de alguma adaptação, estou à disposição! 📊
