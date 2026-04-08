using Microsoft.AspNetCore.Mvc.Testing;
using Microsoft.OpenApi.Models;
using Microsoft.OpenApi.Readers;
using Xunit;

public class SwaggerDocumentationTests : IClassFixture<WebApplicationFactory<Program>>
{
    private readonly WebApplicationFactory<Program> _factory;

    public SwaggerDocumentationTests(WebApplicationFactory<Program> _factory)
    {
        this._factory = _factory;
    }

    [Fact]
    public async Task SwaggerDoc_AllSchemas_ShouldHaveSummaryAndExample()
    {
        // 1. Arrange: Obtém o JSON do Swagger
        var client = _factory.CreateClient();
        var response = await client.GetAsync("/swagger/v1/swagger.json");
        response.EnsureSuccessStatusCode();
        
        var stream = await response.Content.ReadAsStreamAsync();
        var openApiDocument = new OpenApiStreamReader().Read(stream, out var diagnostic);

        // 2. Act & Assert: Valida cada schema (DTO)
        var errors = new List<string>();

        foreach (var schema in openApiDocument.Components.Schemas)
        {
            var schemaName = schema.Key;
            var properties = schema.Value.Properties;

            foreach (var prop in properties)
            {
                // Valida Summary (Description)
                if (string.IsNullOrWhiteSpace(prop.Value.Description))
                {
                    errors.Add($"[Summary Ausente] DTO: {schemaName}, Propriedade: {prop.Key}");
                }

                // Valida Example
                if (prop.Value.Example == null)
                {
                    errors.Add($"[Example Ausente] DTO: {schemaName}, Propriedade: {prop.Key}");
                }
            }
        }

        // Se houver erros, o teste falha listando todos os campos pendentes
        Assert.Empty(errors);
    }
}
