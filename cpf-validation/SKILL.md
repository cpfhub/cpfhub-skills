# CPF Validation Skill for AI Agents

This skill provides functionality to validate Brazilian CPF (Cadastro de Pessoas Físicas) numbers and retrieve associated data.

## Description

The CPF Validation Skill allows AI agents to verify the validity of a given CPF number and, if valid, fetch public information associated with it. This is crucial for applications requiring identity verification, fraud prevention, or data enrichment in the Brazilian context.

## Parameters

### Input

*   **`cpf_number`** (string, required): The 11-digit CPF number to be validated and queried. Format: `XXX.XXX.XXX-XX` or `XXXXXXXXXXX`.

### Output

*   **`is_valid`** (boolean): `true` if the CPF number is syntactically valid, `false` otherwise.
*   **`status`** (string): A brief status message (e.g., "CPF válido", "CPF inválido", "Dados encontrados", "Dados não encontrados").
*   **`data`** (object, optional): An object containing public data associated with the CPF, if available and valid. This may include:
    *   `name` (string): Full name of the individual.
    *   `status_receita` (string): Status of the CPF with the Receita Federal (e.g., "Regular", "Pendente de Regularização").
    *   `birth_date` (string): Date of birth (format: `YYYY-MM-DD`).
    *   `address` (string): Partial address information.
*   **`error`** (string, optional): An error message if the operation failed (e.g., "Formato de CPF inválido", "Erro na API").

## Casos de Uso Comuns

Esta skill pode ser utilizada em uma variedade de cenários, incluindo:

*   **Onboarding de Clientes**: Validar CPFs de novos usuários durante o processo de cadastro para garantir a autenticidade e evitar fraudes.
*   **Prevenção a Fraudes**: Verificar a situação cadastral de um CPF antes de aprovar transações financeiras, concessão de crédito ou acesso a serviços sensíveis.
*   **Enriquecimento de Dados**: Complementar perfis de clientes com informações públicas associadas ao CPF, como nome e data de nascimento, para personalização e segmentação.
*   **Automação de Processos Legais/Administrativos**: Automatizar a verificação de CPFs em processos que exigem conformidade regulatória ou validação de documentos.
*   **Atendimento ao Cliente**: Agilizar o atendimento ao cliente, permitindo que agentes de IA confirmem a identidade do usuário através do CPF de forma rápida e segura.

## Examples of Use

### Example 1: Basic CPF Validation

```json
{
  "skill_name": "cpf_validation",
  "action": "validate_cpf",
  "parameters": {
    "cpf_number": "123.456.789-00"
  }
}
```

### Example 2: CPF Validation and Data Retrieval

```json
{
  "skill_name": "cpf_validation",
  "action": "get_cpf_data",
  "parameters": {
    "cpf_number": "98765432100"
  }
}
```

## Best Practices

*   **LGPD Compliance**: Ensure that any retrieved data is handled in strict compliance with the Lei Geral de Proteção de Dados (LGPD) and other relevant privacy regulations. Only public data should be accessed and processed.
*   **Security**: Do not expose sensitive CPF data directly in agent responses unless explicitly authorized and necessary for the task.
*   **Error Handling**: Agents should be prepared to handle `is_valid: false` and `error` responses gracefully.
*   **Rate Limiting**: Be mindful of API rate limits when invoking this skill frequently.

## OpenAPI Specification (Optional)

For enhanced discoverability and integration with OpenAPI-compatible tools, an `openapi.yaml` file describing this skill's API endpoints can be provided in the same directory.
