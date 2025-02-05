# 🛠️ Acessar Cache Redis de um Cliente
Necessário: Nome do host, porta e chave de acesso.

- **Nome do Host:** Endereço público do cache (ex.: sportsresults.redis.cache.windows.net).
- **Chave de Acesso:** Senha do cache (primária e secundária).

# 💻 Interagir com o Cache do Azure para Redis usando .NET
## 🚀 StackExchange.Redis
### Criar uma Conexão
```csharp
using StackExchange.Redis;

var connectionString = "[nome-do-cache].redis.cache.windows.net:6380,password=[senha-aqui],ssl=True,abortConnect=False";
var redisConnection = ConnectionMultiplexer.Connect(connectionString);
