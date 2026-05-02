# cpfhub-skills

🇺🇸 **English** | [🇧🇷 Português](#português)

**Official AI Agent Skills for [CPFHub.io](https://cpfhub.io) — Brazilian CPF Lookup API**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

---

## What is CPFHub.io?

CPFHub.io is a REST API that returns name, gender, and date of birth from any Brazilian CPF number — in ~300ms, with 99.9% uptime and full LGPD compliance.

**10M+ CPFs queried · 1,300+ active companies · 99.9% uptime**

---

## Available Skills

| Skill | Description | Details |
|-------|-------------|----------|
| `get_person_by_cpf` | Retrieve identity data from a Brazilian CPF number | [get-person-by-cpf/SKILL.md](get-person-by-cpf/SKILL.md) |

---

## Quick Start

```bash
curl -X GET "https://api.cpfhub.io/cpf/12345678909" \\
  -H "x-api-key: YOUR_API_KEY"
```

**Response:**

```json
{
  "success": true,
  "data": {
    "cpf": "12345678909",
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

Get your free API key at [app.cpfhub.io](https://app.cpfhub.io) — no credit card required.

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
        "description": "Brazilian CPF number"
      }
    },
    "required": ["cpf"]
  }
}
```

---

## Use Cases

- **Automated onboarding**: Validate a new user's identity during a conversational sign-up flow
- **Real-time fraud prevention**: Verify CPF identity during online transactions
- **Data enrichment pipelines**: Enrich customer profiles with verified identity data
- **KYC compliance agents**: Automate CPF verification in Know Your Customer workflows

---

## Error Handling

| HTTP Code | Meaning |
|-----------|--------|
| `400` | Invalid CPF format |
| `401` | Invalid or missing API key |
| `404` | CPF not found |
| `429` | Rate limit exceeded |
| `500` | Server error |

---

## Rate Limits

| Plan | Limit |
|------|-------|
| Free | 1 request every 2 seconds · 50 requests/month |
| Pro | 1 request per second · 1,000 requests/month |
| Corporate | Custom |

---

## Plans & Pricing

| Plan | Price | Included | Extra |
|------|-------|----------|-------|
| **Free** | R$ 0/month | 50 lookups | — |
| **Pro** | R$ 149/month | 1,000 lookups | R$ 0,15/lookup |
| **Corporate** | Custom | Custom | Custom |

[View full pricing at cpfhub.io →](https://cpfhub.io#pricing)

---

## Links

- [Documentation](https://cpfhub.io/documentacao)
- [MCP Server (AI Agents)](https://github.com/cpfhub/cpfhub-mcp)
- [OpenAPI Specification](https://github.com/cpfhub/cpfhub-openapi/blob/main/openapi.yaml)
- [Dashboard](https://app.cpfhub.io)
- [Status Page](https://app.cpfhub.io/status)
- [LGPD Compliance](https://cpfhub.io/lgpd)

---

## License

MIT © [CPFHub.io](https://cpfhub.io)

---

# Português

[🇺🇸 English](#cpfhub-skills) | 🇧🇷 **Português**

**Skills oficiais para Agentes de IA do [CPFHub.io](https://cpfhub.io) — API de Consulta de CPF Brasileiro**

---

## O que é o CPFHub.io?

O CPFHub.io é uma API REST que retorna nome, gênero e data de nascimento de qualquer CPF brasileiro — em ~300ms, com 99,9% de uptime e total conformidade com a LGPD.

**10M+ CPFs consultados · 1.300+ empresas ativas · 99,9% uptime**

---

## Skills Disponíveis

| Skill | Descrição | Detalhes |
|-------|------------|----------|
| `get_person_by_cpf` | Recupera dados de identidade a partir de um CPF brasileiro | [get-person-by-cpf/SKILL.md](get-person-by-cpf/SKILL.md) |

---

## Início Rápido

```bash
curl -X GET "https://api.cpfhub.io/cpf/12345678909" \\
  -H "x-api-key: SUA_CHAVE_DE_API"
```

**Resposta:**

```json
{
  "success": true,
  "data": {
    "cpf": "12345678909",
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

Obtenha sua chave de API gratuita em [app.cpfhub.io](https://app.cpfhub.io) — sem cartão de crédito.

---

## Definição da Tool

```json
{
  "name": "get_person_by_cpf",
  "description": "Retrieve identity data from a Brazilian CPF number",
  "parameters": {
    "type": "object",
    "properties": {
      "cpf": {
        "type": "string",
        "description": "Brazilian CPF number"
      }
    },
    "required": ["cpf"]
  }
}
```

---

## Casos de Uso

- **Onboarding automatizado**: Valide a identidade de um novo usuário durante um fluxo de cadastro conversacional
- **Prevenção de fraude em tempo real**: Verifique a identidade do CPF durante transações online
- **Pipelines de enriquecimento de dados**: Enriqueça perfis de clientes com dados de identidade verificados
- **Agentes de compliance KYC**: Automatize a verificação de CPF em fluxos de Know Your Customer

---

## Tratamento de Erros

| Código HTTP | Significado |
|------------|-------------|
| `400` | Formato de CPF inválido |
| `401` | Chave de API inválida ou ausente |
| `404` | CPF não encontrado |
| `429` | Limite de requisições excedido |
| `500` | Erro no servidor |

---

## Limites de Requisição

| Plano | Limite |
|-------|--------|
| Gratuito | 1 requisição a cada 2 segundos · 50 requisições/mês |
| Pro | 1 requisição por segundo · 1.000 requisições/mês |
| Corporativo | Personalizado |

---

## Planos e Preços

| Plano | Preço | Incluído | Extra |
|-------|-------|----------|-------|
| **Gratuito** | R$ 0/mês | 50 consultas | — |
| **Pro** | R$ 149/mês | 1.000 consultas | R$ 0,15/consulta |
| **Corporativo** | Personalizado | Personalizado | Personalizado |

[Ver preços completos em cpfhub.io →](https://cpfhub.io#pricing)

---

## Links

- [Documentação](https://cpfhub.io/documentacao)
- [Servidor MCP (Agentes de IA)](https://github.com/cpfhub/cpfhub-mcp)
- [Especificação OpenAPI](https://github.com/cpfhub/cpfhub-openapi/blob/main/openapi.yaml)
- [Dashboard](https://app.cpfhub.io)
- [Página de Status](https://app.cpfhub.io/status)
- [Conformidade LGPD](https://cpfhub.io/lgpd)

---

## Licença

MIT © [CPFHub.io](https://cpfhub.io)
