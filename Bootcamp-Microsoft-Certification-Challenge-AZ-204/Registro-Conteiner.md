# Mapa Mental: Registro de Contêiner do Azure e Aplicativos de Contêiner do Azure

## 🌐 Registro de Contêiner do Azure (ACR)

### 📦 Uso do Serviço de ACR
- Desenvolvimento e Implantação
  - Utilização do ACR para desenvolvimento de contêineres e pipelines de implantação
  - Utilização das Tarefas do ACR para criação de imagens de contêiner

### 📌 Caso de Uso
- Obtenção de Imagens para Destinos de Implantação
  - Sistemas de orquestração escalonáveis
  - Serviços Azure para criação e execução de aplicativos em escala

### 📊 Camadas de Serviço do ACR
| Camada de Serviço | Descrição |
|-------------------|-----------|
| Basic             | Camada inicial com recursos básicos |
| Standard          | Camada intermediária com recursos adicionais |
| Premium           | Camada avançada com recursos completos |

### 🖼️ Imagens e Artefatos com Suporte
- Imagens Docker (Windows e Linux)
- Helm Chart
- Imagens OCI

### 🛠️ Tarefas do ACR
- Simplificação da criação, teste, push e implantação de imagens no Azure

### 💾 Funcionalidades de Armazenamento
| Funcionalidade                      | Descrição                                                                           |
|-------------------------------------|-------------------------------------------------------------------------------------|
| Criptografia em Inatividade         | Todas as imagens são criptografadas durante a inatividade                            |
| Armazenamento com Redundância       | Armazenamento geograficamente redundante                                             |
| Replicação Geográfica (Premium)     | Alta disponibilidade com replicação geográfica                                      |

### 🖥️ Criação e Gerenciamento de Contêineres com Tarefas
- Criação Baseada em Nuvem (Linux, Windows, ARM)
- Automatização de patches para contêineres Docker
- Cenários: Tarefa rápida, tarefas disparadas automaticamente, tarefas de várias etapas

## 🚀 Instâncias de Contêiner do Azure (ACI)

### 📋 Introdução
- Execução rápida e simples de contêineres no Azure
- Sem necessidade de gerenciar VMs

### ⚙️ Recursos das Instâncias de Contêiner do Azure
| Recurso                       | Descrição |
|-------------------------------|-----------|
| Tempo de Inicialização        | Contêineres iniciam em segundos |
| Conectividade de IP Público   | Exposição direta à Internet com IP público e FQDN |
| Segurança em Nível de Hipervisor | Isolamento comparável ao de VMs |
| Tamanhos Personalizados       | Especificações exatas de memória e núcleos da CPU |
| Armazenamento Persistente     | Suporte à montagem de compartilhamentos de Arquivos do Azure |
| Compatibilidade               | Suporte a contêineres Windows e Linux |
| Grupos Coagendados            | Agendamento de grupos compartilhando recursos |
| Implantação em Rede Virtual   | Implantação em redes virtuais |

### 🗂️ Grupos de Contêineres
- Compartilhamento de ciclos de vida, recursos, rede e volumes
- Implantação via modelo ARM ou Arquivo YAML
- Alocação de CPU, memória e GPUs somando solicitações das instâncias
- Cenários Comuns: Dividir tarefa funcional em múltiplas imagens de contêiner

### 🔄 Política de Reinicialização
- Configurações: Always, Never, Onfailure

## ⚙️ Definir Variáveis de Ambiente em Instâncias de Contêiner

### 📑 Exemplo de YAML
```yaml
az container create \ 
  --resource-group myResourceGroup \ 
  --name mycontainer2 \
  --image mcr.microsoft.com/azuredocs/aci-wordcount:latest \
  --restart-policy Onfailure \
  --environment-variables 'NumWords'='5' 'MinLength'='8'

# 🗂️ Montar um Compartilhamento de Arquivos do Azure em Instâncias de Contêiner

## 🌐 Visão Geral
- **Persistência de Estado:** Montagem de volumes externos

- **Limitações:** 
  - Apenas contêineres Linux
  - Execução como root
  - Suporte limitado a CIFS

## 📝 Implantação com YAML
- Implantação e montagem de volumes usando CLI do Azure e YAML

## 📦 Montagem de Vários Volumes
- Uso de modelo ARM ou YAML para montar múltiplos volumes

# 🛠️ Aplicativos de Contêiner do Azure

## 📋 Introdução
- Serviço de contêiner sem servidor para microserviços e dimensionamento automático

## 🚀 Funcionalidades dos Aplicativos de Contêiner do Azure

| Funcionalidade              | Descrição                                |
|-----------------------------|------------------------------------------|
| Dimensionamento Dinâmico    | Baseado em dimensionadores KEDA          |
| Ambiente de Aplicativos     | Limite seguro para grupos de contêineres |
| Desenvolvimento Independente| Atualização e dimensionamento de áreas de funcionalidade |
| Integração do Dapr          | Runtime de aplicativos distribuídos integrado |

## 🗂️ Organização de Contêineres
- Agrupamento em pods dentro de instantâneos de revisão
- Implementação do padrão sidecar
- Imagens de registros privados com credenciais configuradas

## 🔄 Gerenciamento de Revisões e Segredos

| Aspecto  | Descrição                                             |
|----------|-------------------------------------------------------|
| Revisões | Controle de versão com revisões, tráfego roteado e atualizações |
| Segredos | Definição de segredos no nível do aplicativo, referência por revisões |
