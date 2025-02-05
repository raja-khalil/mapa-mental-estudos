# 🌐 Contas de Armazenamento no Azure

## Nomeação da Conta
- 🔠 Nome exclusivo
    - 3 a 24 caracteres
    - Não pode repetir
    - Exemplo: storage-account + recurso + projeto + complemento

## Acesso Global
- 🌍 Fornece acesso à internet em todo o mundo

## Redundância de Armazenamento
- 📦 Determina durabilidade e disponibilidade dos dados
- Fonte: Microsoft

### Configurações de Redundância
| 🔄 Configuração de Redundância | 🏢 Implantação | 🛡️ Durabilidade |
| --- | --- | --- |
| **LRS** (Local) | Datacenter individual | 99.999999999% |
| **ZRS** (Zona) | 3 zonas de disponibilidade | 99.9999999999% |
| **GRS** (Geográfica) | Datacenter em região primária e secundária | 99.99999999999999% |
| **GZRS** (Zona Geográfica) | 3 zonas na primária e 1 datacenter na secundária | 99.99999999999999% |

## Serviços de Armazenamento
| 🛠️ Serviço | 📄 Descrição |
| --- | --- |
| **Blob** | Dados não estruturados (texto, binário) |
| **Disco** | Discos para VMs, aplicativos |
| **Fila** | Mensagens até 64KB |
| **Arquivos** | Compartilhamento via SMB |
| **Tabelas** | Dados estruturados não relacionais |

## Pontos de Extremidade Públicas
| 🌐 Serviço | 🔗 Endpoint |
| --- | --- |
| **Blob** | `https://<storage-account-name>.blob.core.windows.net` |
| **Data Lake Gen2** | `https://<storage-account-name>.dfs.core.windows.net` |
| **Arquivos** | `https://<storage-account-name>.file.core.windows.net` |
| **Filas** | `https://<storage-account-name>.queue.core.windows.net` |
| **Tabelas** | `https://<storage-account-name>.table.core.windows.net` |

## Camadas de Acesso
| 🎚️ Camada | 📖 Descrição | 📅 Requisitos |
| --- | --- | --- |
| **Frequente** | Dados acessados frequentemente | - |
| **Esporádico** | Dados acessados raramente (30 dias) | 30 dias |
| **Frio** | Dados acessados raramente (90 dias) | 90 dias |
| **Arquivo Morto** | Dados acessados raramente (180 dias) | 180 dias |

## Migrações para o Azure
- 🚚 **Plataforma Unificada**
    - Ferramentas integradas/autônomas

### Opções de Migração
| 🚛 Opção | 📄 Descrição |
| --- | --- |
| **Data Box** | Migração física (80TB) |
| **Data Box Disk** | Versão menor do Data Box |
| **Data Box Heavy** | Versão maior do Data Box |

## Gerenciamento de Arquivos
| 💼 Ferramenta | 📄 Descrição |
| --- | --- |
| **AzCopy** | Linha de comando para copiar blobs/arquivos |
| **Gerenciador do Azure** | Interface gráfica (Windows, Mac, Linux) |
| **Sincronização de Arquivos** | Sincronização bidirecional, liberação de espaço |

## Referências
- **Microsoft Azure Documentation**: [Azure Storage Overview](https://docs.microsoft.com/en-us/azure/storage/)
