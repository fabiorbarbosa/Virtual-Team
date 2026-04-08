Quero que você implemente suporte a OpenAPI YAML em uma library .NET já existente, sem remover o suporte atual a JSON do Swagger.

Contexto:
- A library já é usada por aplicações ASP.NET Core com Swagger configurado via Swashbuckle.
- A estrutura atual já gera documentos Swagger em JSON.
- Preciso adicionar suporte para expor também o mesmo contrato em YAML.
- O projeto deve continuar compatível com aplicações ASP.NET Core 3.1+.
- Se necessário, ajuste o target framework da library para suportar o código ASP.NET Core corretamente, preservando o uso compartilhado da biblioteca.

Objetivo:
- Criar os arquivos e classes necessários para expor endpoints YAML equivalentes aos endpoints JSON já existentes.
- Considerar múltiplos documentos/versionamentos por contexto no formato:
  - /doc/v1/clientes/swagger.json
  - /doc/v2/clientes/swagger.json
  - /doc/v1/produtos/swagger.json
  - /doc/v2/produtos/swagger.json
  - /doc/v3/produtos/swagger.json
- O endpoint YAML correspondente deve seguir exatamente o mesmo padrão:
  - /doc/v1/clientes/swagger.yaml
  - /doc/v2/clientes/swagger.yaml
  - /doc/v1/produtos/swagger.yaml
  - /doc/v2/produtos/swagger.yaml
  - /doc/v3/produtos/swagger.yaml

O que preciso que você faça:
1. Inspecione a estrutura atual do projeto e identifique onde hoje o Swagger é configurado.
2. Crie as extensões necessárias para expor YAML a partir do documento OpenAPI já gerado pelo Swashbuckle.
3. Se necessário, crie ou ajuste uma extensão como `UseSwaggerYaml()` ou `UseSwaggerContractFormats()`.
4. Crie os arquivos necessários dentro da library, seguindo o padrão já existente do projeto.
5. Se houver necessidade de arquivo JS para incluir um link ou botão de download de YAML no Swagger UI, crie esse arquivo também.
6. Preserve compatibilidade com a configuração atual e evite quebrar os endpoints JSON existentes.
7. Se precisar ajustar `.csproj`, faça isso com a menor mudança possível.
8. Não remova nem reestruture partes não relacionadas.
9. Ao final, mostre:
   - quais arquivos foram criados/alterados
   - como registrar a solução na aplicação consumidora
   - quais URLs finais passam a existir
10. Se houver ambiguidade sobre como os documentos Swagger são nomeados internamente, primeiro descubra isso no código antes de implementar.

Critérios de implementação:
- Reutilizar ao máximo a configuração atual.
- Seguir as convenções existentes do projeto.
- Criar código pronto para produção, sem pseudocódigo.
- Evitar duplicação de lógica.
- Não assumir nomes internos dos documentos Swagger sem verificar no código.
- Se houver múltiplos contextos/versionamentos, mapear corretamente `version + context` para o documento OpenAPI correspondente.

Entregue a implementação completa no próprio projeto, com as alterações aplicadas.
