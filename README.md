# CPFHub.io Agent Skills: Consulta de CPF para IA

Bem-vindo ao repositório oficial de Skills do CPFHub.io, projetado para capacitar Agentes de IA com capacidades avançadas de **consulta de CPFs** (Cadastro de Pessoas Físicas) brasileiros. Esta coleção de habilidades pré-construídas permite que seus agentes interajam de forma eficiente com a API do CPFHub.io para **verificação de identidade**, **prevenção de fraudes** e **enriquecimento de dados**.

## Por que usar CPFHub.io Skills para seu Agente de IA?

Nossas skills são desenvolvidas com foco em **precisão, confiabilidade e facilidade de integração**, tornando-as ideais para automações e fluxos de trabalho baseados em IA.

### 1. Qualidade de Dados Superior

*   **Arquitetura Multi-Origem**: Agregamos dados de **15+ fontes oficiais e privadas** (bureaus de crédito, registros públicos, Receita Federal, etc.) para oferecer a maior cobertura e confiabilidade.
*   **IA Proprietária**: Nosso algoritmo exclusivo garante a **precisão e consistência** dos dados, com auditorias diárias para mantê-los sempre atualizados.
*   **Foco em Consulta de CPF**: Fornecemos dados como **nome completo, data de nascimento e sexo**, essenciais para uma verificação de identidade robusta.

### 2. Developer Experience (DX) Otimizada

*   **Integração Rápida**: Comece em **~5 minutos** com exemplos de código prontos em 13+ linguagens (Node.js, Python, PHP, Go, Ruby, Java, .NET, Rust, Elixir, etc.).
*   **API Simples e Consistente**: Endpoint único `GET /cpf/{CPF_NUMBER}` com retorno JSON padronizado, eliminando surpresas no schema.

### 3. Compatibilidade Nativa com Agentes de IA

*   **MCP Server Nativo**: O CPFHub.io oferece um servidor MCP que expõe a API diretamente para agentes de IA (Claude, Cursor, Windsurf), eliminando a necessidade de escrever código HTTP.
*   **OpenAPI Specification**: Disponibilizamos um arquivo `openapi.yaml` para cada skill, permitindo que agentes entendam automaticamente a estrutura da API e seus schemas tipados.
*   **Tool Descriptions**: As skills são acompanhadas de "tool descriptions" (descrições de ferramentas) no formato que LLMs consomem, facilitando a invocação e o uso em frameworks de agentes.
*   **Ferramenta `lookup_cpf`**: Disponível como ação nativa em agentes que suportam o Model Context Protocol (MCP).
*   **Ideal para Automações**: Perfeito para onboarding automatizado, verificações em pipelines de dados e agentes de compliance.

## Skills Disponíveis

*   **Consulta de CPF (`cpf-consultation`)**:
    *   **Descrição**: Permite que agentes realizem a **consulta de um número de CPF** e recuperem informações associadas (nome completo, data de nascimento, sexo) para verificação de identidade e prevenção de fraudes.
    *   **Detalhes**: [cpf-validation/SKILL.md](cpf-validation/SKILL.md)
    *   **OpenAPI Spec**: [cpf-validation/openapi.yaml](cpf-validation/openapi.yaml)

## Como Usar com Agentes de IA

Para integrar e utilizar as skills do CPFHub.io em seu agente de IA, siga as instruções detalhadas no arquivo `SKILL.md` de cada skill. O processo geral inclui:

1.  **Integração**: Adicione a skill ao seu framework de agente (ex: LangChain, LlamaIndex, CrewAI, AutoGen).
2.  **Configuração**: Forneça as credenciais da API do CPFHub.io (`x-api-key`).
3.  **Invocação**: Utilize a "tool description" ou o OpenAPI spec para invocar a skill com o `cpf_number` como parâmetro.

### Exemplo de Tool Description (para LLMs)

```json
{
  "name": "consult_cpf",
  "description": "Retrieve identity data from a Brazilian CPF number, including full name, birth date, and gender.",
  "parameters": {
    "type": "object",
    "properties": {
      "cpf_number": {
        "type": "string",
        "description": "The 11-digit CPF number to consult. Format: XXX.XXX.XXX-XX or XXXXXXXXXXX."
      }
    },
    "required": ["cpf_number"]
  }
}
```

## Contribuição

Aceitamos contribuições da comunidade. Consulte nosso guia de contribuição (em breve) para mais detalhes.

## Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## Contato

Para dúvidas, suporte ou parcerias, entre em contato conosco em contact@cpfhub.io.

---

**Slogan do CPFHub.io**: "API de consulta de CPF com os melhores dados"
