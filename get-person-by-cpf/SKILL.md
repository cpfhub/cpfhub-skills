# get_person_by_cpf — CPFHub.io Skill for AI Agents

**Retrieve identity data from a Brazilian CPF number using the [CPFHub.io](https://cpfhub.io) API.**

---

## Description

This skill enables AI agents to look up any Brazilian CPF number and retrieve the holder's full name, gender, and date of birth — in ~300ms, with 99.9% uptime and full LGPD compliance.

Powered by CPFHub.io's multi-source architecture aggregating data from 15+ official and private sources.

---

## Tool Definition

```json
{
  "name": "get_person_by_cpf",
  "description": "Retrieve identity data from a Brazilian CPF number",
  "parameters": {
    "type": "object",
    "properties": {
      "cpf": {
        "type": "string",
        "description": "Brazilian CPF number (with or without formatting)"
      }
    },
    "required": ["cpf"]
  }
}
```

---

## Parameters

### Input

| Parameter | Type     | Required | Description                                                      |
|-----------|----------|----------|------------------------------------------------------------------|
| `cpf`     | `string` | Yes      | Brazilian CPF number. Accepts `000.000.000-00` or `00000000000` |

### Output

| Field           | Type      | Description                         |
|-----------------|-----------|-------------------------------------|
| `success`       | `boolean` | `true` if lookup succeeded          |
| `data.cpf`      | `string`  | CPF number (digits only)            |
| `data.name`     | `string`  | Full name — e.g. `"Fulano de Tal"`  |
| `data.nameUpper`| `string`  | Full name in uppercase              |
| `data.gender`   | `string`  | `"M"` or `"F"`                      |
| `data.birthDate`| `string`  | Date of birth — `"DD/MM/YYYY"`      |
| `data.day`      | `integer` | Birth day                           |
| `data.month`    | `integer` | Birth month                         |
| `data.year`     | `integer` | Birth year                          |

---

## Authentication

All requests require an API key passed via the `x-api-key` header.

Get your free API key at [app.cpfhub.io](https://app.cpfhub.io) — no credit card required.

---

## Example Invocation

```json
{
  "name": "get_person_by_cpf",
  "parameters": {
    "cpf": "123.456.789-00"
  }
}
```

**Response:**

```json
{
  "success": true,
  "data": {
    "cpf": "12345678900",
    "name": "Fulano de Tal",
    "nameUpper": "FULANO DE TAL",
    "gender": "M",
    "birthDate": "15/06/1990",
    "day": 15,
    "month": 6,
    "year": 1990
  }
}
```

---

## curl Example

```bash
curl -X GET "https://api.cpfhub.io/cpf/12345678909" \
  -H "x-api-key: YOUR_API_KEY"
```

---

## Use Cases for AI Agents

- **Automated onboarding**: Validate a new user's identity during a conversational sign-up flow
- **Real-time fraud prevention**: Verify CPF identity during online transactions
- **Data enrichment pipelines**: Enrich customer profiles with verified identity data
- **KYC compliance agents**: Automate CPF verification in Know Your Customer workflows

---

## Error Handling

| HTTP Code | Meaning                       |
|-----------|-------------------------------|
| `400`     | Invalid CPF format            |
| `401`     | Invalid or missing API key    |
| `404`     | CPF not found                 |
| `429`     | Rate limit exceeded           |
| `500`     | Server error                  |
| `503`     | Service temporarily unavailable |

---

## Best Practices

- **LGPD Compliance**: All data retrieved must be handled in strict compliance with Brazil's LGPD. CPFHub.io operates under the legal basis of legitimate interest for fraud prevention and identity verification.
- **Security**: Do not expose raw CPF data in agent responses unless strictly necessary and authorized.
- **Error handling**: Always handle `success: false` responses gracefully.
- **Rate limiting**: Be aware of API rate limits when invoking this skill at high frequency.

---

## MCP Server

CPFHub.io provides a native MCP server, enabling AI agents (Claude, Cursor, Windsurf) to use this skill natively without writing HTTP code.

[View MCP Server →](https://github.com/cpfhub/cpfhub-mcp)

---

## OpenAPI Specification

[View OpenAPI Spec →](https://github.com/cpfhub/cpfhub-openapi/blob/main/openapi.yaml)

---

## Links

- [Documentation](https://cpfhub.io/documentacao)
- [Dashboard](https://app.cpfhub.io)
- [MCP Server](https://github.com/cpfhub/cpfhub-mcp)
- [OpenAPI Spec](https://github.com/cpfhub/cpfhub-openapi/blob/main/openapi.yaml)
- [LGPD Compliance](https://cpfhub.io/compliance)
