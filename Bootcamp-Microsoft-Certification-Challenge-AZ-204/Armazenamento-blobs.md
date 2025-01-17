# Armazenamento de Blobs do Azure 🗄️

## Introdução 🌟
- Solução de armazenamento de objetos na nuvem da Microsoft
- Otimizado para grandes quantidades de dados não estruturados
- Usos:
  - Fornecimento de imagens e documentos 🌐
  - Armazenamento distribuído de arquivos 📁
  - Streaming de áudio e vídeo 🎵🎥
  - Gravação de arquivos de log 📝
  - Backup e restauração 🔄
  - Análise de dados 📊

## Explorar o Armazenamento de Blobs do Azure 🔍
### Discos 💿
- Discos persistentes para VMs IaaS do Azure
- Opções de disco do Armazenamento Premium

### Contas de Armazenamento 📦
| Categoria    | Descrição                                                                                 |
|--------------|-------------------------------------------------------------------------------------------|
| **Arquivos** | Compartilhamentos gerenciados na nuvem, Acesso SMB/REST, Sincronização com locais         |
| **Blobs**    | Armazenamento escalável REST, Blobs de bloco (sequencial), página (aleatória), acréscimo  |
| **Tabelas**  | Armazenamento NoSQL escalável com dimensionamento dinâmico                                |
| **Filas**    | Filas confiáveis em escala para serviços de nuvem, Desacoplar e dimensionar componentes   |

### Sistema de Armazenamento Distribuído Unificado 🌐
- Durabilidade
- Criptografia em repouso 🔐
- Replicação consistente
- Tolerância a falhas ⚠️
- Balanceamento de carga

## Contas de Armazenamento 📂
| Categoria   | Tipo de Conta               | Serviços Compatíveis                                |
|-------------|-----------------------------|----------------------------------------------------|
| **Standard**| Uso geral v2 Standard       | Blob, fila, armazenamento de tabela, arquivos       |
| **Premium** | Blobs de bloco Premium      | Armazenamento de blob                               |
| **Premium** | Blobs de bloco Premium      | Blobs de página somente                             |

## Camadas de Acesso para Dados de Blob de Blocos 📉
| Camada      | Descrição                                                                                   |
|-------------|---------------------------------------------------------------------------------------------|
| **Frequente** | Acesso frequente a objetos na conta de armazenamento                                      |
| **Esporádico** | Dados acessados com pouca frequência (mín. 30 dias)                                       |
| **Frio**      | Dados acessados raramente (mín. 90 dias)                                                   |
| **Arquivo**   | Dados que podem tolerar várias horas de latência (mín. 180 dias)                           |

## Recursos de Segurança do Armazenamento do Azure 🛡️
### Funcionalidades de Segurança 🔒
- Microsoft Entra ID e RBAC compatíveis
- Proteção de dados em trânsito
- Assinatura de Acesso Compartilhado para acesso delegado

### Criptografia para Dados em Repouso 🔑
- Habilitada por padrão, não desativável
- Chave gerenciada pela Microsoft ou próprias chaves
  - Chave gerenciada pelo cliente 🔐
  - Chave fornecida pelo cliente 🔑

## Hospedagem de Site Estático no Armazenamento do Azure 🌐
### Recursos ⚙️
- Conteúdo estático a partir do contêiner $web
- Arquiteturas sem servidor com Azure Functions
- Domínio personalizado
- Ativado na seção Site Estático

### Limitações 🚫
- Não é possível configurar cabeçalhos
- AuthN e AuthZ não compatíveis

## Gerenciar o Ciclo de Vida do Armazenamento de Blobs do Azure 🔄
### Introdução 📈
- Crescimento exponencial de dados na nuvem
- Necessidade de acesso diminui com o tempo
- Organização com base na frequência de acesso e tempo de retenção

### Níveis de Acesso 🗂️
| Camada      | Descrição                                                                                   |
|-------------|---------------------------------------------------------------------------------------------|
| **Frequente** | Dados acessados frequentemente                                                           |
| **Esporádico** | Dados acessados com pouca frequência                                                     |
| **Frio**      | Dados raramente acessados com recuperação rápida                                          |
| **Arquivo**   | Dados raramente acessados com requisitos de latência flexíveis                            |

### Políticas de Ciclo de Vida 📜
- Transferência de blobs para armazenamento mais esporádico
- Exclusão de blobs no final do ciclo de vida
- Regras diárias de execução
- Aplicação de regras a contêineres ou subconjuntos de blobs

## Trabalhar com o Armazenamento de Blobs do Azure 🛠️
### Bibliotecas de Cliente (.NET) 📚
- **BlobClient**: Representa um blob específico
- **BlobContainerClient**: Representa um contêiner de blob
- **BlobServiceClient**: Representa a conta de armazenamento
- **AppendBlobClient**: Representa um blob de acréscimo
- **BlockBlobClient**: Representa um blob de blocos

### Criar um Objeto Cliente 🛠️
- URI de ponto de extremidade passado ao criar um objeto cliente
- Construído manualmente ou consultado em tempo de execução
- Uso da DefaultAzureCredential para autenticação

### Gerenciar Propriedades e Metadados de Contêiner (.NET) 📋
- Recuperar propriedades: GetProperties, GetPropertiesAsync
- Definir metadados: SetMetadata, SetMetadataAsync

### Propriedades e Metadados de Recursos de Blob (REST) 🖥️
- Cabeçalho de metadados: x-ms-meta-name:string-value
- Recuperar: GET/HEAD https://myaccount.blob.core.windows.net/mycontainer?restype=container
- Definir: PUT https://myaccount.blob.core.windows.net/mycontainer?restype=container
