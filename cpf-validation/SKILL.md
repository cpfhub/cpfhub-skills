# CPF Consultation Skill for AI Agents

Esta skill oferece a funcionalidade de **consultar números de CPF** (Cadastro de Pessoas Físicas) brasileiros e recuperar dados associados, como nome completo, data de nascimento e sexo.

## Description

A Skill de Consulta de CPF permite que agentes de IA realizem a **consulta de um número de CPF** e, se o CPF for válido, obtenham informações como nome completo, data de nascimento e sexo. Isso é crucial para aplicações que exigem verificação de identidade, prevenção de fraudes ou enriquecimento de dados no contexto brasileiro.

## Parameters

### Input

*   **`cpf_number`** (string, required): O número de CPF de 11 dígitos a ser consultado. Formato: `XXX.XXX.XXX-XX` ou `XXXXXXXXXXX`.

### Output

*   **`success`** (boolean): `true` se a consulta foi bem-sucedida e dados foram encontrados, `false` caso contrário.
*   **`data`** (object, optional): Um objeto contendo os dados associados ao CPF, se disponível e válido. Isso inclui:
    *   `cpf` (string): O número de CPF consultado.
    *   `name` (string): Nome completo do titular.
    *   `nameUpper` (string): Nome completo em letras maiúsculas.
    *   `gender` (string): Gênero (M/F).
    *   `birthDate` (string): Data de nascimento (formato: `DD/MM/YYYY`).
    *   `day` (number): Dia de nascimento.
    *   `month` (number): Mês de nascimento.
    *   `year` (number): Ano de nascimento.
*   **`error`** (string, optional): Uma mensagem de erro se a operação falhou (e.g., "CPF inválido", "Erro na API").

Esta skill pode ser utilizada em uma variedade de cenários, incluindo:

*   **Onboarding de Clientes**: **Consultar CPFs** de novos usuários durante o processo de cadastro para garantir a autenticidade e evitar fraudes, obtendo nome completo, data de nascimento e sexo.
*   **Prevenção a Fraudes**: **Consultar CPFs** para obter nome completo, data de nascimento e sexo antes de aprovar transações financeiras, concessão de crédito ou acesso a serviços sensíveis, ajudando a confirmar a identidade e mitigar riscos.
*   **Enriquecimento de Dados**: Complementar perfis de clientes com informações associadas ao CPF, como nome completo, data de nascimento e sexo, para personalização e segmentação.
*   **Automação de Processos Legais/Administrativos**: Automatizar a verificação de CPFs em processos que exigem conformidade regulatória ou validação de documentos.
*   **Atendimento ao Cliente**: Agilizar o atendimento ao cliente, permitindo que agentes de IA confirmem a identidade do usuário através da **consulta de CPF** para obter nome completo, data de nascimento e sexo de forma rápida e segura.

## Examples of Use

### Example 1: Basic CPF Validation

```json
{
  "skill_name": "cpf_consultation",
  "action": "consult_cpf",
  "parameters": {
    "cpf_number": "123.456.789-00"
  }
}
```

### Example 2: CPF Validation and Data Retrieval

```json
{
  "skill_name": "cpf_consultation",
  "action": "consult_cpf",
  "parameters": {
    "cpf_number": "98765432100"
  }
}
```

## Best Practices

*   **LGPD Compliance**: Garanta que todos os dados recuperados sejam tratados em estrita conformidade com a Lei Geral de Proteção de Dados (LGPD) e outras regulamentações de privacidade relevantes. A API do CPFHub.io fornece dados que são considerados públicos ou que possuem base legal para tratamento, como o legítimo interesse para prevenção de fraudes e verificação de identidade.
*   **Security**: Do not expose sensitive CPF data directly in agent responses unless explicitly authorized and necessary for the task.
*   **Error Handling**: Agents should be prepared to handle `is_valid: false` and `error` responses gracefully.
*   **Rate Limiting**: Be mindful of API rate limits when invoking this skill frequently.

## OpenAPI Specification (Optional)

For enhanced discoverability and integration with OpenAPI-compatible tools, an `openapi.yaml` file describing this skill's API endpoints can be provided in the same directory.
