# Coleta de Dados - Power BI

## 1. Power BI
- Ferramenta da Microsoft para análise de dados e criação de relatórios interativos.

## 2. Coleta de Dados
### Fontes de Dados
- Bancos de Dados
- Arquivos Excel
- Serviços Online (SharePoint, Google Analytics)
- APIs

### Tipos de Arquivos
- CSV (Comma-Separated Values)
- TXT
- Excel
- JSON
- PDF
- APIs
- URL
- Azure
- Cosmo DB
- Outros Comumente Usados (XML, OData, Parquet)

### Origem dos Dados
- Local
- OneDrive (pessoal ou empresa)
- SharePoint
- Sistemas e APIs

### Conexão
- Interface intuitiva do Power BI
- Consultas em M (Power Query) ou DAX (Data Analysis Expressions)

## 3. Transformação de Dados com Power Query
### Power Query Editor
- Limpar e transformar dados

### Passos Comuns
- Manipular Dados
- Remover Erros
- Combinar Resultados
- Padronização de Dados
- ETL (Extração, Transformação e Carregamento)

## 4. Arquivos CSV
### Formato
- Arquivos tabulares separados por vírgulas

### Importação no Power BI
- Facilmente importados através da opção "Obter Dados"

## 5. Conectando ao MySQL Local Utilizando o Power BI Desktop
### Instalação do Conector
### Configuração da Conexão
- Informar servidor e banco de dados

### Quando Utilizar SQL?
- Seleção de Dados de Base
- Carregamento Parcial
- Junção de Tabelas

## 6. Observações Sobre SQL
- Teste sua Consulta
- Utilize Outro Meio para Teste (MySQL Workbench, SQL Server Management Studio)
- Visualização no Power Query

## 7. Modelagem de Dados
### Relacionamentos
### Medidas e Colunas Calculadas
- Utilização de DAX

## 8. Visualização de Dados
### Dashboards
- Interativos

### Gráficos e Tabelas
- Diversas visualizações disponíveis

## 9. Como Lidar com Problemas de Desempenho no Power BI
### Issues Comuns
- Gargalo de Acesso
- Tempo de Execução
- Lentidão no Carregamento
- Erros de Importação
- Falhas de Disco, Servidor e Outros

### Soluções Propostas
- Sobragem de Consultas
- Transformações Controladas pela Ferramenta
- Execução no Servidor (SQL)

### Motivos para Implementação
- Garantir Transformações no Servidor de Origem
- Mais Eficiência em Atualização de Dados
- Compatibilidade Automática com Modos de Armazenamento

## 10. Melhorando a Performance
- Processar Dados na Origem
- Utilizar SQL Nativo
- Separar Data e Hora do Mesmo Campo
- Manter a Base a Ser Utilizada

## 11. Fluxo de Dados no Power BI
1. Coleta de Dados
2. Transformação (Power Query)
3. Criação do Dashboard
4. Publicação do Relatório
5. Inserção em um Dashboard

## 12. Dataset de Origem
### Mudança Durante o Projeto
### Atualização do Local da Dataset

## 13. Substituição da Origem do Dataset
### Substituição da Origem Local para OneDrive
### Uso Direto de Origem do OneDrive

## 14. Seções de Obtenção de Dados
- Tudo
- Arquivo
- Banco de Dados
- Microsoft Fabric
- Power Platform
- Azure
- Serviços Online
- Outros

## 15. Conclusão
- Power BI facilita a coleta, transformação, modelagem e visualização de dados.
- Uso do Power Query é essencial para preparação de dados.
- A conexão ao MySQL local utilizando SQL é eficaz para seleção, carregamento parcial e junção de dados.
- Melhorar desempenho através da sobragem de consultas, transformações controladas pela ferramenta e execução no servidor.
- Seguir o fluxo de dados garante insights valiosos para a tomada de decisões informadas.
