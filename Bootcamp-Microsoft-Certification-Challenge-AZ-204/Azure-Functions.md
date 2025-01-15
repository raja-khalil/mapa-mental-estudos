# Azure Functions 🧩

## Introdução 📘
- **Azure Functions**:
  - Serviço de solução sem servidor.
  - Infraestrutura de nuvem com recursos necessários para aplicativos.
  - Dimensionamento automático conforme demanda.

## Descobrir o Azure Functions 🕵️
- **Visão Geral**:
  - Ideal para tarefas como processamento de imagens, manutenção de arquivos e execução de tarefas agendadas.
  - Suporte a gatilhos e associações para simplificar a codificação.

- **Comparação entre Azure Functions e Aplicativos Lógicos**:
  
  | Aspecto               | Azure Functions                        | Aplicativos Lógicos do Azure                           |
  |-----------------------|----------------------------------------|--------------------------------------------------------|
  | **Desenvolvimento**   | Primeiro o código (Obrigatório)        | Primeiro o Designer (Declarativo)                      |
  | **Conectividade**     | Tipos internos de associação (+ custom) | Grande conjunto de conectores (+ custom)               |
  | **Ações**             | Cada atividade é uma função do Azure   | Grande conjunto de ações predefinidas                  |
  | **Monitoramento**     | Azure Application Insights             | Portal do Azure, logs do Azure Monitor                 |
  | **Gerenciamento**     | API REST, Visual Studio                | Portal do Azure, API REST, PowerShell, Visual Studio   |
  | **Contexto de Execução** | Local ou na nuvem                    | Suporte a cenário de run-anywhere                      |
  
- **Comparação entre Azure Functions e WebJobs**:
  
  | Aspecto                          | Azure Functions                     | WebJobs com o SDK do WebJobs      |
  |----------------------------------|-------------------------------------|-----------------------------------|
  | **Modelo sem servidor**          | Sim                                 | Não                               |
  | **Desenvolver e testar no navegador** | Sim                           | Não                               |
  | **Preço de pagamento por uso**   | Sim                                 | Não                               |
  | **Integração com Aplicativos Lógicos** | Sim                          | Não                               |
  | **Eventos de Gatilho**           | Variedade de opções (HTTP, timers, filas, etc.) | Menos opções                      |
  
- **Opções de Hospedagem do Azure Functions**:
  
  | Aspecto                          | Plano de Consumo               | Plano Premium                 | Plano Dedicado (Serviço de Aplicativo) |
  |----------------------------------|--------------------------------|--------------------------------|----------------------------------------|
  | **Dimensionamento**              | Automático, paga pelo uso       | Pré-aquecido, baseado na demanda | Manual, taxas regulares do Serviço de Aplicativos |
  | **Recursos**                     | Dinâmico, com base na demanda   | Instâncias mais poderosas       | Longa execução, integração a redes virtuais      |
  | **Tempo Limite**                 | Padrão 5 minutos, máximo 10    | Padrão 30 minutos, sem limite máximo | Padrão 30 minutos, sem limite máximo            |
  | **Requisitos de Armazenamento**  | Conta geral de armazenamento    | Conta geral de armazenamento    | Conta geral de armazenamento                     |

## Desenvolvimento do Azure Functions 💻

- **Arquitetura**:
  - Código em várias linguagens.
  - Configurações no arquivo `function.json`.
  - Define gatilhos, associações e outras configurações.

- **Ambientes de Desenvolvimento Locais**:
  - Use seu editor de código favorito para criar e testar funções localmente.
  - Conectar funções locais a serviços do Azure em tempo real e depurá-las.

- **Criar Gatilhos e Associações**:
  
  | Linguagem                  | Definição de Gatilhos e Associações           |
  |----------------------------|----------------------------------------------|
  | **C# class library**       | Identificação de métodos e parâmetros com atributos C# |
  | **Java**                   | Identificação de métodos e parâmetros com anotações Java |
  | **JavaScript/PowerShell/Python/TypeScript** | Atualização do esquema `function.json` |
  
  - Gatilhos fazem a função ser executada, uma função deve ter exatamente um gatilho.
  - Associações conectam recursos declarativamente à função.

- **Exemplo de Gatilho e Associação**:
  - Gravar uma nova linha no armazenamento de tabelas do Azure quando uma mensagem nova aparecer no Armazenamento de Filas do Azure.
  - Implementado usando um gatilho do Armazenamento de Filas do Azure e uma associação de saída do Armazenamento de Tabelas do Azure.

- **Conectar Funções a Serviços do Azure**:
  - Faça referência a informações de conexão por nome a partir do provedor de configuração.
  - Suporte para valores de conexão, inclusive aqueles baseados em identidade.

## Exercício: Criar um Projeto do Azure Function usando Visual Studio Code 🚀

- **Objetivos**:
  - Criar seu projeto local.
  - Executar a função localmente.
  - Entrar no Azure.
  - Publicar o projeto no Azure.
  - Executar a função no Azure.
  - Limpar os recursos.

- **Instalações Necessárias**:
  - Azure Functions Core Tools (GitHub).
  - Visual Studio Code:
    - Extensões:
      - C#
      - Azure Functions
  - .Net 8.0

- **Código de Exemplo**:

```csharp
using System.IO;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Azure.WebJobs;
using Microsoft.Azure.WebJobs.Extensions.Http;
using Microsoft.AspNetCore.Http;
using Microsoft.Extensions.Logging;
using Newtonsoft.Json;

public static class MyHttpFunction
{
    [FunctionName("MyHttpFunction")]
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function, "get", "post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        string name = req.Query["name"];

        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        dynamic data = JsonConvert.DeserializeObject(requestBody);
        name = name ?? data?.name;

        return name != null
            ? (ActionResult)new OkObjectResult($"Hello, {name}")
            : new BadRequestObjectResult("Please pass a name on the query string or in the request body");
    }
}
