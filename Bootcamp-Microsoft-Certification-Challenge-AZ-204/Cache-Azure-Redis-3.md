# 🔧 Principais Tarefas com ConnectionMultiplexer
- Acessar um banco de dados Redis.
- Publicações/assinaturas do Redis.
- Manutenção ou monitoramento.

## 📜 Exemplo de Código para Acessar Banco de Dados Redis
```csharp
IDatabase db = redisConnection.GetDatabase();
bool wasSet = db.StringSet("favorite:flavor", "i-love-rocky-road");
string value = db.StringGet("favorite:flavor");
Console.WriteLine(value); // exibe: "i-love-rocky-road"
